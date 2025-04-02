
# UGV Beast PI ROS2 2. RViz 제품 모델 보기 - Waveshare Wiki

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

# 2. RViz 제품 모델 보기

기본적으로 1장 [UGV Beast PI ROS2 1. 준비 과정](https://www.waveshare.com/wiki/UGV_Beast_PI_ROS2_1._Preparation)의 내용에 따라 메인 프로그램을 종료하고 도커 컨테이너에 원격으로 연결했다고 가정합니다.

## 목차

1.  [RViz 제품 모델 보기](#2.-RViz-제품-모델-보기)
    1.  [2.1 모델 관절 보기](#2.1-모델-관절-보기)
    2.  [2.2 ROS2 로봇 드라이버 노드 실행](#2.2-ROS2-로봇-드라이버-노드-실행)
    3.  [2.3 로봇 라이트 제어](#2.3-로봇-라이트-제어)

## 2.1 모델 관절 보기

컨테이너 내에서 해당 제품의 ROS 2 프로젝트 작업 공간으로 이동합니다:

```bash
cd /home/ws/ugv_ws
```

RViz2 모델 인터페이스를 시작합니다:

```bash
ros2 launch ugv_description display.launch.py use_rviz:=true
```

이때는 제품의 RViz2 모델 인터페이스만 볼 수 있으며, 제어판의 슬라이더를 움직여 로봇의 움직임을 제어할 수는 없습니다. RViz2 모델의 터미널 인터페이스가 성공적으로 시작되면 인터페이스를 닫지 말고 다음 단계인 ROS2 로봇 드라이버 노드를 실행합니다.

## 2.2 ROS2 로봇 드라이버 노드 실행

새로운 도커 컨테이너 터미널을 열어야 합니다. 왼쪽 사이드바에서 "⭐" 기호를 클릭하고, 도커의 원격 터미널을 더블 클릭하여 엽니다. 사용자 이름: `root`, 비밀번호: `ws`를 입력합니다.

[![ROS2 newDocker.png](https://www.waveshare.com/w/upload/thumb/b/bb/ROS2_newDocker.png/800px-ROS2_newDocker.png)](https://www.waveshare.com/wiki/File:ROS2_newDocker.png)

컨테이너 내에서 해당 제품의 ROS 2 프로젝트 작업 공간으로 이동합니다:

```bash
cd /home/ws/ugv_ws
```

드라이버 로봇 노드를 실행합니다. 노드 실행이 완료된 후에는 정보 피드백이 없습니다:

```bash
ros2 run ugv_bringup ugv_driver
```

그런 다음 아래 그림의 제어판에서 슬라이더를 움직여 팬틸트 회전을 제어할 수 있으며, 모델과 실제 제품 모두 슬라이드에 따라 회전합니다.

*   `pt_base_link_to_pt_link1`: 팬틸트의 팬 서보 회전을 제어합니다.
*   `pt_link1_to_pt_link2`: 팬틸트의 틸트 서보 회전을 제어합니다.
*   `Center`: 이 버튼을 클릭하면 팬틸트가 중앙 위치로 돌아갑니다.

[![Beast rviz.png](https://www.waveshare.com/w/upload/thumb/1/19/Beast_rviz.png/800px-Beast_rviz.png)](https://www.waveshare.com/wiki/File:Beast_rviz.png)

## 2.3 로봇 라이트 제어

UGV 시리즈 제품의 경우, 드라이버 보드는 2 채널의 12V 스위치 제어 인터페이스를 통합합니다 (실제 최대 전압은 배터리 전압에 따라 변경됨). 이는 ESP32의 IO4 및 IO5 핀을 통해 MOS 튜브로 제어됩니다. 각 채널에는 두 개의 해당 인터페이스가 있어 총 4개의 12V 스위치 제어 인터페이스가 있습니다. 기본 조립 방법에 따라 IO4는 섀시 헤드라이트(OKA 카메라 옆의 라이트)를 제어하고 IO5는 헤드라이트(USB 카메라 팬틸트의 라이트)를 제어합니다. 해당 명령을 서브 컨트롤러로 전송하여 이 두 스위치의 전환을 제어하고 전압 레벨을 조정할 수 있습니다. 그러나 MOSFET 제어의 고유한 지연으로 인해 ESP32의 IO에서 출력되는 PWM과 실제 전압 출력 간에 선형 관계가 없을 수 있습니다.

LED가 없는 제품의 경우, 이 두 12V 스위치에 12.6V 내압 LED를 확장할 수 있습니다 (일반적으로 안전 및 배터리 보호를 위해 12V 내압도 허용되며, 제품의 UPS는 배터리를 12V 이상으로 충전하지 않음). 나머지 스위치 제어 인터페이스에 12V 내압 물총 기어박스와 같은 다른 주변 장치를 확장하여 IO5로 제어되는 인터페이스에 직접 연결하여 자동 조준 및 발사 기능을 구현할 수도 있습니다.

제어 노드를 실행할 때마다 새로운 도커 컨테이너 터미널을 열어야 합니다. 왼쪽 사이드바에서 ⭐ 기호를 클릭하고, 도커의 원격 터미널을 더블 클릭하여 엽니다. 사용자 이름: `root`, 비밀번호: `ws`를 입력합니다.

컨테이너 내에서 해당 제품의 ROS 2 프로젝트 작업 공간으로 이동합니다:

```bash
cd /home/ws/ugv_ws
```

라이트 제어 노드를 실행하면 로봇의 세 LED 라이트가 켜지는 것을 볼 수 있습니다:

```bash
ros2 topic pub /ugv/led_ctrl std_msgs/msg/Float32MultiArray "{data: [255, 255]}" -1
```

`data: [0, 0]`——첫 번째 0은 IO4 인터페이스(섀시 헤드라이트)를 제어하는 스위치입니다. 두 번째 0은 IO5 인터페이스(헤드라이트)를 제어하는 스위치입니다.

매개변수 변수 범위는 0-255입니다. 이 변수 값이 0이면 IO4 및 IO5로 제어되는 인터페이스 스위치가 꺼집니다. 이 변수가 255이면 IO4 및 IO5로 제어되는 인터페이스 스위치에서 출력되는 전압이 UPS의 BAT 전압(직렬로 연결된 3개의 리튬 배터리의 현재 UPS 전압)에 가까워집니다.

LED 라이트를 다시 끄는 명령을 실행하면 세 LED 라이트가 모두 꺼지는 것을 볼 수 있습니다:

```bash
ros2 topic pub /ugv/led_ctrl std_msgs/msg/Float32MultiArray "{data: [0, 0]}" -1
```

이 튜토리얼 섹션에서는 제품 모델 관절 보기, 로봇 드라이브 노드 실행 및 로봇 라이트 제어 방법을 보여주었습니다. 다음 튜토리얼을 따라 다른 ROS 2 제어에 대해 알아보십시오.
