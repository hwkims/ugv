알겠습니다. 제가 직접 코드를 수정해 드릴 수는 없지만, **Flask 애플리케이션 (`app.py` 또는 유사 파일)과 HTML/JavaScript 템플릿 파일을 어떻게 수정하여 ROS Lidar 데이터를 웹 인터페이스에 표시하고 기본적인 로봇 제어 명령을 보낼 수 있는지 구체적인 예시 코드와 함께 설명**해 드리겠습니다.

**⚠️ 중요:** 이것은 **개념적인 예시 코드**입니다. 실제 `ugv_rpi` 프로젝트의 구조, 사용 중인 ROS 버전(ROS1/ROS2), 정확한 토픽 이름 등에 맞춰 **반드시 수정하고 테스트**해야 합니다. 또한, 에러 처리, 성능 최적화 등은 생략된 기본 형태입니다.

**사전 준비:**

1.  **ROS 환경:** 라즈베리파이에 ROS (ROS1 또는 ROS2)가 설치되어 있고, Lidar 노드가 실행되어 스캔 데이터를 특정 토픽(예: `/scan`)으로 발행(publish)하고 있어야 합니다. 로봇 이동을 위한 노드가 특정 토픽(예: `/cmd_vel`)을 구독(subscribe)하고 있어야 합니다.
2.  **파이썬 라이브러리 설치:** Flask 애플리케이션의 가상 환경 (`ugv-env`)에 필요한 라이브러리를 설치합니다. (ROS 버전에 맞게 선택)
    ```bash
    # ugv_rpi 폴더로 이동
    cd ugv_rpi
    # 가상 환경 활성화 (activate 스크립트 경로는 다를 수 있음)
    source ugv-env/bin/activate 
    
    # Flask-SocketIO 설치 (실시간 통신용)
    pip install Flask-SocketIO rclpy # ROS2 용
    # 또는 pip install Flask-SocketIO rospy # ROS1 용
    
    # 다른 필요한 라이브러리도 설치 (예: simple-websocket)
    pip install simple-websocket Flask
    ```

**1단계: Flask 백엔드 수정 (`app.py` 또는 관련 파일)**

```python
import rclpy # ROS2 사용 시
# import rospy # ROS1 사용 시
from rclpy.node import Node # ROS2 사용 시
from sensor_msgs.msg import LaserScan
from geometry_msgs.msg import Twist
from flask import Flask, render_template, request
from flask_socketio import SocketIO, emit
import threading
import time
import json # Lidar 데이터를 JSON으로 변환하기 위해

# --- 기존 Flask 앱 설정 ---
app = Flask(__name__)
# 앱의 시크릿 키 설정 (실제로는 안전하게 관리해야 함)
app.config['SECRET_KEY'] = 'your_secret_key!' 
# 비동기 모드 설정 (eventlet 또는 gevent 권장, 없으면 기본 스레딩 사용)
# 예: async_mode = 'eventlet' 
async_mode = None 
socketio = SocketIO(app, async_mode=async_mode)

# --- ROS 노드 관련 설정 ---
ros_node = None
latest_scan_data = None # 최신 Lidar 데이터를 저장할 변수
publisher_cmd_vel = None # 로봇 제어 명령 발행자

# ROS2 노드 클래스 정의
class FlaskROSNode(Node):
    def __init__(self):
        super().__init__('ugv_flask_web_node')
        self.get_logger().info('ROS Node for Flask Web UI started')
        
        # Lidar 스캔 데이터 구독자 생성
        self.subscription_scan = self.create_subscription(
            LaserScan,
            '/scan', # 실제 Lidar 토픽 이름으로 변경해야 함
            self.scan_callback,
            10) # QoS 프로파일 깊이
            
        # 로봇 제어 명령 발행자 생성
        global publisher_cmd_vel
        publisher_cmd_vel = self.create_publisher(Twist, '/cmd_vel', 10)

        self.subscription_scan # prevent unused variable warning

    def scan_callback(self, msg):
        # 콜백 함수는 가능한 한 빨리 완료되어야 함
        global latest_scan_data
        # 필요한 데이터만 추출 (예: 각도와 거리) - 데이터 양 줄이기
        ranges = msg.ranges
        angle_min = msg.angle_min
        angle_increment = msg.angle_increment
        
        # 간단히 거리 데이터만 저장 (실제로는 더 정제된 데이터 구조 사용)
        latest_scan_data = {
            'ranges': list(ranges), # 리스트로 변환
            'angle_min': angle_min,
            'angle_increment': angle_increment
        }
        # print("Scan data received") # 디버깅용
        
        # 웹 클라이언트로 Lidar 데이터 전송 (SocketIO 사용)
        # 주의: 너무 자주 보내면 성능 문제 발생 가능. throttling 필요
        socketio.emit('lidar_data', {'data': latest_scan_data})

# ROS 노드를 별도 스레드에서 실행하는 함수
def spin_ros_node():
    global ros_node
    rclpy.init()
    ros_node = FlaskROSNode()
    print("Starting ROS spin...")
    try:
        rclpy.spin(ros_node)
    except KeyboardInterrupt:
        pass
    finally:
        # 노드 종료 및 리소스 정리
        if ros_node:
            ros_node.destroy_node()
        rclpy.shutdown()
        print("ROS node stopped.")

# --- Flask 라우트 및 SocketIO 이벤트 핸들러 ---

# 메인 페이지 라우트
@app.route('/')
def index():
    # 기존 템플릿 렌더링 방식 유지
    # 예: return render_template('index.html', async_mode=socketio.async_mode)
    # ugv_rpi의 기존 코드를 확인하여 필요한 변수 전달
    return render_template('index.html') # 필요에 따라 수정

# 웹 클라이언트가 연결되었을 때 호출
@socketio.event
def connect():
    print('Client connected')
    # 연결 시 최신 Lidar 데이터가 있으면 즉시 전송 (선택 사항)
    # if latest_scan_data:
    #    emit('lidar_data', {'data': latest_scan_data})

# 웹 클라이언트 연결 해제 시 호출
@socketio.event
def disconnect():
    print('Client disconnected')

# 웹 클라이언트로부터 로봇 제어 명령 수신
@socketio.on('robot_control')
def handle_robot_control(json_data):
    global publisher_cmd_vel
    if publisher_cmd_vel:
        try:
            # 수신한 JSON 데이터에서 속도 값 추출
            linear_x = float(json_data.get('linear_x', 0.0))
            angular_z = float(json_data.get('angular_z', 0.0))
            
            # Twist 메시지 생성
            twist_msg = Twist()
            twist_msg.linear.x = linear_x
            twist_msg.angular.z = angular_z
            
            # /cmd_vel 토픽으로 발행
            publisher_cmd_vel.publish(twist_msg)
            # print(f"Published Twist: linear.x={linear_x}, angular.z={angular_z}") # 디버깅
        except Exception as e:
            print(f"Error handling robot control: {e}")
    else:
        print("cmd_vel publisher is not ready.")

# --- 메인 실행 부분 ---
if __name__ == '__main__':
    # ROS 노드를 별도 스레드에서 시작
    ros_thread = threading.Thread(target=spin_ros_node, daemon=True)
    ros_thread.start()
    
    # Flask-SocketIO 앱 실행 (기존 ugv_rpi의 실행 방식 확인 필요)
    # host='0.0.0.0' 으로 설정해야 외부에서 접속 가능
    print("Starting Flask-SocketIO server...")
    socketio.run(app, host='0.0.0.0', port=5000, debug=True, use_reloader=False) 
    # use_reloader=False 중요! 리로더는 스레드/ROS 초기화와 충돌 가능
```

**2단계: HTML 템플릿 수정 (`templates/index.html` 또는 관련 파일)**

```html
<!DOCTYPE html>
<html>
<head>
    <title>UGV Control with Lidar</title>
    <!-- 기존 CSS/JS 파일 포함 -->
    <style>
        /* Lidar 시각화를 위한 Canvas 스타일 */
        #lidarCanvas {
            border: 1px solid black;
            background-color: #f0f0f0;
            display: block; /* 중앙 정렬 등을 위해 */
            margin: 10px auto; /* 예시: 위아래 여백 및 중앙 정렬 */
        }
        /* 제어 버튼 스타일 (예시) */
        .controls button {
            padding: 10px;
            margin: 5px;
            font-size: 16px;
        }
        .controls {
            text-align: center; /* 버튼 중앙 정렬 */
            margin-top: 10px;
        }
    </style>
</head>
<body>
    <h1>UGV Control Panel</h1>

    <!-- 기존 웹 인터페이스 요소들 -->
    <!-- (비디오 스트리밍, 로봇 상태 표시 등) -->

    <hr>

    <h2>Lidar Visualization</h2>
    <!-- Lidar 데이터를 그릴 Canvas 요소 -->
    <canvas id="lidarCanvas" width="400" height="400"></canvas>

    <h2>Robot Control</h2>
    <div class="controls">
        <button onclick="sendControl(0.2, 0.0)">Forward</button><br>
        <button onclick="sendControl(0.0, 0.5)">Turn Left</button>
        <button onclick="sendControl(0.0, -0.5)">Turn Right</button><br>
        <button onclick="sendControl(-0.2, 0.0)">Backward</button><br>
        <button onclick="sendControl(0.0, 0.0)">Stop</button>
    </div>

    <!-- Socket.IO 클라이언트 라이브러리 로드 -->
    <!-- Flask-SocketIO 버전에 맞는 URL 사용 필요 -->
    <script src="https://cdn.socket.io/4.6.0/socket.io.min.js"></script> 
    
    <script>
        // Socket.IO 서버에 연결
        // 네임스페이스가 있다면 지정: io('/mynamespace')
        const socket = io(); 

        socket.on('connect', () => {
            console.log('Connected to server');
        });

        socket.on('disconnect', () => {
            console.log('Disconnected from server');
        });

        // Lidar 데이터를 받을 이벤트 리스너
        socket.on('lidar_data', (msg) => {
            // console.log('Lidar data received:', msg.data); // 디버깅
            if (msg.data) {
                drawLidar(msg.data);
            }
        });

        // --- Lidar 데이터 시각화 함수 ---
        const canvas = document.getElementById('lidarCanvas');
        const ctx = canvas.getContext('2d');
        const canvasWidth = canvas.width;
        const canvasHeight = canvas.height;
        const centerX = canvasWidth / 2;
        const centerY = canvasHeight / 2;
        // 지도 스케일 (미터 단위를 픽셀로 변환, 조정 필요)
        const scale = 20; // 예: 1미터 = 20픽셀 

        function drawLidar(lidarData) {
            // 캔버스 지우기
            ctx.clearRect(0, 0, canvasWidth, canvasHeight);

            // 로봇 위치 (중앙) 그리기 (선택 사항)
            ctx.fillStyle = 'blue';
            ctx.beginPath();
            ctx.arc(centerX, centerY, 5, 0, 2 * Math.PI);
            ctx.fill();

            // Lidar 스캔 포인트 그리기
            ctx.fillStyle = 'red';
            if (lidarData && lidarData.ranges) {
                const ranges = lidarData.ranges;
                const angle_min = lidarData.angle_min;
                const angle_increment = lidarData.angle_increment;

                for (let i = 0; i < ranges.length; i++) {
                    const distance = ranges[i];
                    // 유효한 거리 값만 그리기 (inf, nan 제외, 최대/최소 거리 제한 등)
                    if (distance > 0.1 && distance < 10.0) { 
                        const angle = angle_min + i * angle_increment;
                        
                        // 극좌표계 -> 직교좌표계 변환
                        // ROS 좌표계는 일반적으로 X축이 전방, Y축이 왼쪽
                        // Canvas 좌표계는 X축이 오른쪽, Y축이 아래쪽 이므로 변환 필요
                        const x = centerX + (distance * scale * Math.cos(angle));
                        const y = centerY - (distance * scale * Math.sin(angle)); // Y축 반전

                        // 점 찍기
                        ctx.fillRect(x - 1, y - 1, 3, 3); // 작은 사각형으로 점 표시
                    }
                }
            }
        }
        
        // --- 로봇 제어 함수 ---
        function sendControl(linear_x, angular_z) {
            console.log(`Sending control: linear=${linear_x}, angular=${angular_z}`);
            // 'robot_control' 이벤트를 서버로 전송
            socket.emit('robot_control', {
                linear_x: linear_x,
                angular_z: angular_z
            });
        }

    </script>
    
    <!-- 기존 JS 파일 포함 -->

</body>
</html>
```

**3단계: 통합 및 실행**

1.  수정한 `app.py` (또는 메인 Flask 파일)와 `index.html` (또는 관련 템플릿 파일)을 `ugv_rpi` 프로젝트의 적절한 위치에 저장합니다.
2.  터미널에서 `ugv_rpi` 폴더로 이동하여 가상 환경을 활성화합니다.
3.  수정된 Flask 애플리케이션을 실행합니다. (기존 `autorun.sh` 또는 직접 실행 방식 확인)
    ```bash
    # 가상환경 활성화 후
    python app.py 
    ```
    *   **주의:** `sudo ./setup.sh`나 `autorun.sh`를 다시 실행해야 할 수도 있습니다. 기존 실행 방식과 충돌하지 않도록 주의하세요.
4.  웹 브라우저에서 `http://<라즈베리파이_IP>:5000` 으로 접속하여 Lidar 데이터가 시각화되고 제어 버튼이 작동하는지 확인합니다.

**고려 사항 및 개선점:**

*   **성능:** Lidar 데이터는 매우 빠르게 생성됩니다. 모든 데이터를 실시간으로 웹소켓을 통해 보내고 그리는 것은 성능 부하를 유발할 수 있습니다. 데이터 샘플링, 서버 측 렌더링, 또는 데이터 전송 빈도 조절(throttling)이 필요할 수 있습니다.
*   **ROS-Flask 통합:** `rclpy.spin()`을 별도 스레드에서 실행하는 것은 일반적인 방법이지만, 복잡한 애플리케이션에서는 GIL(Global Interpreter Lock) 문제나 스레드 간 데이터 동기화 문제가 발생할 수 있습니다. 더 견고한 구조가 필요할 수 있습니다.
*   **데이터 시각화:** Canvas API는 간단한 시각화에 적합하지만, 더 복잡한 지도나 3D 시각화에는 `three.js`나 `RVizWeb` 같은 전문 라이브러리를 사용하는 것이 좋습니다.
*   **제어 인터페이스:** 버튼 방식은 간단하지만, 조이스틱 인터페이스(가상 또는 물리적)를 구현하면 더 직관적인 제어가 가능합니다.
*   **에러 처리:** 예시 코드에는 에러 처리가 거의 없습니다. 실제 애플리케이션에서는 ROS 노드 연결 실패, 데이터 형식 오류 등을 처리해야 합니다.
*   **ROS1 vs ROS2:** 제시된 코드는 ROS2 (`rclpy`) 기준입니다. ROS1 (`rospy`)을 사용한다면 노드 초기화, 구독/발행 방식, 메시지 타입 임포트 등이 달라집니다.

이 예시 코드를 바탕으로 실제 `ugv_rpi` 코드에 적용하고 필요한 부분을 수정해나가시면 됩니다. 구현 중 막히는 부분이 있다면 더 구체적으로 질문해주세요.
