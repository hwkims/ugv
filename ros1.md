
# UGV Beast PI ROS2 1. 준비 과정 - Waveshare Wiki

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

# 1. 준비 과정

제품은 전원을 켤 때 기본적으로 라즈베리파이 메인 프로그램을 자동으로 실행합니다. 이 메인 프로그램은 시리얼 포트와 카메라를 점유하게 됩니다. 이 경우 ROS 2를 사용할 수 없습니다. 따라서 메인 프로그램을 종료하거나 메인 프로그램의 자동 실행을 비활성화해야 합니다. ROS 2 기능 패키지는 모두 라즈베리파이 시스템의 도커 컨테이너 안에서 실행되므로, 라즈베리파이의 메인 프로그램을 종료한 후에는 도커 원격 서비스를 시작해야 원격으로 도커 컨테이너에 로그인하여 ROS 2 기능 패키지를 실행할 수 있습니다.

## 목차

1.  [준비 과정](#1.-준비-과정)
    1.  [1.1 메인 프로그램 종료하기](#1.1-메인-프로그램-종료하기)
    2.  [1.2 메인 프로그램 자동 실행 비활성화하기](#1.2-메인-프로그램-자동-실행-비활성화하기)
    3.  [1.3 도커 원격 서비스 시작하기](#1.3-도커-원격-서비스-시작하기)
    4.  [1.4 도커 컨테이너 원격 로그인하기](#1.4-도커-컨테이너-원격-로그인하기)

## 1.1 메인 프로그램 종료하기

터미널에서 현재 시스템에서 실행 중인 작업 및 프로세스 정보를 실시간으로 표시합니다:

```bash
top
```

몇 초 기다리면 `COMMAND`가 `python`인 프로세스의 `PID`를 볼 수 있습니다.

[![ROS2 top.png](https://www.waveshare.com/w/upload/thumb/f/f3/ROS2_top.png/600px-ROS2_top.png)](https://www.waveshare.com/wiki/File:ROS2_top.png)

`Ctrl+C`를 눌러 보기를 종료한 다음, 프로세스를 종료하는 명령어를 입력합니다.

```bash
Kill -9 <Python 프로세스 PID>
```

예시: 위 그림과 같이 `kill -9 850`을 입력합니다. 이렇게 하면 해당 제품의 메인 라즈베리파이 프로그램 실행이 종료됩니다. **참고:** 메인 프로그램 실행을 종료한 후에는 라즈베리파이 IP 주소:5000으로 성공적으로 접속할 수 없습니다. 하지만 제품을 재시작하면 메인 프로그램은 여전히 자동으로 실행됩니다. 만약 전원을 다시 켰을 때 제품이 메인 프로그램을 자동으로 실행하지 않도록 하려면, 다음 섹션 [1.2 메인 프로그램 자동 실행 비활성화하기](#1.2-메인-프로그램-자동-실행-비활성화하기)의 내용에 따르십시오.

## 1.2 메인 프로그램 자동 실행 비활성화하기

제품을 재시작할 때마다 기본적으로 메인 프로그램을 자동으로 실행합니다. 부팅 시 제품의 메인 프로그램이 자동으로 실행되는 것을 직접 금지하려면, `crontab`에 설정된 메인 프로그램 자동 실행 설정을 취소해야 합니다. 터미널에 다음 명령어를 입력합니다:

```bash
crontab -e
```

어떤 편집기를 사용할지 묻는 메시지가 나오면, `1`을 입력하고 Enter 키를 눌러 nano를 선택합니다.

`crontab` 설정 파일을 열면 다음 두 줄을 볼 수 있습니다:

```cron
@reboot ~/ugv_pt_rpi/ugv-env/bin/python ~/ugv_pt_rpi/app.py >> ~/ugv.log 2>&1
@reboot /bin/bash ~/ugv_pt_rpi/start_jupyter.sh >> ~/jupyter_log.log 2>&1
```

"...app.py >> ...." 줄 시작 부분에 `#` 기호를 추가하여 이 줄을 주석 처리합니다. 다음과 같이 변경합니다:

```cron
#@reboot ~/ugv_pt_rpi/ugv-env/bin/python ~/ugv_pt_rpi/app.py >> ~/ugv.log 2>&1
@reboot /bin/bash ~/ugv_pt_rpi/start_jupyter.sh >> ~/jupyter_log.log 2>&1
```

터미널 페이지에서 `Ctrl + X`를 눌러 종료합니다. `Save modified buffer?` (수정된 버퍼를 저장하시겠습니까?) 라고 물으면 "Y"를 입력하고 Enter 키를 눌러 변경 사항을 저장합니다.

재시작 명령어를 입력하여 장치를 재시작합니다 (재시작 과정 중 라즈베리파이의 녹색 LED가 깜박입니다. 녹색 LED 깜박임이 줄어들거나 꺼지면 부팅이 성공적으로 완료된 것입니다):

```bash
sudo reboot
```

이전 단계에서 "...start_jupyter.sh >>..." 줄을 주석 처리하지 않았다면, 로봇이 재시작된 후에도 Jupyter Lab을 정상적으로 사용할 수 있습니다 (JupyterLab과 로봇의 메인 프로그램 app.py는 서로 독립적으로 실행됩니다).

**주의:** 하위 장치가 상위 장치와 시리얼 포트를 통해 계속 통신하기 때문에, 재시작 과정 중 시리얼 포트 레벨이 계속 변경되어 상위 장치가 정상적으로 부팅되지 못할 수 있습니다. 호스트 장치가 라즈베리파이인 경우를 예로 들면, 재시작 시 라즈베리파이가 종료된 후 다시 켜지지 않는 경우가 발생할 수 있습니다. 빨간색 LED는 계속 켜져 있고 녹색 LED는 켜지지 않는 상태입니다. 이때는 로봇의 전원 스위치를 껐다가 다시 켜면 로봇이 정상적으로 재시작됩니다.

## 1.3 도커 원격 서비스 시작하기

라즈베리파이의 `ugv_ws` 프로젝트 디렉토리로 이동하여 `ros2_humble.sh` 및 `remotessh.sh` 파일에 실행 권한을 부여합니다:

```bash
cd /home/ws/ugv_ws
sudo chmod +x ros2_humble.sh remotessh.sh
```

스크립트 파일 `ros2_humble.sh`를 실행하여 도커 원격 서비스를 시작합니다:

```bash
./ros2_humble.sh
```

`1`을 입력하여 도커 컨테이너에 들어가 SSH 서비스를 시작합니다.

[![ROS2 Dockerstart.png](https://www.waveshare.com/w/upload/thumb/9/9c/ROS2_Dockerstart.png/800px-ROS2_Dockerstart.png)](https://www.waveshare.com/wiki/File:ROS2_Dockerstart.png)

## 1.4 도커 컨테이너 원격 로그인하기

도커 컨테이너가 성공적으로 SSH 서비스를 시작한 후, [MobaXterm](https://files.waveshare.com/wiki/UGV%20Rover%20PT%20ROS2/MobaXterm_Portable_v22.0.zip)을 사용하여 도커 컨테이너에 원격으로 로그인합니다.

`Session` → `SSH`를 클릭합니다. 호스트 IP는 도커 컨테이너 IP입니다. `Remote host`에 라즈베리파이의 IP 주소를 입력하고, `Port`는 할당된 포트 `23`을 입력한 후 OK를 클릭합니다.

[![ROS2 DockerSSH.png](https://www.waveshare.com/w/upload/thumb/d/d0/ROS2_DockerSSH.png/600px-ROS2_DockerSSH.png)](https://www.waveshare.com/wiki/File:ROS2_DockerSSH.png)

연결이 설정된 후, 사용자 이름: `root`와 비밀번호: `ws`를 입력합니다. **참고:** 비밀번호를 입력할 때 화면에 아무것도 표시되지 않는 것이 정상입니다. 비밀번호 입력 후 Enter 키를 누르면 도커 컨테이너에 접속됩니다. 이로써 도커 컨테이너에 대한 SSH 원격 연결이 성공적으로 완료되었습니다.
