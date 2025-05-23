# 🤖 UGV Beast PI ROS2
![스크린샷(67)](https://github.com/user-attachments/assets/c4910802-d233-40a4-8976-9510e504c446)
![스크린샷(67)](https://github.com/user-attachments/assets/438e1cc7-d788-4ec9-9336-e00265f9a01c)
![스크린샷(65)](https://github.com/user-attachments/assets/11ce8049-8cd7-445b-a322-1c78beba0301)
![스크린샷(64)](https://github.com/user-attachments/assets/e2acd574-3404-4d01-a8a7-cf245188af5d)
![스크린샷(64)](https://github.com/user-attachments/assets/0288dba0-3edb-4b97-b956-257920770c68)
![스크린샷(64)](https://github.com/user-attachments/assets/9894a854-1084-46d5-8489-7de61600cb38)

---
![IMG_2303](https://github.com/user-attachments/assets/77abb3f8-7b07-4579-9067-53648a785c03)

🔌 **주요 인터페이스:** I2C, UART, TTL 직렬 버스 서보 제어 인터페이스
![IMG_2302](https://github.com/user-attachments/assets/aacc8d2f-ba67-48e4-a7de-aef65fa58e25)
![IMG_2301](https://github.com/user-attachments/assets/6d8a8e07-c288-4518-8a32-1270cde1c2a6)

---

## ℹ️ 소개

UGV Beast는 오프로드 추적형 오픈소스 AI 로봇 🤖으로, 듀얼 컨트롤러 구조를 특징으로 합니다. ESP32 슬레이브 장치는 모터 PID, IMU 센서, OLED 화면, 서보, LED ON/OFF 등을 제어하여 호스트 컴퓨터의 IO 리소스를 크게 줄이고 고성능 통신 인터페이스를 제공합니다. 호스트 장치는 **Raspberry Pi 4B/5**를 지원하여 높은 연산 능력 🧠과 특정 전략과 같은 고급 기능을 제공합니다.

로봇 본체는 두께 2mm의 **전체 알루미늄 합금 쉘**을 사용하여 구조적 강도와 내구성이 뛰어납니다 💪. 여러 개의 **독립 서스펜션 시스템**을 활용하여 복잡한 지형의 충격을 효과적으로 흡수합니다. 인코더가 장착된 2개의 기어 모터는 폐쇄 루프 속도 제어를 통해 진동을 방지하고, 최대 **0.35m/s**의 속도로 우수한 주행 성능을 제공합니다 🚀. 내장된 **3S 리튬 배터리 UPS 전원 공급 모듈** 🔋은 강력하고 오래 지속되는 전력을 공급하며, 충전 중에도 연속 사용이 가능하여 장기적인 개발 및 사용 요구를 충족합니다.

Raspberry Pi 4B/5에는 USB 카메라 📷가 장착되어 있어, 사용자는 높은 프레임 속도와 낮은 지연 시간으로 부드러운 실시간 영상 스트리밍을 경험할 수 있으며, 사진 및 비디오 촬영 기능으로 다양한 순간을 포착할 수 있습니다. 또한 배터리 전압, CPU 사용량 등 로봇의 상태 정보가 **WEB 애플리케이션**을 통해 실시간으로 표시되어 사용자가 로봇 상태를 쉽게 모니터링할 수 있습니다.

로봇 비전 시스템은 **2DOF(자유도) 고토크 유연 팬틸트**와 **160° 초광각 5백만 화소 카메라** 👀를 갖추고 있어 넓은 시야각과 유연한 관찰 각도를 제공하며, 다양한 AI 머신 비전 기능을 지원합니다. 팬틸트 옆의 고휘도 LED 스포트라이트 💡는 저조도 환경에서도 선명한 시야를 확보해 줍니다. **피카티니 레일** 설계를 통해 사용자는 추가적인 전술 액세서리를 쉽게 확장하여 로봇의 기능을 더욱 향상시킬 수 있습니다 🔗.

사용자가 로봇의 잠재력을 최대한 활용할 수 있도록, **JupyterLab 웹 애플리케이션**을 포함한 온라인 문서와 튜토리얼 📚을 제공합니다. 로봇 공학 초보자부터 숙련된 개발자까지 모두 단계별 학습, 이해, 창작 활동을 지원합니다.

---

## ✨ 특징

*   ✅ **고성능 듀얼 컨트롤러** 💻: ESP32 슬레이브 컨트롤러는 정밀한 모터 PID 제어 및 센서 데이터 처리를 담당하고, Raspberry Pi 4B/5 호스트 컨트롤러는 고수준 연산을 수행하여 효율적인 로봇 작동을 보장합니다.
*   ✅ **오픈소스 코드** 🌐: 호스트 장치는 최신 Raspberry Pi OS (Debian Bookworm) 기반이며, 웹 애플리케이션은 Flask와 Python으로 개발되었습니다. 모든 소프트웨어 플랫폼이 오픈 소스여서 학습 및 2차 개발이 용이합니다.
*   ✅ **풍부한 튜토리얼** 📚: JupyterLab 대화형 튜토리얼, 그래픽 튜토리얼, 비디오 튜토리얼 등 다양한 학습 자료를 제공하여 로봇 기술 초보자의 학습 곡선을 단축합니다.
*   ✅ **넓은 시야각** 👀: 2자유도 고토크 팬틸트는 수평 360° 시야각을 제공하며, 160° 초광각 5백만 화소 카메라는 넓은 범위를 포착합니다.
*   ✅ **로봇 비전** 👁️‍🗨️: 색상, 객체, 제스처 인식, 얼굴 및 움직임 감지 등 다양한 로봇 비전 기능을 통합하고 확장 가능합니다.
*   ✅ **풍부한 상호작용** 🎮: 실시간 비디오 스트리밍, 디지털 줌, 사진/비디오 촬영 기능과 웹 애플리케이션을 통한 실시간 로봇 정보 표시로 사용자 경험을 향상시킵니다.
*   ✅ **크로스플랫폼 지원** 📱💻: 별도 앱 설치 없이 다양한 플랫폼에서 원격 제어가 가능하며, Pgyer, Cpolar, LocalTunnel 등의 솔루션을 통해 로컬 네트워크 외부에서도 원격 제어를 구현할 수 있습니다.
*   ✅ **확장성** 🔗: 확장 플레이트와 피카티니 레일을 통해 다양한 전술 액세서리 추가가 용이합니다. 예비 LED 인터페이스로 물총 등 주변 장치 확장이 가능하며, 4G/5G 모듈 확장도 지원합니다.
*   ✅ **견고한 구조** 💪: 2mm 두께의 전체 알루미늄 합금 쉘은 뛰어난 구조적 강도와 내구성을 제공합니다.
*   ✅ **고성능 구동 모터** 🚀: 인코더가 장착된 2개의 기어드 모터로 폐쇄 루프 속도 제어를 구현하며, 최대 0.35m/s의 속도를 냅니다.
*   ✅ **다중 독립 서스펜션 시스템** 🚜: 각 측면에 4개의 독립 서스펜션이 있어 하중을 실은 상태에서의 등반 능력이 우수합니다.
*   ✅ **긴 배터리 수명** 🔋: 3S 리튬 배터리 UPS 시스템은 충전 중 연속 사용을 지원하여 긴 작동 시간을 보장합니다.

---

## 🛠️ 제품 조립

이 조립 튜토리얼은 ACCE 모델용 Raspberry Pi 4B/5 설치와 리튬 배터리 설치 두 부분으로 구성됩니다. (상세 튜토리얼은 별도 제공)

---

## 🚀 제품 기본 사용법

### ⚠️ 주의사항

사용 전 반드시 읽어주세요:

*   본 제품은 공장 출고 시 **리튬 배터리가 설치되어 있지 않습니다**. 사용 전 **18650 리튬 배터리 3개**를 직접 설치해야 합니다. (용량 2200mA 이상, 방전율 4C 이상 권장)
*   ACCE 모델 구매자는 **Raspberry Pi 마더보드를 직접 준비하고 설치**해야 합니다.
*   배터리를 처음 연결할 때, 배터리 모듈의 LED가 켜지는지 확인하세요. LED가 켜지면 **극성이 반대로 연결된 것**이니 즉시 수정해야 합니다. 반대로 연결된 상태에서 충전하면 폭발 위험이 있습니다! 💥
*   본 제품은 심한 충격에 약하며 **방수가 되지 않습니다**. 💧🚫

### ▶️ 처음 사용하기

제품과 함께 제공된 TF 카드는 소프트웨어 및 ROS2 기능이 미리 구성된 이미지입니다. TF 카드를 Raspberry Pi에 삽입하면 바로 사용할 수 있습니다.

1.  **전원 연결**: 제공된 12V 5A 전원 어댑터를 제품의 전원 인터페이스에 연결합니다.
2.  **전원 켜기**: 전원 스위치를 켜면 제품이 초기화되고 OLED 화면에 초기화 정보가 표시됩니다.
3.  **핫스팟 생성 (AP 모드)**: Raspberry Pi는 부팅 후 자동으로 **`AccessPopup`** 이라는 이름의 Wi-Fi 핫스팟을 생성합니다. (비밀번호: **`1234567890`**)
4.  **OLED 정보 확인**: 부팅 완료 후 OLED 화면에는 다음과 같은 정보가 표시됩니다.
    *   **E:** 이더넷 IP 주소 (연결 시) / `No Ethernet` (미연결 시)
    *   **W:** Wi-Fi IP 주소 (AP 모드: `192.168.50.5` / STA 모드: 할당된 IP)
    *   **F/J:** 포트 번호 (`5000`: 웹 제어 페이지 / `8888`: JupyterLab)
    *   **AP/STA:** 현재 Wi-Fi 모드 / 사용 시간 / 신호 강도 (STA 모드 시)
5.  **웹 제어 인터페이스 접속**:
    *   **AP 모드**: `AccessPopup` 핫스팟에 연결 후, 웹 브라우저 주소창에 `http://192.168.50.5:5000` 입력
    *   **STA 모드**: 로봇이 연결된 Wi-Fi 네트워크와 동일한 네트워크에 있는 장치에서 웹 브라우저 주소창에 `http://<로봇의 W 라인 IP 주소>:5000` 입력 (예: `http://192.168.10.156:5000`)

*   **참고**: 제어 장치는 로봇과 **동일한 로컬 네트워크(LAN)**에 있어야 합니다.

### 🌐 네트워크 설정

자신의 Wi-Fi 네트워크에 연결하려면 JupyterLab 페이지에서 네트워크 설정을 진행해야 합니다.

**JupyterLab 페이지 접속 방법:**

*   웹 제어 인터페이스 (`:5000`) 우측 상단의 **JupyterLab** 버튼 클릭
*   웹 브라우저 주소창에 로봇 IP 주소와 포트 `8888` 입력 (초기 AP 모드: `http://192.168.50.5:8888`)

#### 1️⃣ 처음으로 알려진 WIFI 연결하기 (STA 모드 설정)

1.  JupyterLab 페이지 하단의 **Terminal**을 엽니다.
2.  프로젝트 폴더로 이동합니다:
    ```bash
    bash
    cd ~/ugv_rpi/AccessPopup/
    ```
3.  설정 스크립트에 실행 권한을 부여합니다:
    ```bash
    sudo chmod +x installconfig.sh
    ```
4.  설정 스크립트를 실행합니다:
    ```bash
    sudo ./installconfig.sh
    ```
5.  스크립트 메뉴에서 **`5`** (Set up a new WIFI connection)를 입력하고 Enter 키를 누릅니다.
6.  주변 Wi-Fi 목록이 표시되면 연결하려는 Wi-Fi의 **번호**를 입력하고 Enter 키를 누릅니다.
7.  해당 Wi-Fi의 **비밀번호** 🔑를 입력하고 Enter 키를 누릅니다.
8.  연결이 성공하면 OLED 화면의 **W** 라인 IP 주소가 변경됩니다. **변경된 IP 주소**를 사용하여 JupyterLab (`:8888`) 및 웹 제어 페이지 (`:5000`)에 다시 접속해야 합니다.
9.  터미널 화면에서 아무 키나 누른 후, **`9`** (Exit)를 입력하여 스크립트를 종료합니다.

*   **참고**: 설정된 Wi-Fi 범위를 벗어나면 로봇은 자동으로 **`AccessPopup`** 핫스팟 (AP 모드)으로 전환됩니다.

#### 🔄 WIFI 모드 전환

*   **STA 모드 → AP 모드 전환**:
    JupyterLab 터미널에서 다음 명령을 실행합니다.
    ```bash
    sudo accesspopup -a
    ```
*   **AP 모드 → STA 모드 전환 (이전에 설정한 Wi-Fi로)**:
    JupyterLab 터미널에서 다음 명령을 실행합니다.
    ```bash
    sudo accesspopup
    ```
*   **주의**: 모드 전환 시 IP 주소가 변경되므로, 웹 페이지 접속 주소도 **새 IP 주소**로 변경해야 합니다.

#### 🗑️ 알려진 WIFI 삭제

1.  JupyterLab 터미널을 열고 `bash`를 입력하여 프로젝트 폴더로 이동합니다.
2.  현재 연결된 네트워크 목록을 확인합니다:
    ```bash
    nmcli connection show
    ```
3.  삭제하려는 Wi-Fi 연결 이름을 확인하고 다음 명령을 실행합니다 (`<connection_name>`을 실제 이름으로 대체):
    ```bash
    sudo nmcli connection delete <connection_name>
    ```
*   **참고**: 현재 연결된 Wi-Fi를 삭제하면 자동으로 AP 모드로 전환됩니다.

### 🔐 SSH 서비스 활성화

원격 터미널 접속을 위해 SSH 서비스를 활성화할 수 있습니다.

1.  JupyterLab 페이지에서 **Terminal**을 엽니다.
2.  `raspi-config` 도구를 실행합니다:
    ```bash
    sudo raspi-config
    ```
3.  키보드 화살표 키를 사용하여 **`3 Interface Options`** 로 이동하고 Enter 키를 누릅니다.
4.  **`I2 SSH`** 를 선택하고 Enter 키를 누릅니다.
5.  **`<Yes>`** 를 선택하여 SSH 서비스를 활성화하고 Enter 키를 누릅니다.
6.  확인 메시지가 나타나면 Enter 키를 누릅니다.
7.  `raspi-config` 메인 화면에서 오른쪽 화살표 키를 사용하여 **`<Finish>`** 로 이동하고 Enter 키를 누릅니다.
8.  변경 사항을 적용하기 위해 시스템을 재부팅합니다:
    ```bash
    sudo reboot
    ```

---

## 🦾 제품 ROS2 사용 방법

*   ⚙️ **UGV Beast PI ROS2 1. 준비**
*   ⚙️ **UGV Beast PI ROS2 2. RViz로 제품 모델 보기**
*   ⚙️ **UGV Beast PI ROS2 3. 조이스틱 또는 키보드를 사용하여 제어**
*   ⚙️ **UGV Beast PI ROS2 4. 라이다 기반 2D 매핑**
*   ⚙️ **UGV Beast PI ROS2 5. 깊이 카메라 기반 3D 매핑**
*   ⚙️ **UGV Beast PI ROS2 6. 자동 내비게이션**
*   ⚙️ **UGV Beast PI ROS2 7. 내비게이션 및 SLAM 매핑**
*   ⚙️ **UGV Beast PI ROS2 8. 웹 기반 자연어 상호작용**
*   ⚙️ **UGV Beast PI ROS2 9. 웹 기반 제어 도구**
*   ⚙️ **UGV Beast PI ROS2 10. 명령 상호작용**
*   ⚙️ **UGV Beast PI ROS2 11. Gazebo 시뮬레이션 디버깅**
    *(각 항목에 대한 상세 내용은 별도 문서/튜토리얼 참조)*

---

## 📁 리소스

*   📐 **3D 다이어그램**
    *   팬틸트 포함 다이어그램
*   🔩 **STEP 모델**
    *   팬틸트 포함 모델
*   🤖 **ROS2 오픈소스 프로젝트**
    *   프로젝트 주소: UGV Beast ROS2 기능 패키지
*   💻 **제품 오픈소스 프로그램**
    *   호스트 장치 (Raspberry Pi) 메인 프로그램

---

## ❓ 지원

### 🆘 기술 지원

기술 지원이 필요하거나 피드백/리뷰가 있으시면, 티켓 제출 시스템을 통해 문의해 주십시오. 지원팀이 영업일 기준 1~2일 이내에 확인 후 답변해 드립니다.
**근무 시간:** 오전 9시 - 오후 6시 GMT+8 (월요일 ~ 금요일)

**(티켓 제출 버튼/링크는 원본 문서 참조)**
**프로젝트 목표:**

*   Waveshare UGV Beast PI ROS2 로봇을 기반으로, 로컬에서 실행되는 Ollama LLM(거대 언어 모델)을 통합하여 자연어 명령을 이해하거나 질문에 답할 수 있는 AI 로봇을 만듭니다.

**핵심 아이디어:**

1.  **Ollama 실행:** 적합한 LLM(예: Llama 3, Phi-3 등)을 사용하여 Ollama를 라즈베리 파이 5 자체에서 실행하거나 (소형 모델의 경우 성능이 허용된다면), 더 현실적으로는 로봇과 동일한 네트워크에 있는 별도의 컴퓨터에서 실행합니다.
2.  **로봇 소프트웨어 수정:** 로봇의 소프트웨어(기존의 Python Flask 웹 애플리케이션 또는 라즈베리 파이의 새로운 ROS 2 노드)를 수정하여 다음을 수행합니다:
    *   사용자 입력(웹 UI의 텍스트, 추후 음성 가능)을 받습니다.
    *   이 입력을 Ollama API 엔드포인트에 프롬프트로 보냅니다.
    *   LLM의 응답을 받습니다.
    *   응답을 분석하여 명령이나 정보를 추출합니다.
    *   추출된 명령을 로봇이 수행할 수 있는 동작(예: 이동, 카메라 제어, 센서 읽기)으로 변환합니다. 이때 기존 로봇 제어 함수나 ROS 2 토픽/서비스를 사용합니다.
    *   응답이나 상태를 사용자에게 다시 표시합니다.

**단계별 개발 계획:**

**1단계: 설정 및 기본 로봇 작동**

1.  **로봇 조립:** 제공된 조립 튜토리얼에 따라 라즈베리 파이(ACCE 모델의 경우)와 18650 배터리를 설치합니다.
2.  **초기 부팅 및 네트워크:**
    *   제공된 TF 카드 이미지를 사용합니다.
    *   처음에는 12V 전원 어댑터를 사용하여 로봇을 부팅합니다.
    *   컴퓨터/휴대폰을 `AccessPopup` WiFi 핫스팟(비밀번호: `1234567890`)에 연결합니다.
    *   웹 UI (`http://192.168.50.5:5000`) 및 JupyterLab (`http://192.168.50.5:8888`)에 접속합니다.
    *   **매우 중요:** "네트워크 구성" 단계에 따라 로봇을 사용자의 주 WiFi 네트워크(STA 모드)에 연결합니다. OLED에 표시되는 새 IP 주소를 기록합니다. (Ollama가 다른 컴퓨터에 있는 경우 통신에 필수적입니다.)
    *   개발 접근성을 높이기 위해 SSH 서비스를 활성화합니다.
3.  **제어 익숙해지기:** 웹 UI 및 ROS 2 키보드/조이스틱 제어(문서의 `UGV Beast PI ROS2 3. Control using the joystick or keyboard` 참고)를 사용하여 로봇의 작동 방식을 이해합니다. JupyterLab 튜토리얼을 탐색합니다.

**2단계: Ollama 설정 및 기본 API 상호작용**

1.  **Ollama 설치:**
    *   **(권장)** 로봇과 동일한 네트워크에 있는 별도의 (성능 좋은) 컴퓨터에 Ollama를 설치합니다.
    *   **(실험적)** 라즈베리 파이 5에 직접 Ollama를 설치해 봅니다. 성능 제한이 있을 수 있으므로 매우 작은 모델(예: Phi-3 Mini)을 선택합니다.
2.  **LLM 다운로드:** Ollama가 설치된 기기의 터미널에서 `ollama pull phi3` (또는 `llama3:8b` 등 다른 모델)를 실행합니다.
3.  **Ollama 서비스 실행:** Ollama 서비스가 실행 중인지 확인합니다. (기본: `localhost:11434`, 별도 PC의 경우 네트워크 IP에서 수신하도록 설정 필요).
4.  **로봇에서 Ollama API 테스트:**
    *   로봇의 라즈베리 파이에 SSH로 접속합니다.
    *   `requests` 라이브러리가 없다면 설치합니다 (`pip install requests`).
    *   `curl` 또는 간단한 Python 스크립트를 사용하여 Ollama API에 요청을 보냅니다. (Ollama가 다른 PC에 있다면 해당 PC의 IP 주소와 포트 사용)
    *   LLM으로부터 유효한 JSON 응답을 받는지 확인합니다. (실패 시 네트워크/방화벽 문제 해결)

**3단계: 자연어 명령을 위한 Ollama 통합**

1.  **통합 지점 선택:**
    *   **(간단한 시작)** 기존 Flask 웹 애플리케이션 수정 (`~/ugv_rpi/app.py` 추정).
    *   **(ROS 방식)** 명령 문자열 토픽을 구독하고, Ollama와 상호작용하며, 제어 명령(예: `/cmd_vel`에 `Twist` 메시지 발행)을 발행하거나 서비스를 호출하는 새로운 ROS 2 Python 노드를 생성합니다.
2.  **상호작용 로직 개발 (Flask 예시):**
    *   웹 UI HTML에 텍스트 입력 필드와 제출 버튼을 추가합니다.
    *   Flask `app.py`에서:
        *   웹 폼에서 텍스트를 받는 새 라우트(예: `/process_command`)를 만듭니다.
        *   `requests` 라이브러리를 import 합니다.
        *   Ollama API 엔드포인트 URL을 정의합니다.
        *   **프롬프트 엔지니어링:** 사용자 텍스트를 해석하고 미리 정의된 로봇 동작에 매핑하도록 Ollama에 요청하는 프롬프트를 구성합니다. (예: "사용자 명령: '{user_text}'. 다음 동작 키워드 중 하나로만 응답하세요: MOVE_FORWARD, TURN_LEFT, READ_VOLTAGE, UNKNOWN...")
        *   Ollama API를 호출하고 응답(예: 'MOVE_FORWARD')을 파싱합니다.
        *   **동작 매핑:** `if/elif/else` 문을 사용하여 파싱된 동작 키워드를 기반으로 실제 로봇 제어 함수(모터, 서보, 센서 읽기 등)를 호출합니다. (`ugv_rpi` 프로젝트의 소스 코드를 탐색하여 해당 함수를 찾아야 합니다.)
        *   피드백 메시지를 웹 UI로 반환합니다.

**4단계: AI 기능 향상**

1.  **상황 인식:**
    *   **센서 판독:** 로봇 상태에 대한 질문에 답하기 전에 관련 센서(예: 배터리 전압)를 읽고, 이 정보를 프롬프트에 포함시킵니다. ("현재 배터리 전압은 11.5V입니다. 사용자는 '{user_question}'이라고 질문했습니다...")
    *   **비전 통합 (고급):** 로봇의 비전 기능을 사용하여 객체 등을 감지하고, 그 결과를 Ollama 프롬프트에 넣어 자연스러운 설명을 생성하게 합니다. (또는 LLaVA 같은 멀티모달 모델 사용)
2.  **복잡한 상호작용:** 순차적 명령이나 더 미묘한 요청을 처리하도록 프롬프트 엔지니어링을 개선합니다.
3.  **음성 제어 (확장):** USB 마이크를 추가하고 음성-텍스트 변환 라이브러리(예: `vosk`)를 사용하여 텍스트를 3단계의 명령 처리 로직에 입력합니다.

**5단계: ROS 2 통합 (더 견고한 방식)**

*   3/4단계의 로직을 전용 ROS 2 노드로 리팩토링합니다.
*   이 노드는 `/natural_language_command` 같은 토픽을 구독합니다.
*   Ollama와 상호작용합니다.
*   해석된 명령에 따라 표준 ROS 2 토픽( `/cmd_vel` 등)에 메시지를 발행하거나 관련 ROS 2 서비스를 호출합니다.
*   피드백을 `/command_feedback` 토픽에 게시할 수 있습니다.
*   이를 통해 AI 로직이 웹 서버와 분리되어 로봇의 ROS 생태계와 더 잘 통합됩니다.

**주요 고려 사항:**

*   **성능:** LLM 실행은 리소스를 많이 소모할 수 있습니다. 라즈베리 파이의 CPU/RAM 사용량을 모니터링하고, 가능하면 별도 PC에서 Ollama를 실행하는 것이 좋습니다.
*   **네트워크 지연:** 파이와 Ollama 서버 간 통신에는 지연이 발생합니다. 실시간 제어 시 이를 고려해야 합니다.
*   **프롬프트 엔지니어링:** LLM으로부터 신뢰할 수 있는 해석을 얻으려면 프롬프트의 품질이 매우 중요합니다.
*   **오류 처리:** 네트워크 문제, Ollama 타임아웃, 예상치 못한 LLM 응답 등에 대한 견고한 오류 처리를 구현해야 합니다.
*   **로봇 안전:** LLM의 해석이 항상 완벽하지 않을 수 있으므로 비상 정지 수단(STOP 명령, 물리적 스위치 등)을 확보하고 안전한 장소에서 테스트를 시작해야 합니다.
*   **기존 코드 탐색:** 제공된 "호스트 장치 (라즈베리 파이) 메인 프로그램" 및 "ROS2 오픈 소스 프로젝트" 코드를 깊이 탐색하여 하드웨어 제어 및 ROS 2 노드/토픽 상호작용 방법을 이해하는 것이 중요합니다.
  https://theportalwiki.com/wiki/Turret_voice_lines
https://www.waveshare.com/ugv-beast-ros2-kit.htm
https://www.waveshare.com/wiki/UGV_Beast_PI_ROS2
https://github.com/waveshareteam/ugv_rpi

https://github.com/waveshareteam
