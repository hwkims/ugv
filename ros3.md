
# UGV Beast PI ROS2 3. 조이스틱 또는 키보드를 사용한 제어 - Waveshare Wiki

## 내비게이션 메뉴

*   Waveshare Wiki
*   Raspberry Pi
    *   보드/키트
    *   디스플레이
    *   카메라
    *   확장 보드
    *   올인원
    *   로봇
    *   휴대용 게임기
    *   액세서리
    *   기타 Android/Linux 보드
*   AI
    *   보드/키트
    *   디스플레이
    *   카메라
    *   확장 보드
    *   로봇
*   Displays
    *   LCD/OLED
    *   e-Paper
*   IoT
    *   장거리 무선
    *   단거리 무선
    *   유선 통신/변환기
    *   카메라/오디오/비디오
    *   센서
    *   모터/서보
    *   기타
*   Robotics
    *   모바일 로봇
    *   개 형태 로봇
    *   드라이버/센서
    *   로봇 팔/제어
*   MCU/FPGA
    *   Arduino
    *   micro:bit
    *   STM32
    *   FPGA
*   Support
*   IC
*   제품명 검색

---

<table style="float: right; margin-left: 5px; margin-bottom: 5px; width: 30%;">
<tbody><tr>
<td>
<table style="background: transparent; width: 100%; text-align: center; border-radius: 0.5em; background-color: #00acac;">
<tbody><tr>
<td style="text-align: center; color: white;"><b>UGV Beast PI ROS2</b></td>
</tr>
<tr>
<td style="background: white; margin: 5px; border-radius: 0.5em;"><a href="https://www.waveshare.com/ugv-beast-ros2-kit.htm" title="UGV Beast" target="_blank" rel="nofollow noreferrer noopener"><img alt="UGV Beast" src="https://www.waveshare.com/w/upload/4/47/UGV-Beast-PT-PI5-ROS2-Kit-1.jpg" decoding="async" loading="lazy" width="360" height="270"></a><br><br><small>I2C, UART<br>TTL 시리얼 버스 서보 제어 인터페이스</small>
</td>
</tr>
</tbody>
</table>
</td>
</tr>
</tbody>
</table>

# 3. 조이스틱 또는 키보드를 사용한 제어

이 섹션에서는 조이스틱 또는 키보드 키를 사용하여 움직임을 제어하는 방법을 설명합니다. 제품은 공장 출하 시 Xbox 블루투스 컨트롤러와 함께 제공됩니다. 기본적으로 1장 [UGV Beast PI ROS2 1. 준비 과정](https://www.waveshare.com/wiki/UGV_Beast_PI_ROS2_1._Preparation)의 내용에 따라 메인 프로그램을 종료하고 도커 컨테이너에 원격으로 연결했다고 가정합니다.

## 목차

1.  [조이스틱 또는 키보드 제어 사용](#3.-조이스틱-또는-키보드-제어-사용)
    1.  [3.1 섀시 구동](#3.1-섀시-구동)
    2.  [3.2 조이스틱 제어](#3.2-조이스틱-제어)
    3.  [3.3 키보드 제어](#3.3-키보드-제어)

## 3.1 섀시 구동

조이스틱 제어 및 키보드 제어 데모를 실행하기 전에 먼저 섀시 구동 노드를 실행해야 합니다. 이전 섹션에서는 하나의 ROS2 로봇 구동 노드 작동을 소개했으며, 여기서는 다른 섀시 구동 노드 작동을 소개합니다.

컨테이너 내에서 해당 제품의 ROS 2 프로젝트 작업 공간으로 이동합니다:

```bash
cd /home/ws/ugv_ws
```

로봇 드라이버 노드를 시작합니다:

```bash
ros2 launch ugv_bringup bringup_lidar.launch.py use_rviz:=true
```

이 순간 로봇 팬틸트가 중앙 위치로 돌아가고 카메라가 앞을 향하게 되며, 제품의 RVIZ2 모델 인터페이스를 볼 수 있습니다. 로봇이 제자리에서 회전하면 모델도 로봇과 함께 회전하는 것을 볼 수 있습니다.

[![Beast rviz3.png](https://www.waveshare.com/w/upload/thumb/3/35/Beast_rviz3.png/1000px-Beast_rviz3.png)](https://www.waveshare.com/wiki/File:Beast_rviz3.png)

참고: 모델 인터페이스에 UGV Beast 추적형 섀시가 표시되지 않으면 먼저 Ctrl+C를 눌러 실행 중인 로봇 구동 노드를 꺼야 합니다. 다음으로 ROS 2 프로젝트의 UGV 모델을 UGV Beast로 전환하고, 다음 명령을 입력하여 모델을 전환한 다음 로봇 구동 노드를 시작합니다.

```bash
export UGV_MODEL=ugv_beast
source ~/.bashrc
```

## 3.2 조이스틱 제어

로봇 드라이버 노드를 시작하고 조이스틱 수신기를 라즈베리 파이에 연결합니다.

연결되면 먼저 새 도커 컨테이너 터미널에서 조이스틱 제어 노드를 실행해야 합니다. 새 도커 컨테이너 터미널을 열고 왼쪽 사이드바에서 "⭐" 기호를 클릭하고 도커의 원격 터미널을 더블 클릭하여 엽니다. 사용자 이름: `root`, 비밀번호: `ws`를 입력합니다.

[![ROS2 newDocker.png](https://www.waveshare.com/w/upload/thumb/b/bb/ROS2_newDocker.png/800px-ROS2_newDocker.png)](https://www.waveshare.com/wiki/File:ROS2_newDocker.png)

컨테이너 내에서 먼저 다음 명령을 실행하여 조이스틱이 인식되었는지 확인합니다. 그림과 같이 표시됩니다:

```bash
ls /dev/input
```

[![ROS2 xboxls.png](https://www.waveshare.com/w/upload/thumb/a/a8/ROS2_xboxls.png/800px-ROS2_xboxls.png)](https://www.waveshare.com/wiki/File:ROS2_xboxls.png)

여기서 `js0`는 조이스틱을 나타냅니다.

컨테이너 내에서 해당 제품의 ROS 2 프로젝트 작업 공간으로 이동합니다:

```bash
cd /home/ws/ugv_ws
```

조이스틱 제어 노드를 실행합니다:

```bash
ros2 launch ugv_tools teleop_twist_joy.launch.py
```

그런 다음 조이스틱 뒷면의 스위치를 켜면 조이스틱의 빨간색 표시등이 켜지면서 로봇의 움직임을 제어할 수 있습니다. 참고: 조이스틱에는 세 가지 기능 키가 있습니다: R 아래의 키는 잠금 또는 잠금 해제에 사용되며, 왼쪽 조이스틱은 전진 또는 후진, 오른쪽 조이스틱은 좌회전 또는 우회전입니다.

Ctrl+C를 눌러 조이스틱 제어 노드를 닫을 수 있습니다.

## 3.3 키보드 제어

조이스틱 제어 노드를 닫은 다음, 터미널 창에서 키보드 제어 노드를 실행합니다:

```bash
ros2 run ugv_tools keyboard_ctrl
```

이 창을 활성 상태로 유지하고(즉, 키를 조작할 때 터미널 창 인터페이스에 있는지 확인) 다음 키를 통해 로봇의 움직임을 제어합니다:

| 키보드 키 | 동작 설명    | 키보드 키 | 동작 설명 | 키보드 키 | 동작 설명    |
| :-------- | :----------- | :-------- | :-------- | :-------- | :----------- |
| **U**     | 좌측 전진    | **I**     | 직진      | **O**     | 우측 전진    |
| **J**     | 좌회전       | **K**     | 정지      | **L**     | 우회전       |
| **M**     | 좌측 후진    | **,**     | 직진 후진 | **.**     | 우측 후진    |

Ctrl+C를 눌러 키보드 제어 노드를 닫을 수 있습니다.
