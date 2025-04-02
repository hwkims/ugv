# UGV Beast ROS 2 오픈소스 오프로드 추적형 AI 로봇, 듀얼 컨트롤러, 컴퓨터 비전, 전체 금속 바디, 유연하고 확장 가능, Raspberry Pi 4B / Raspberry Pi 5에 적합

## 제품 개요

UGV Beast ROS 2 오픈소스 오프로드 추적형 AI 로봇, 듀얼 컨트롤러, 컴퓨터 비전, 전체 금속 바디, 유연하고 확장 가능, Raspberry Pi 4B / Raspberry Pi 5에 적합

## 초보자 선택 추천

호스트 컨트롤러로 <span style="color: #ce224e;">Raspberry Pi</span>를 사용하려면 [UGV Rover PT PI5 ROS2 Kit](https://www.waveshare.com/ugv-rover-ros2-kit.htm?sku=28847)를 구매하는 것이 좋으며, <span style="color: #458362;">NVIDIA Jetson Orin Nano</span>를 호스트 컨트롤러로 사용하려면 [UGV Rover PT Jetson Orin ROS2 Kit](https://www.waveshare.com/ugv-rover-pt-jetson-orin-ros2-kit.htm?sku=29224)를 구매하는 것이 좋습니다.

두 키트 모두 뛰어난 신뢰성을 제공하며, 고토크 2축 팬틸트, D500 Lidar, OAK-D Lite 뎁스 카메라를 갖추고 있습니다. 초보자가 로봇 공학 지식을 빠르게 배우고 적용할 수 있도록 포괄적인 기본 기능과 ROS2 튜토리얼을 제공합니다. 로봇 키트는 우수한 확장성을 제공하여 사용자가 다양한 애플리케이션을 배포할 수 있습니다.

## 제품 모델명 소개

제품 모델명에는 <span style="color: #d9730f;">섀시 유형</span>, <span style="color: #458362;">팬틸트 옵션</span>, <span style="color: #347ea9;">호스트 컨트롤러 모델</span>, <span style="color: #9065b0;">기능 유형</span>이 포함됩니다.

| 구분             | 모델명                                                                                                                                              | 설명                                                                                                                                                                                                 | 해당 모듈                                                                                                 |
| :--------------- | :-------------------------------------------------------------------------------------------------------------------------------------------------- | :--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :-------------------------------------------------------------------------------------------------------- |
| **섀시 유형**    | <span style="color: #d9730f;">UGV Rover</span>                                                                                                      | 6륜 4WD 섀시                                                                                                                                                                                         | ![UGV Rover](https://www.waveshare.com/img/devkit/accBoard/UGV-Product-Selection-Table/UGV%20Rover.jpg)    |
|                  | <span style="color: #d9730f;">UGV Beast</span>                                                                                                      | 독립 서스펜션 오프로드 추적형 섀시                                                                                                                                                                     | ![UGV Beast](https://www.waveshare.com/img/devkit/accBoard/UGV-Product-Selection-Table/UGV%20Beast.jpg)    |
| **팬틸트 옵션**  | <span style="color: #458362;">PT</span>                                                                                                            | 2축 팬틸트 포함                                                                                                                                                                                      | ![PT](https://www.waveshare.com/img/devkit/accBoard/UGV-Product-Selection-Table/PT.jpg)                   |
| **호스트 컨트롤러** | <a href="https://www.waveshare.com/jetson-orin-nano.htm?sku=24432" target="_blank" style="color: #347ea9; text-decoration: underline;">Jetson Orin</a> | **Jetson Orin Nano**를 호스트 컨트롤러로 사용.<br><span style="color: #ababab;">참고: 모델명 끝에 "Acce"가 붙은 키트에는 호스트 컨트롤러가 포함되지 않으며, 사용자가 Jetson Orin 보드를 직접 준비해야 합니다.</span> | ![Jetson Orin](https://www.waveshare.com/img/devkit/accBoard/UGV-Product-Selection-Table/Jetson%20Orin.jpg) |
|                  | <a href="https://www.waveshare.com/raspberry-pi-5.htm?sku=25837" target="_blank" style="color: #347ea9; text-decoration: underline;">PI 5</a>        | **Raspberry Pi 5**를 호스트 컨트롤러로 사용.<br><span style="color: #ababab;">참고: 모델명 끝에 "Acce"가 붙은 키트에는 호스트 컨트롤러가 포함되지 않으며, 사용자가 Raspberry Pi 5와 방열판을 직접 준비해야 합니다.</span> | ![PI5](https://www.waveshare.com/img/devkit/accBoard/UGV-Product-Selection-Table/PI5.jpg)                 |
|                  | <a href="https://www.waveshare.com/raspberry-pi-4-model-b-4gb-ram.htm" target="_blank" style="color: #347ea9; text-decoration: underline;">PI 4B</a>     | **Raspberry Pi 4B**를 호스트 컨트롤러로 사용.<br><span style="color: #ababab;">참고: 모델명 끝에 "Acce"가 붙은 키트에는 호스트 컨트롤러가 포함되지 않으며, 사용자가 Raspberry Pi 4B와 방열판을 직접 준비해야 합니다.</span> | ![PI4B](https://www.waveshare.com/img/devkit/accBoard/UGV-Product-Selection-Table/PI4B.jpg)               |
|                  | <span style="color: #347ea9;">Acce</span>                                                                                                           | 모델명 끝에 "Acce"가 붙은 키트에는 호스트 컨트롤러가 포함되지 않습니다. 호스트 보드가 있다면 Acce 버전을 선택할 수 있습니다.                                                                                   | ![Acce](https://www.waveshare.com/img/devkit/accBoard/UGV-Product-Selection-Table/Acce.jpg)               |
| **기능 유형**    | <span style="color: #9065b0;">AI Kit</span>                                                                                                        | 5MP 초광각 카메라가 포함된 기본 AI 키트, 컴퓨터 비전 기능 및 튜토리얼 제공.                                                                                                                             | ![AI Kit](https://www.waveshare.com/img/devkit/accBoard/UGV-Product-Selection-Table/AI%20Kit.jpg)         |
|                  | <span style="color: #9065b0;">ROS2 Kit</span>                                                                                                       | AI 키트를 기반으로 D500 360° Lidar와 OAK-D Lite 뎁스 카메라 장착, 완전한 ROS2 기능 및 튜토리얼 제공.                                                                                                  | ![ROS2 Kit](https://www.waveshare.com/img/devkit/accBoard/UGV-Product-Selection-Table/ROS2%20Kit.jpg)     |

---

## 제품 이미지

![UGV Beast ROS 2 Kit](https://www.waveshare.com/media/catalog/product/cache/1/image/800x800/9df78eab33525d08d6e5fb8d27136e95/u/g/ugv-beast-pt-pi4b-ros2-kit-1.jpg)

*다른 이미지들:*
*   ![Image 2](https://www.waveshare.com/media/catalog/product/cache/1/thumbnail/122x122/9df78eab33525d08d6e5fb8d27136e95/u/g/ugv-beast-pt-pi4b-ros2-kit-2.jpg)
*   ![Image 3](https://www.waveshare.com/media/catalog/product/cache/1/thumbnail/122x122/9df78eab33525d08d6e5fb8d27136e95/u/g/ugv-beast-pt-pi4b-ros2-kit-3.jpg)
*   ![Image 4](https://www.waveshare.com/media/catalog/product/cache/1/thumbnail/122x122/9df78eab33525d08d6e5fb8d27136e95/u/g/ugv-beast-pt-pi4b-ros2-kit-4.jpg)
*   ![Image 5](https://www.waveshare.com/media/catalog/product/cache/1/thumbnail/122x122/9df78eab33525d08d6e5fb8d27136e95/u/g/ugv-beast-pt-pi4b-ros2-kit-5.jpg)

---

## 제품 정보

*   **카테고리:** [Raspberry Pi 4](https://www.waveshare.com/product/raspberry-pi/boards-kits/raspberry-pi-4.htm), [Mobile Robots](https://www.waveshare.com/product/raspberry-pi/robots/mobile-robots.htm), [Mobile Robots (AI)](https://www.waveshare.com/product/ai/robots/mobile-robots.htm), [Raspberry Pi Robots](https://www.waveshare.com/product/robotics/mobile-robots/raspberry-pi-robots.htm), [Raspberry Pi 5](https://www.waveshare.com/product/raspberry-pi/boards-kits/raspberry-pi-5.htm)
*   **제품명:** UGV Beast ROS 2 오픈소스 오프로드 추적형 AI 로봇, 듀얼 컨트롤러, 컴퓨터 비전, 전체 금속 바디, 유연하고 확장 가능, Raspberry Pi 4B / Raspberry Pi 5에 적합
*   **가격:** $559.99 - $617.99
*   [장바구니에 추가 버튼]
*   **옵션 선택:** (주문 전 아래 필수 옵션을 모두 선택하세요.)
    *   **키트 선택:**
        *   UGV Beast PI4B ROS2 Kit
        *   UGV Beast PI5 ROS2 Kit
    *   **Raspberry Pi 선택:**
        *   포함
        *   미포함
    *   **팬틸트 모듈:**
        *   포함
    *   **전원 플러그:**
        *   EU
        *   UK
        *   US

---

## 상세 설명

### 개요

**UGV Beast ROS2 Kit**는 ROS 2를 기반으로 하며 Lidar와 뎁스 카메라를 갖춘, 뛰어난 확장 잠재력을 가진 탐험 및 창작용 AI 로봇입니다. 상상력과 현실을 매끄럽게 연결합니다. 기술 애호가, 메이커 또는 프로그래밍 초보자에게 적합하며, 지능형 기술의 세계를 탐험하기 위한 이상적인 선택입니다.

고성능 Raspberry Pi 컴퓨터를 장착하여 복잡한 전략과 기능의 도전을 처리하고 창의력을 발휘하도록 영감을 줍니다. 듀얼 컨트롤러 설계를 채택하여 호스트 컨트롤러의 고수준 AI 기능과 서브 컨트롤러의 고빈도 기본 작업을 결합하여 모든 작업을 정확하고 부드럽게 만듭니다.

소프트웨어를 다운로드할 필요 없이 UGV Beast 웹 애플리케이션을 통해 원격으로 쉽게 제어할 수 있습니다. 브라우저를 열고 여정을 시작하기만 하면 됩니다. PC에 가상 머신을 설치하지 않고도 로봇의 기본 ROS 2 기능을 사용할 수 있습니다. 고프레임 속도 실시간 비디오 전송과 다양한 AI 컴퓨터 비전 기능을 지원하는 UGV Beast는 아이디어와 창의성을 실현하기 위한 이상적인 플랫폼입니다!

![UGV Beast 사용 시나리오](https://www.waveshare.com/img/devkit/accBoard/UGV-Beast-PT-PI4B-ROS2-Kit/UGV-Beast-PT-PI4B-ROS2-Kit-details-1.jpg)
![UGV Beast AI 로봇 특징](https://www.waveshare.com/img/devkit/accBoard/UGV-Beast-PT-PI4B-ROS2-Kit/UGV-Beast-PT-PI4B-ROS2-Kit-details-3.jpg)

---

### 주요 특징

*   **UGV Beast ROS2 Kit**는 ROS 2 기반의 AI 로봇으로, Lidar와 뎁스 카메라를 장착하여 탐험과 창작을 위해 설계되었으며 뛰어난 확장 잠재력을 가집니다. 기술 애호가, 메이커, 프로그래밍 초보자에게 적합하며 지능형 기술 세계를 탐험하는 데 이상적인 선택입니다.
*   고성능 Raspberry Pi 컴퓨터를 장착하여 복잡한 전략과 기능 과제를 처리하고 창의력을 고취시킵니다.
*   듀얼 컨트롤러 설계를 채택하여 호스트 컨트롤러의 고수준 AI 기능과 서브 컨트롤러의 고주파 기본 작동을 결합하여 모든 작업을 정확하고 부드럽게 만듭니다.
*   소프트웨어를 다운로드할 필요 없이 UGV Beast 웹 애플리케이션을 통해 원격으로 쉽게 제어할 수 있습니다. 브라우저를 열기만 하면 여정을 시작할 수 있습니다.
*   PC에 가상 머신을 설치하지 않고도 로봇의 기본 ROS 2 기능을 사용할 수 있습니다.
*   고프레임률 실시간 비디오 전송과 다양한 AI 컴퓨터 비전 기능을 지원하여 아이디어와 창의성을 실현하기 위한 이상적인 플랫폼입니다!

---

### 키트 선택

*   더 나은 확장 잠재력을 위한 팬틸트 모듈 옵션(PT 버전만 해당).
*   호스트 컨트롤러 옵션(Raspberry Pi 4B / Raspberry Pi 5), 또는 Pi가 있다면 Acce 버전을 선택할 수 있습니다.
*   모든 키트에는 카메라, 마운팅 액세서리, TF 카드, 냉각 팬 등이 포함되어 있습니다.

| 특징                 | UGV Beast PT PI4B/PI5 ROS2 Kit                                                                    | UGV Beast PT PI4B/PI5 ROS2 Kit Acce                                                                 | UGV Beast PI4B/PI5 ROS2 Kit                                                                     | UGV Beast PI4B/PI5 ROS2 Kit Acce                                                                  |
| :------------------- | :------------------------------------------------------------------------------------------------ | :-------------------------------------------------------------------------------------------------- | :---------------------------------------------------------------------------------------------- | :------------------------------------------------------------------------------------------------ |
| **모델 이미지**        | ![UGV Beast PT PI4B/PI5 ROS2 Kit](https://www.waveshare.com/img/devkit/accBoard/UGV-Beast-PT-PI4B-ROS2-Kit/UGV-Beast-PT-PI4B-ROS2-Kit-details-7-1.jpg) | ![UGV Beast PT PI4B/PI5 ROS2 Kit Acce](https://www.waveshare.com/img/devkit/accBoard/UGV-Beast-PT-PI4B-ROS2-Kit/UGV-Beast-PT-PI4B-ROS2-Kit-details-7-2.jpg) | ![UGV Beast PI4B/PI5 ROS2 Kit](https://www.waveshare.com/img/devkit/accBoard/UGV-Beast-PT-PI4B-ROS2-Kit/UGV-Beast-PI4B-ROS2-Kit-details-7-3.jpg) | ![UGV Beast PI4B/PI5 ROS2 Kit Acce](https://www.waveshare.com/img/devkit/accBoard/UGV-Beast-PT-PI4B-ROS2-Kit/UGV-Beast-PI4B-ROS2-Kit-details-7-4.jpg) |
| **크기**             | 196.82×231.46×251.78mm                                                                             | 196.82×231.46×251.78mm                                                                              | 196.82×231.46×152.25mm                                                                          | 196.82×231.46×152.25mm                                                                            |
| **무게**             | 2411 ±5g                                                                                          | 2411 ±5g                                                                                            | 2095 ±5g                                                                                        | 2095 ±5g                                                                                          |
| **섀시 높이**        | 25mm                                                                                              | 25mm                                                                                                | 25mm                                                                                            | 25mm                                                                                              |
| **팬틸트 자유도**      | 2                                                                                                 | 2                                                                                                   | -                                                                                               | -                                                                                                 |
| **팬틸트 서보 토크**   | 30KG.CM                                                                                           | 30KG.CM                                                                                             | -                                                                                               | -                                                                                                 |
| **팬틸트 서보**      | ST3215 서보                                                                                       | ST3215 서보                                                                                         | -                                                                                               | -                                                                                                 |
| **호스트 컨트롤러**    | RPi 4B 4GB / RPi 5 4GB                                                                            | 미포함                                                                                                | RPi 4B 4GB / RPi 5 4GB                                                                          | 미포함                                                                                              |
| **호스트 시스템 지원** | Debian Bookwrom                                                                                   | Debian Bookwrom                                                                                     | Debian Bookwrom                                                                                 | Debian Bookwrom                                                                                   |
| **ROS2 버전**        | ROS2-HUMBLE-LTS                                                                                   | ROS2-HUMBLE-LTS                                                                                     | ROS2-HUMBLE-LTS                                                                                 | ROS2-HUMBLE-LTS                                                                                   |
| **카메라 FOV**       | 160°                                                                                              | 160°                                                                                                | 160°                                                                                            | 160°                                                                                              |
| **전원 공급**        | 3S UPS 모듈                                                                                       | 3S UPS 모듈                                                                                         | 3S UPS 모듈                                                                                     | 3S UPS 모듈                                                                                       |
| **배터리 지원**      | 18650 리튬 배터리 x 3 (미포함)                                                                        | 18650 리튬 배터리 x 3 (미포함)                                                                        | 18650 리튬 배터리 x 3 (미포함)                                                                    | 18650 리튬 배터리 x 3 (미포함)                                                                      |
| **데모 제어 방법**     | 웹 애플리케이션 / Jupyter Lab 대화형 프로그래밍                                                       | 웹 애플리케이션 / Jupyter Lab 대화형 프로그래밍                                                         | 웹 애플리케이션 / Jupyter Lab 대화형 프로그래밍                                                     | 웹 애플리케이션 / Jupyter Lab 대화형 프로그래밍                                                     |
| **기본 최대 속도**   | 0.35m/s                                                                                           | 0.35m/s                                                                                             | 0.35m/s                                                                                         | 0.35m/s                                                                                           |
| **구동 휠 수**       | 2                                                                                                 | 2                                                                                                   | 2                                                                                               | 2                                                                                                 |
| **서스펜션 재질**    | 스테인리스 스틸                                                                                     | 스테인리스 스틸                                                                                       | 스테인리스 스틸                                                                                   | 스테인리스 스틸                                                                                   |
| **트랙 폭**          | 40mm                                                                                              | 40mm                                                                                                | 40mm                                                                                            | 40mm                                                                                              |
| **최소 회전 반경**   | 0M (제자리 회전)                                                                                    | 0M (제자리 회전)                                                                                      | 0M (제자리 회전)                                                                                  | 0M (제자리 회전)                                                                                    |

---

### Raspberry Pi 기반

Raspberry Pi 5 / Raspberry Pi 4B를 지원하며, 강력한 컴퓨팅 성능으로 더 복잡한 작업을 처리하고 더 많은 가능성을 제공합니다.

![Raspberry Pi 4B 연결](https://www.waveshare.com/img/devkit/accBoard/UGV-Beast-PT-PI4B-ROS2-Kit/UGV-Beast-PT-PI4B-ROS2-Kit-details-9-1.jpg)
**Raspberry Pi 4B 연결**

![Raspberry Pi 5 연결](https://www.waveshare.com/img/devkit/accBoard/UGV-Beast-PT-PI4B-ROS2-Kit/UGV-Beast-PT-PI4B-ROS2-Kit-details-9-2.jpg)
**Raspberry Pi 5 연결**

---

### 듀얼 컨트롤러 설계, 효율적인 협업과 업그레이드된 성능 제공

호스트 컨트롤러는 AI 비전 및 전략 계획을 위해 Raspberry Pi를 채택하고, 서브 컨트롤러는 모션 제어 및 센서 데이터 처리를 위해 ESP32를 사용합니다.

![듀얼 컨트롤러 설계](https://www.waveshare.com/img/devkit/accBoard/UGV-Beast-PT-PI4B-ROS2-Kit/UGV-Beast-PT-PI4B-ROS2-Kit-details-11.jpg)

---

### Raspberry Pi OS + ROS2 Docker

로봇의 고급 의사 결정 성능과 시스템 호환성을 동시에 보장합니다. 이전 AI Kit 시리즈 제품의 모든 AI 기능을 지원합니다.

![Raspberry Pi OS + ROS2 Docker](https://www.waveshare.com/img/devkit/accBoard/UGV-Beast-PT-PI4B-ROS2-Kit/UGV-Beast-PT-PI4B-ROS2-Kit-details-13.jpg)

---

### 360° 유연한 전방향 팬틸트

5MP 160° 광각 카메라를 장착하여 모든 세부 사항을 캡처합니다.

![전방향 팬틸트](https://www.waveshare.com/img/devkit/accBoard/UGV-Beast-PT-PI4B-ROS2-Kit/UGV-Beast-PT-PI4B-ROS2-Kit-details-17.jpg)

---

### 모든 ROS 2 개발 리소스 오픈 소스 제공

로봇 설명 파일(URDF 모델), 서브 컨트롤러의 센서 데이터 처리 노드, 운동학적 제어 알고리즘, 다양한 원격 제어 노드를 포함한 호스트 컨트롤러 및 서브 컨트롤러의 모든 데모를 오픈 소스로 제공합니다.

![오픈 소스 ROS2 리소스](https://www.waveshare.com/img/devkit/accBoard/UGV-Beast-PT-PI4B-ROS2-Kit/UGV-Beast-PT-PI4B-ROS2-Kit-details-19.jpg)

---

### 다양한 ROS 2 매핑 방법 통합

다양한 시나리오의 매핑 요구를 충족합니다.

![Gmapping 2D 매핑](https://www.waveshare.com/img/devkit/accBoard/UGV-Beast-PT-PI4B-ROS2-Kit/UGV-Beast-PT-PI4B-ROS2-Kit-details-21-1.jpg)
*Gmapping 2D 매핑*

![Cartographer 2D 매핑](https://www.waveshare.com/img/devkit/accBoard/UGV-Beast-PT-PI4B-ROS2-Kit/UGV-Beast-PT-PI4B-ROS2-Kit-details-21-2.jpg)
*Cartographer 2D 매핑*

![RTAB-Map 3D 매핑](https://www.waveshare.com/img/devkit/accBoard/UGV-Beast-PT-PI4B-ROS2-Kit/UGV-Beast-PT-PI4B-ROS2-Kit-details-21-3.jpg)
*RTAB-Map 3D 매핑*

---

### 다중 비용 효율적인 센서 채택

높은 비용 효율성과 실용성을 갖춘 여러 센서를 채택합니다.

![다중 센서 채택](https://www.waveshare.com/img/devkit/accBoard/UGV-Beast-PT-PI4B-ROS2-Kit/UGV-Beast-PT-PI4B-ROS2-Kit-details-23.jpg)

---

### 다중 내비게이션 모드

다양한 시나리오에서 로봇의 자율 내비게이션 요구를 충족합니다.

![다중 내비게이션 모드](https://www.waveshare.com/img/devkit/accBoard/UGV-Beast-PT-PI4B-ROS2-Kit/UGV-Beast-PT-PI4B-ROS2-Kit-details-25.jpg)

---

### 자동 탐색 및 매핑

SLAM Toolbox를 사용하여 알 수 없는 환경에서 매핑 및 내비게이션 기능을 동시에 구현하여 작업 실행 프로세스를 단순화합니다. UGV 로봇은 알 수 없는 영역을 자율적으로 탐색하고 매핑을 완료할 수 있어 무인 애플리케이션에 적합합니다.

![자동 탐색 및 매핑 지원](https://www.waveshare.com/img/devkit/accBoard/UGV-Beast-PT-PI4B-ROS2-Kit/UGV-Beast-PT-PI4B-ROS2-Kit-details-27.jpg)

---

### 자연어 상호작용 지원

대규모 언어 모델(LLM) 기술을 채택하여 사용자는 자연어로 로봇에게 명령을 내릴 수 있으며, 이를 통해 이동, 매핑, 내비게이션과 같은 작업을 수행할 수 있습니다.

![자연어 상호작용 지원](https://www.waveshare.com/img/devkit/accBoard/UGV-Beast-PT-PI4B-ROS2-Kit/UGV-Beast-PT-PI4B-ROS2-Kit-details-29.jpg)

---

### 웹 콘솔 도구 제공

PC에 가상 머신을 설치하지 않고도 웹에서 기본 ROS 2 기능을 사용할 수 있으며, Android 또는 iOS 태블릿에서 크로스 플랫폼 작동을 지원합니다. 사용자는 브라우저를 열고 로봇을 제어하여 이동, 매핑, 내비게이션 및 기타 작업을 수행할 수 있습니다.

![웹 콘솔 도구](https://www.waveshare.com/img/devkit/accBoard/UGV-Beast-PT-PI4B-ROS2-Kit/UGV-Beast-PT-PI4B-ROS2-Kit-details-31.jpg)

---

### ROS2 노드 명령 상호작용

사용자는 스크립트를 통해 로봇에 제어 명령을 보내 이동, 현재 위치 얻기, 특정 지점으로 내비게이션 등의 작업을 수행할 수 있어 2차 개발에 더 편리합니다.

![ROS2 노드 명령 상호작용 데모](https://www.waveshare.com/img/devkit/accBoard/UGV-Beast-PT-PI4B-ROS2-Kit/UGV-Beast-PT-PI4B-ROS2-Kit-details-33-1.jpg)
![ROS2 노드 이동 데모](https://www.waveshare.com/img/devkit/accBoard/UGV-Beast-PT-PI4B-ROS2-Kit/UGV-Beast-PT-PI4B-ROS2-Kit-details-33-2.jpg)

---

### Gazebo 시뮬레이션 디버깅

시뮬레이션 디버깅을 위한 Gazebo 로봇 모드와 완전한 기능 라이브러리를 제공하여 개발 초기 단계에서 시스템을 검증하고 테스트하는 데 도움을 줍니다.

![Gazebo 로봇 모드 제공](https://www.waveshare.com/img/devkit/accBoard/UGV-Beast-PT-PI4B-ROS2-Kit/UGV-Beast-PT-PI4B-ROS2-Kit-details-35.jpg)

---

### 밤에도 모험은 계속, 전술적 확장 지원

*   **고휘도 LED 라이트:** 저조도 조건에서도 선명한 이미지를 보장합니다.
    ![저조도 조건 작동 데모](https://www.waveshare.com/img/devkit/accBoard/UGV-Beast-PT-PI4B-ROS2-Kit/UGV-Beast-PT-PI4B-ROS2-Kit-details-39.jpg)
*   **전술적 확장:** 21mm 와이드 레일과 30KG.CM 고정밀 & 고토크 버스 서보가 함께 제공되어 전술적 확장이 가능합니다.
    ![전술적 확장 지원](https://www.waveshare.com/img/devkit/accBoard/UGV-Beast-PT-PI4B-ROS2-Kit/UGV-Beast-PT-PI4B-ROS2-Kit-details-37.jpg)
    *(참고용이며, 위 사진의 액세서리는 포함되어 있지 않습니다.)*

---

### 표준 알루미늄 레일

2 × 1020 유럽 표준 프로파일 레일이 함께 제공되며, 보트 너트를 통해 추가 주변 장치를 설치하여 다양한 요구를 충족하고 특수 작업 시나리오를 쉽게 확장할 수 있습니다.

![추가 주변 장치 설치용 표준 알루미늄 레일](https://www.waveshare.com/img/devkit/accBoard/UGV-Beast-PT-PI4B-ROS2-Kit/UGV-Beast-PT-PI4B-ROS2-Kit-details-41.jpg)
*(참고: 레일, 보트 너트, M4 나사만 포함되며, 다른 액세서리는 별도로 구매해야 합니다.)*

---

### 복잡한 지형 주행 지원

독립 서스펜션 시스템을 갖춘 추적형 모바일 로봇 섀시를 채택하여 더 안정적인 오프로드 횡단 능력을 제공합니다.

![복잡한 지형 주행 지원](https://www.waveshare.com/img/devkit/accBoard/UGV-Beast-PT-PI4B-ROS2-Kit/UGV-Beast-PT-PI4B-ROS2-Kit-details-43.jpg)

---

### 크로스 플랫폼 웹 애플리케이션을 통한 쉬운 제어

앱 설치가 필요 없으며, 사용자는 휴대폰, 태블릿, 컴퓨터를 통해 브라우저 웹 앱으로 로봇에 연결하고 제어할 수 있습니다. 키보드가 있는 PC를 통해 WASD 및 마우스와 같은 단축키 제어를 지원합니다.

![웹 애플리케이션을 통한 제어](https://www.waveshare.com/img/devkit/accBoard/UGV-Beast-PT-PI4B-ROS2-Kit/UGV-Beast-PT-PI4B-ROS2-Kit-details-45.jpg)

---

### WebRTC 실시간 비디오 전송

Flask 경량 웹 애플리케이션을 채택하고, WebRTC 초저지연 실시간 전송을 기반으로 하며, Python 언어를 사용하고 확장하기 쉬우며 OpenCV와 원활하게 작동합니다.

![실시간 무선 전송 지원](https://www.waveshare.com/img/devkit/accBoard/UGV-Beast-PT-PI4B-ROS2-Kit/UGV-Beast-PT-PI4B-ROS2-Kit-details-47.jpg)

---

### 인식, 추적 및 타겟팅

OpenCV를 기반으로 색상 인식 및 자동 타겟팅을 달성합니다. 원키 팬틸트 제어 및 자동 LED 조명을 지원하며, 더 많은 기능 확장이 가능합니다.

![색상 인식 및 자동 타겟팅 데모](https://www.waveshare.com/img/devkit/accBoard/UGV-Beast-PT-PI4B-ROS2-Kit/UGV-Beast-PT-PI4B-ROS2-Kit-details-49-3.jpg)

---

### 얼굴 감지: 자동 사진 또는 비디오 캡처

OpenCV를 기반으로 얼굴 인식을 달성하며, 얼굴이 인식되면 자동 사진 촬영 또는 비디오 녹화를 지원합니다.

![얼굴 인식 데모](https://www.waveshare.com/img/devkit/accBoard/UGV-Beast-PT-PI4B-ROS2-Kit/UGV-Beast-PT-PI4B-ROS2-Kit-details-49-1.jpg)

---

### 지능형 객체 인식

기본 모델로 많은 일반적인 객체를 인식할 수 있습니다.

![객체 인식 데모](https://www.waveshare.com/img/devkit/accBoard/UGV-Beast-PT-PI4B-ROS2-Kit/UGV-Beast-PT-PI4B-ROS2-Kit-details-49-2.jpg)

---

### 제스처 인식: 신체 언어와의 AI 상호작용

OpenCV와 MediaPipe를 결합하여 팬틸트 및 LED의 제스처 제어를 실현합니다.

![사진 촬영 제스처 제어 데모](https://www.waveshare.com/img/devkit/accBoard/UGV-Beast-PT-PI4B-ROS2-Kit/UGV-Beast-PT-PI4B-ROS2-Kit-details-49-4-1.jpg)
**사진 촬영 제스처 제어**

![백라이트 제어 제스처 제어 데모](https://www.waveshare.com/img/devkit/accBoard/UGV-Beast-PT-PI4B-ROS2-Kit/UGV-Beast-PT-PI4B-ROS2-Kit-details-49-4-2.jpg)
**LED ON/OFF 및 백라이트 제어**

---

### 복잡한 비디오 처리 작업을 쉽게 생성하기 위한 더 많은 MediaPipe 데모

MediaPipe는 Google에서 개발한 오픈 소스 프레임워크로, 크로스 플랫폼 멀티미디어 처리 파이프라인 구축을 위한 것입니다. 사전 구축된 구성 요소 및 도구 세트를 제공하며, 고성능 처리 능력으로 로봇이 실시간 비디오 분석과 같은 복잡한 멀티미디어 입력에 응답하고 처리할 수 있도록 합니다.

![얼굴 인식 데모](https://www.waveshare.com/img/devkit/accBoard/UGV-Beast-PT-PI4B-ROS2-Kit/UGV-Beast-PT-PI4B-ROS2-Kit-details-51-2.jpg)
**얼굴 인식**

![자세 감지 데모](https://www.waveshare.com/img/devkit/accBoard/UGV-Beast-PT-PI4B-ROS2-Kit/UGV-Beast-PT-PI4B-ROS2-Kit-details-51-1.jpg)
**자세 감지**

---

### 40PIN GPIO 확장 헤더

로봇은 통신을 위해 Raspberry Pi GPIO의 URAT 인터페이스만 점유하며, 드라이버 보드의 외부 40PIN 헤더를 적용하여 더 많은 주변 장치와 기능을 확장할 수 있습니다.

![온보드 40PIN GPIO 확장 헤더](https://www.waveshare.com/img/devkit/accBoard/UGV-Beast-PT-PI4B-ROS2-Kit/UGV-Beast-PT-PI4B-ROS2-Kit-details-53.jpg)

---

### 실시간 정보 피드백 얻기

로봇의 작동 상태를 실시간으로 모니터링합니다.

![실시간 정보 피드백 얻기](https://www.waveshare.com/img/devkit/accBoard/UGV-Beast-PT-PI4B-ROS2-Kit/UGV-Beast-PT-PI4B-ROS2-Kit-details-55.jpg)

---

### 웹 페이지 명령줄 도구: 쉬운 확장을 위한 다중 기능

빠른 설정, 쉬운 확장. 프론트엔드 코드 수정 없이 새로운 기능을 쉽게 사용자 정의하고 추가할 수 있습니다.

![웹 페이지 명령줄 도구](https://www.waveshare.com/img/devkit/accBoard/UGV-Beast-PT-PI4B-ROS2-Kit/UGV-Beast-PT-PI4B-ROS2-Kit-details-56.jpg)

---

### 로봇 간 ESP-NOW 무선 통신

ESP-NOW 통신 프로토콜을 기반으로 여러 로봇이 IP 또는 MAC 주소 없이 서로 통신할 수 있으며, 100 마이크로초의 저지연 통신으로 다중 장치 협업을 달성합니다.

![ESP-NOW 무선 통신 지원](https://www.waveshare.com/img/devkit/accBoard/UGV-Beast-PT-PI4B-ROS2-Kit/UGV-Beast-PT-PI4B-ROS2-Kit-details-59.jpg)

---

### 더 나은 작동 경험을 위한 게임패드 제어

무선 게임패드가 함께 제공되어 로봇 제어가 더욱 유연해집니다. USB 수신기를 PC에 연결하고 인터넷을 통해 원격으로 로봇을 제어할 수 있습니다. 사용자 고유의 상호작용 방법을 사용자 정의하기 위한 오픈 소스 데모를 제공합니다.

![무선 게임패드 제어 지원](https://www.waveshare.com/img/devkit/accBoard/UGV-Beast-PT-PI4B-ROS2-Kit/UGV-Beast-PT-PI4B-ROS2-Kit-details-61.jpg)

---

### 4G/5G 확장 지원

WiFi가 없는 애플리케이션 시나리오를 위해 4G/5G 모듈* 설치를 지원합니다.

![4G/5G 모듈 설치 지원](https://www.waveshare.com/img/devkit/accBoard/UGV-Beast-PT-PI4B-ROS2-Kit/UGV-Beast-PT-PI4B-ROS2-Kit-details-63.jpg)
*\* 로봇의 로컬 네트워크 서비스(Flask 애플리케이션)를 인터넷에 노출시켜 어디서든 로봇을 제어할 수 있도록 Ngrok, Cpolar 또는 LocalTunnel과 같은 터널링 서비스를 사용해야 할 수 있습니다.*

---

### 인터넷을 통한 원격 제어 실현

*   웹 애플리케이션 데모는 실시간 비디오 전송을 위해 WebRTC를 기반으로 합니다.
*   WebRTC (Web Real-Time Communications)는 웹 애플리케이션과 사이트가 피어 투 피어 연결을 설정하고 선택적으로 오디오 및/또는 비디오 미디어를 캡처 및 스트리밍하며, 중개자 없이 브라우저 간에 임의의 데이터를 교환할 수 있게 하는 기술입니다.
*   빠르게 시작하고 인터넷을 통해 로봇 제어를 실현하는 데 도움이 되는 포괄적인 Ngrok 튜토리얼*을 제공합니다.

![WebRTC 기반 실시간 비디오 전송 및 원격 제어](https://www.waveshare.com/img/devkit/accBoard/UGV-Beast-PT-PI4B-ROS2-Kit/UGV-Beast-PT-PI4B-ROS2-Kit-details-65.jpg)
*\* Ngrok 사용 튜토리얼만 제공하며, Ngrok 계정이나 서버는 제공하지 않습니다. 튜토리얼에 따라 자체 Ngrok 서비스를 열거나 필요에 따라 다른 터널링 서비스를 선택할 수 있습니다.*

---

### 스마트폰 홀더 설치 지원

여분의 휴대폰이 있다면 아래와 같이 홀더를 통해 로봇에 설치할 수 있으며, 휴대폰을 사용하여 로봇용 핫스팟을 생성하고 더 저렴한 비용으로 인터넷을 통한 원격 제어를 달성할 수 있습니다.

![스마트폰 홀더 설치 지원](https://www.waveshare.com/img/devkit/accBoard/UGV-Beast-PT-PI4B-ROS2-Kit/UGV-Beast-PT-PI4B-ROS2-Kit-details-64.jpg)
*\* 패키지에 1/4″ 나사가 있는 스마트폰 홀더가 포함되어 있습니다.*

---

### 크로스 플랫폼 대화형 튜토리얼: 배우면서 개발하기

휴대폰, 태블릿과 같은 장치를 통해 Jupyter Lab에 액세스하여 튜토리얼을 읽고 웹 페이지에서 코드를 편집하여 개발을 더 쉽게 만듭니다.

![Jupyter Lab 액세스 지원](https://www.waveshare.com/img/devkit/accBoard/UGV-Beast-PT-PI4B-ROS2-Kit/UGV-Beast-PT-PI4B-ROS2-Kit-details-67-1.jpg)
![PC를 통해 Jupyter Lab으로 제어](https://www.waveshare.com/img/devkit/accBoard/UGV-Beast-PT-PI4B-ROS2-Kit/UGV-Beast-PT-PI4B-ROS2-Kit-details-67-2.jpg)

---

### 풍부한 튜토리얼 리소스

사용자가 학습 및 2차 개발을 위해 빠르게 시작할 수 있도록 완전한 튜토리얼과 데모를 제공합니다.

![호스트 컨트롤러 튜토리얼 소개](https://www.waveshare.com/img/devkit/accBoard/UGV-Beast-PT-PI4B-ROS2-Kit/UGV-Beast-PT-PI4B-ROS2-Kit-details-69-1.jpg)
![호스트 컨트롤러 학습 튜토리얼 소개](https://www.waveshare.com/img/devkit/accBoard/UGV-Beast-PT-PI4B-ROS2-Kit/UGV-Beast-PT-PI4B-ROS2-Kit-details-69-2.jpg)
![ROS2 학습 튜토리얼 소개](https://www.waveshare.com/img/devkit/accBoard/UGV-Beast-PT-PI4B-ROS2-Kit/UGV-Beast-PT-PI4B-ROS2-Kit-details-69-3.jpg)
![서브 컨트롤러 학습 튜토리얼 소개](https://www.waveshare.com/img/devkit/accBoard/UGV-Beast-PT-PI4B-ROS2-Kit/UGV-Beast-PT-PI4B-ROS2-Kit-details-69-4.jpg)

---

### 모든 데모 오픈 소스 제공: 완전한 듀얼 컨트롤러 기술 스택

![모든 데모 오픈 소스](https://www.waveshare.com/img/devkit/accBoard/UGV-Beast-PT-PI4B-ROS2-Kit/UGV-Beast-PT-PI4B-ROS2-Kit-details-71.jpg)

---

### 제품 쇼

![제품 쇼](https://www.waveshare.com/img/devkit/accBoard/UGV-Beast-PT-PI4B-ROS2-Kit/UGV-Beast-PT-PI4B-ROS2-Kit-details-73.jpg)

---

### 외형 치수

![UGV Beast PT AI Kit 외형 치수](https://www.waveshare.com/img/devkit/accBoard/UGV-Beast-PT-PI4B-ROS2-Kit/UGV-Beast-PT-PI4B-ROS2-Kit-size-1.jpg)
![UGV Beast AI Kit (PT 모듈 없음) 외형 치수](https://www.waveshare.com/img/devkit/accBoard/UGV-Beast-PT-PI4B-ROS2-Kit/UGV-Beast-PT-PI4B-ROS2-Kit-size-2.jpg)

---

### 리소스 및 서비스

![리소스 배너](https://www.waveshare.com/img/devkit/LCD/common/res_banner.png)
![리소스 내용](https://www.waveshare.com/img/devkit/LCD/common/res_content.png)
---
**WIKI:** [www.waveshare.com/wiki/UGV_Beast_PI_ROS2](https://www.waveshare.com/wiki/UGV_Beast_PI_ROS2)
---
*\* 다른 제품의 리소스는 다를 수 있으므로, 실제로 제공되는 리소스를 확인하려면 위키 페이지를 확인하십시오.*

---

## 패키지 내용

### UGV Beast PT PI4B ROS2 Kit

![UGV Beast PT PI4B ROS2 Kit 패키지 내용](https://www.waveshare.com/img/devkit/accBoard/UGV-Beast-PT-PI4B-ROS2-Kit/UGV-Beast-PT-PI4B-ROS2-Kit-pack.jpg)

### UGV Beast PT PI5 ROS2 Kit

![UGV Beast PT PI5 ROS2 Kit 패키지 내용](https://www.waveshare.com/img/devkit/accBoard/UGV-Beast-PT-PI4B-ROS2-Kit/UGV-Beast-PT-PI5-ROS2-Kit-pack.jpg)

### UGV Beast PI4B ROS2 Kit

![UGV Beast PI4B ROS2 Kit 패키지 내용](https://www.waveshare.com/img/devkit/accBoard/UGV-Beast-PT-PI4B-ROS2-Kit/UGV-Beast-PI4B-ROS2-Kit-pack.jpg)

### UGV Beast PI5 ROS2 Kit

![UGV Beast PI5 ROS2 Kit 패키지 내용](https://www.waveshare.com/img/devkit/accBoard/UGV-Beast-PT-PI4B-ROS2-Kit/UGV-Beast-PI5-ROS2-Kit-pack.jpg)

---

## 위키

자세한 정보 및 설정 가이드는 다음 위키 페이지를 참조하십시오:
[www.waveshare.com/wiki/UGV_Beast_PI_ROS2](https://www.waveshare.com/wiki/UGV_Beast_PI_ROS2)
