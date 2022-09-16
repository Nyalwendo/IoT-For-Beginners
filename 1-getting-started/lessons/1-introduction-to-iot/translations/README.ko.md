# IoT에 대한 소개

![이 강의의 개요](../../../../sketchnotes/lesson-1.jpg)

> [Nitya Narasimhan](https://github.com/nitya) 의 스케치노트. 더 큰 이미지를 보고싶으면 클릭하세요.

이 수업은 [Microsoft Reactor](https://developer.microsoft.com/reactor/?WT.mc_id=academic-17441-jabenn)의 [Hello IoT series](https://youtube.com/playlist?list=PLmsFUfdnGr3xRts0TIwyaHyQuHaNQcb6-) 일부로 진행되었습니다. 수업은 2개의 비디오로 진행되었는데, 1시간짜리 수업과 강의에 대한 집중탐구 및 질의 응답 1시간으로 구성되어있습니다. 

[![Lesson 1: Introduction to IoT](https://img.youtube.com/vi/bVFfcYh6UBw/0.jpg)](https://youtu.be/bVFfcYh6UBw)

[![Lesson 1: Introduction to IoT - Office hours](https://img.youtube.com/vi/YI772q5v3yI/0.jpg)](https://youtu.be/YI772q5v3yI)

> 🎥 비디오를 시청하고 싶으면 이미지를 클릭하세요

## 강의 전 퀴즈

[강의 전 퀴즈](https://black-meadow-040d15503.1.azurestaticapps.net/quiz/1)

## 개요

이 강의에서는 사물 인터넷과 관련된 몇 가지 소개용 항목에 대해 설명하고 하드웨어를 설정하는 방법에 대해 설명합니다.

이 단원에서는 다음을 다룹니다:

* ['사물 인터넷'이란?](#what-is-the-internet-of-things)
* [IoT 장치](#iot-devices)
* [디바이스 설정](#set-up-your-device)
* [IoT의 응용 프로그램](#applications-of-iot)
* [내 주변에서 IoT의 예시](#examples-of-iot-devices-you-may-have-around-you)

## '사물 인터넷'이란 무엇인가?

'사물 인터넷'이라는 용어는 1999년, [Kevin Ashton](https://wikipedia.org/wiki/Kevin_Ashton)이 센서를 통해 인터넷을 물리적 세계에 연결하는 것을 지칭하기 위해 만들었다. 그 이후로 이 용어는 센서로부터 데이터를 수집하거나 액츄에이터(스위치를 켜거나 LED를 켜거나 켜는 것과 같은 일을 하는 장치)를 통해 실제 상호작용을 제공함으로써 주변 물리 세계와 상호 작용하는 모든 장치를 기술하기 위해 사용되어 왔으며 일반적으로 다른 장치나 인터넷에 연결되어 있다.

> **센서** 는 속도, 온도 또는 위치 와 같은 정보를 세상에서 수집합니다.
>
> **액츄에이터** 는 전기 신호를 스위치 트리거, 조명 켜기, 소리 내기 또는 전원 소켓 켜기와 같은 실제 상호 작용으로 변환합니다.

IoT는 단순한 기기가 아니라 센서 데이터를 처리하거나 IoT 기기에 연결된 액츄에이터에 요청을 보낼 수 있는 클라우드 기반 서비스를 포함합니다. 또한 edge장치라고 종종 언급되는, 인터넷 연결이 없거나 필요하지 않은 장치도 포함됩니다. 이들은 센서 데이터를 자체적으로 처리하고 대응할 수 있는 장치들로, 대개 클라우드에서 훈련된 AI 모델을 사용합니다.

IoT는 빠르게 성장하는 기술 분야입니다. 2020년 말까지, IoT 기기가 300억대 보급돼 인터넷에 연결된 것으로 추산됩니다. 미래를 내다보면 2025년에는, IoT 기기가 거의 80제타바이트 또는 80조 기가바이트의 데이터를 수집할 것으로 예상됩니다. 정말 많은 데이터양이죠!

![2015년에 50억 미만에서 2025년에 300억 이상으로 증가하는 추세로 시간에 따른 활성 IoT 기기를 보여주는 그래프](../../../../images/connected-iot-devices.svg)

✅ 약간의 조사를 해보세요: IoT 기기에서 생성된 데이터의 얼마가 실제로 사용되고 있고, 얼마나 많은 데이터가 낭비되고 있나요? 왜 이렇게 많은 데이터가 무시되는 것일까요?

IoT 성공의 비결은 바로 이 데이터입니다. 성공적인 IoT 개발자가 되려면 수집해야 할 데이터, 수집 방법, 이를 어떻게 결정을 할지 및 필요한 경우 이러한 결정들을 물리 세계와 연동하기 위해 어떻게 이용해야하는지 이해해야 합니다.

## IoT 장치

IoT에서 **T** 는 **Things** 을 의미합니다. - 센서로부터 데이터를 수집하거나 액추에이터를 통해 실세계의 상호작용을 제공하며 주변 물리적 세계와 상호 작용하는 장치입니다.

소비자 피트니스 추적기 또는 산업용 기계 제어기와 같은 생산 또는 상업적 사용을 위한 장치는 일반적으로 맞춤 제작됩니다. 이들은 맞춤형 회로 기판, 심지어 맞춤형 프로세서를 사용하기도 하는데, 이 기판은 손목에 찰 정도로 작거나 고온, 고강도 또는 고진동 공장 환경에서 작동하기에 충분히 견고하거나, 손목에 잘 맞도록 설계되어 있습니다.

개발자는 IoT에 대해 배우거나 기기 프로토타입을 만들 때 개발자 키트로 시작해야 합니다. 그것은 개발자가 사용할 수 있도록 설계된 범용 IoT 장치이며, 센서나 액추에이터를 연결할 수 있는 외부 핀 세트, 디버깅을 지원하는 하드웨어 또는 대규모 제조 실행 시 불필요한 비용을 추가하는 추가 리소스와 같은 운영 장치에는 없는 기능을 갖추고 있습니다.

이러한 개발자 키트는 일반적으로 마이크로컨트롤러와 싱글보드 컴퓨터의 두 가지 범주로 나뉩니다. 이것들은 여기서 소개될 것이고, 다음 수업에서 더 자세히 다루도록 하겠습니다.

> 💁 당신의 핸드폰 또한 센서와 액추에이터가 내장된 범용 IoT 기기로도 볼 수 있으며, 앱마다 센서와 액추에이터를 사용하는 방식이 다르고 클라우드 서비스도 다릅니다. 당신은 또한 휴대폰 앱을 IoT 기기로 사용하는 IoT 튜토리얼도 찾아볼 수 있습니다.

### 마이크로컨트롤러

마이크로컨트롤러(줄여서 MCU라고도 함)는 다음과 같이 구성된 소형 컴퓨터입니다.:

🧠 하나 이상의 CPU(중앙 처리 장치) - 당시의 프로그램을 실행하는 마이크로컨트롤러의 '두뇌'

💾 메모리(RAM 및 프로그램 메모리) - 당신의 프로그램, 데이터 및 변수가 저장되는 위치

🔌 프로그래밍 가능한 입출력(I/O) 연결 - 센서 및 액추에이터와 같은 외부 주변 장치(연결 장치)와 통신

마이크로컨트롤러는 일반적으로 저렴한 컴퓨팅 장치이며, 사용자 지정 하드웨어에 사용되는 장치의 평균 가격은 약 0.50달러까지 떨어지며, 어떤 장치는 0.03달러만큼 저렴합니다. 개발자 키트는 미화 4달러부터 시작할 수 있으며, 기능을 추가할수록 비용도 증가합니다. [Wio Terminal](https://www.seeedstudio.com/Wio-Terminal-p-4509.html) 센서, 액츄에이터, WiFi, 스크린을 갖춘 [Seeed studios](https://www.seeedstudio.com) 의 마이크로컨트롤러 개발자 키트로 미화 약 30달러의 가격으로 형성되어 있습니다.

![A Wio Terminal](../../../../images/wio-terminal.png)

> 💁 인터넷에서 마이크로컨트롤러를 검색할 때 **MCU**라는 용어를 검색하면 마이크로컨트롤러가 아닌 Marvel Cinematic Universe에 대한 많은 결과를 얻을 수 있으므로 주의해야 합니다.

마이크로컨트롤러는 PC나 맥과 같은 범용 컴퓨터가 아니라 제한된 수의 매우 특정한 작업을 수행하도록 프로그래밍되어 있습니다. 매우 구체적인 시나리오를 제외하고는 모니터, 키보드 및 마우스를 연결하여 범용 작업에 사용할 수 없습니다.

마이크로컨트롤러 개발자 키트는 보통 추가적인 센서와 작동기가 탑재되어 있습니다. 대부분의 보드에는 프로그래밍할 수 있는 하나 이상의 LED와 다양한 제조업체의 에코시스템을 사용하여 더 많은 센서 또는 액추에이터를 추가하는 표준 플러그와 같은 다른 장치 또는 내장 센서(일반적으로 온도 센서 등 가장 인기 있는 센서)가 있습니다. 일부 마이크로컨트롤러는 Bluetooth 또는 WiFi와 같은 무선 연결이 내장되어 있거나 이 연결을 추가하기 위해 보드에 추가 마이크로컨트롤러가 있습니다.

> 💁 마이크로컨트롤러는 보통 C/C++로 프로그래밍 됩니다.

### 싱글보드 컴퓨터

단일 보드 컴퓨터(single-board computer)는 하나의 작은 보드에 포함된 완전한 컴퓨터의 모든 요소를 포함하는 소형 컴퓨팅 장치입니다. 데스크탑 또는 노트북 PC 또는 Mac에 가까운 사양을 갖추고 있으며 전체 운영 체제를 실행하지만 크기가 작고 전력 사용량이 적으며 가격이 상당히 저렴한 장치입니다.

![A Raspberry Pi 4](../../../../images/raspberry-pi-4.jpg)

라즈베리 파이는 가장 인기 있는 싱글보드 컴퓨터 중 하나입니다.

마이크로컨트롤러와 마찬가지로 싱글보드 컴퓨터에는 CPU, 메모리, 입출력 핀이 있지만 모니터, 오디오 출력, USB 포트를 연결하여 키보드 마우스와 웹캠이나 외장 스토리지와 같은 표준 USB 장치를 연결할 수 있는 그래픽 칩과 같은 추가 기능이 있습니다. 프로그램은 메모리 칩 대신 운영 체제와 함께 SD 카드나 하드 드라이브에 저장됩니다.

> 🎓 싱글보드 컴퓨터는 센서 및 액추에이터와 상호 작용할 GPIO(일반용 입력/출력) 핀을 추가하여 읽고 있는 PC 또는 Mac의 더 작고 저렴한 버전이라고 생각할 수 있습니다.

싱글보드 컴퓨터는 모든 기능을 갖춘 컴퓨터이므로 모든 언어로 프로그래밍할 수 있습니다. IoT 장치는 일반적으로 파이썬으로 프로그래밍됩니다.

### 남은 수업 동안의 하드웨어 선택

이후의 모든 과정에는 IoT 디바이스를 사용하여 물리적 세계와 상호 작용하고 클라우드와 통신하는 과제가 포함됩니다. 각 레슨은 Arduino(Seeed Studios Wio Terminal 사용) 또는 단일 보드 컴퓨터, 물리적 장치(Lasberry Pi 4), PC 또는 Mac에서 실행되는 가상 단일 보드 컴퓨터 등 3가지 장치를 지원합니다.

모든 과제를 완료하는 데 필요한 하드웨어에 대한 자세한 내용은 [하드웨어 가이드](../../../hardware.md)에서 확인할 수 있습니다.

> 💁 과제를 완료하기 위해 IoT 하드웨어를 구입할 필요가 없으며 가상 싱글보드 컴퓨터로 모든 작업을 수행할 수 있습니다.

어떤 하드웨어를 선택할지는 여러분의 학교와 가정에서 사용할 수 있는 것과 여러분이 알고 있거나 배울 계획인 프로그래밍 언어에 달려 있습니다. 두 하드웨어 변형 모두 동일한 센서 생태계를 사용하기 때문에 한 경로에서 시작하면 대부분의 키트를 교체할 필요 없이 다른 경로로 변경할 수 있습니다. 가상 싱글보드 컴퓨터는 라즈베리 파이에서 학습하는 것과 같으며, 결국 장치와 센서를 얻게 되면 대부분의 코드를 파이로 전송할 수 있습니다.

### 아두이노 개발자 키트

마이크로컨트롤러 개발에 관심이 있다면 아두이노 기기를 이용해 과제를 완료할 수 있습니다. 이 수업은 아두이노 프레임워크, 사용 중인 센서와 액추에이터, 클라우드와 상호 작용하는 라이브러리와 관련된 코드만 가르치기 때문에 C/C++ 프로그래밍에 대한 기본적인 이해가 필요합니다.

과제는 [Visual Studio Code](https://code.visualstudio.com/?WT.mc_id=academic-17441-jabenn) 와 [PlatformIO extension for microcontroller development](https://platformio.org)를 이용할 것입니다. 또한 이 도구에 익숙한 경우, 지침이 제공되지 않는 Arduino IDE를 사용할 수도 있습니다.

### Single-board 컴퓨터 개발자 키트

싱글보드 컴퓨터를 사용하여 IoT 개발을 배우는 데 관심이 있다면 PC 또는 Mac에서 실행 중인 가상 장치인 라즈베리 파이를 사용하여 과제를 완료할 수 있습니다.

사용 중인 센서와 액추에이터, 클라우드와 상호 작용하는 라이브러리와 관련된 코드만 학습하므로 파이썬 프로그래밍에 대한 기본적인 이해가 필요합니다.

> 💁 만약 당신이 Python으로 코드를 알기 원한다면 : 다음의 두개의 비디오 시리즈를 확인해보세요 :
>
> * [입문자를 위한 파이썬](https://channel9.msdn.com/Series/Intro-to-Python-Development?WT.mc_id=academic-17441-jabenn)
> * [입문자를 위한 더 많은 파이썬](https://channel9.msdn.com/Series/More-Python-for-Beginners?WT.mc_id=academic-7372-jabenn)

과제에서는 [Visual Studio Code](https://code.visualstudio.com/?WT.mc_id=academic-17441-jabenn)을 이용할 것입니다..

Rasberry Pi를 사용하는 경우 Rasberry Pi OS의 전체 데스크톱 버전을 사용하여 Pi를 실행하고 [Rasberry Pi OS 버전의 VS Code](https://code.visualstudio.com/docs/setup/raspberry-pi?WT.mc_id=academic-17441-jabenn)를 사용하여 Pi에서 직접 모든 코딩을 수행하거나 [원격 SSH 확장](https://code.visualstudio.com/docs/remote/ssh?WT.mc_id=academic-17441-jabenn)을 사용하여 PC 또는 Mac의 헤드리스 장치 및 코드로 Pi를 실행할 수 있습니다. 직접 코드를 코딩하는 것처럼 코드를 편집, 디버그 및 실행합니다.

가상 디바이스 옵션을 사용하는 경우 컴퓨터에서 직접 코딩합니다. 센서와 액추에이터에 액세스하는 대신 도구를 사용하여 정의할 수 있는 센서 값을 제공하고 액추에이터의 결과를 화면에 표시합니다.

## 장치 설정

IoT 장치 프로그래밍을 시작하려면 먼저 소량의 설정을 수행해야 합니다. 사용할 기기에 따라 아래의 관련 지침을 따라보세요.

> 💁 아직 장치가 없는 경우 [하드웨어 가이드](../../../../hardware.md)를 참조하여 사용할 장치와 구입해야 할 추가 하드웨어를 결정해보세요. 모든 프로젝트를 가상 하드웨어에서 실행할 수 있으므로 하드웨어를 구입할 필요는 없습니다.

이러한 지침에는 사용할 하드웨어 또는 도구를 만든 사람이 제공하는 타사 웹 사이트에 대한 링크가 포함됩니다. 이렇게 하면 다양한 도구 및 하드웨어에 대한 최신 지침을 항상 사용할 수 있습니다.

관련 안내에 따라 장치를 설정하고 'Hello World' 프로젝트를 완료해보세요. 이것은 이 시작 부분의 4가지 레슨에 대한 IoT 야간조명을 만드는 첫 번째 단계가 될 것입니다.

* [Arduino - Wio Terminal](wio-terminal.md)
* [Single-board computer - Raspberry Pi](pi.md)
* [Single-board computer - Virtual device](virtual-device.md)

✅ 당신은 아두이노와 싱글보드 컴퓨터 모두에 VS code를 사용하게 될 것입니다. 사용해본적이 없다면 [VS Code site](https://code.visualstudio.com?WT.mc_id=academic-17441-jabenn)를 자세히 읽어보세요.

## IoT의 응용

IoT는 몇 가지 광범위한 그룹에 걸쳐 광범위한 사용 사례를 다루고 있습니다 :

* 소비자 IoT
* 상용 IoT
* 산업 IoT
* 사회 기반 시설 IoT

✅ 약간의 조사를 해보세요: 아래에 설명된 각 영역에 대해, 본문에 나와 있지 않은 구체적인 예를 하나 찾아보세요.

### 소비자 IoT

컨슈머 IoT는 소비자가 가정 주변에서 구매해 사용할 IoT 기기를 말합니다. 스마트 스피커, 스마트 난방 시스템, 로봇 청소기와 같은 이 장치들 중 일부는 엄청나게 유용합니다. 음성 제어 수도꼭지와 같이 유용성이 의심되는 경우도 있는데, 이는 음성 제어가 흐르는 물 소리 때문에 당신의 목소리를 들을 수 없기 때문에 끌 수 없음을 의미합니다.

소비자 IoT 기기들은 특히 장애를 가진 10억 명의 사람들에게 그들의 환경에서 더 많은 것을 성취할 수 있는 힘을 주고 있습니다. 로봇청소기는 스스로 진공청소기를 사용할 수 없는 거동이 불편한 사람들에게 깨끗한 바닥을 제공할 수 있고, 음성제어 오븐은 시력이 제한적이거나 운동기능이 있는 사람들이 목소리만으로 오븐을 데울 수 있게 하며, 건강 모니터는 환자들이 만성 상태를 그들의 상태에 대한 업데이트로 보다 규칙적이고 더 자세하게 스스로 모니터링할 수 있게 합니다. 예를 들어 COVID 대유행 기간 동안 가상 교육을 하는 학생들이 스마트 홈 장치에 타이머를 설정하여 학교 공부를 추적하거나 다가오는 학급 회의를 상기시키는 등 이러한 장치는 매우 보편화되고 있습니다.

✅ 개인 또는 가정에 어떤 소비자 IoT 기기를 가지고 있나요?

### 상용 IoT

상용 IoT는 직장에서 IoT를 사용하는 것을 포함합니다. 사무실 환경에서는 조명과 난방을 관리하기 위한 거주 감지기와 동작 감지기가 있어 필요하지 않을 때만 조명을 유지하고 열을 차단하여 비용과 탄소 배출량을 줄일 수 있습니다. 공장에서 사물인터넷(IoT) 기기는 작업자가 안전모를 쓰지 않거나 위험 수위에 도달한 소음 등 안전상의 위험을 감시할 수 있습니다. 소매업체에서는 사물인터넷(IoT) 기기가 냉장·냉동고가 필요 온도 범위를 벗어나면 점주에게 알려 냉장·냉동고 보관 온도를 측정하거나, 선반에 있는 품목을 모니터링해 직원들에게 판매된 농산물을 리필하도록 지시할 수 있습니다. 운송업계는 차량 위치 모니터링, 도로 사용자 충전을 위한 온로드 마일리지 추적, 운전자 시간 및 고장 준수 여부 추적, 적재 또는 하역 준비를 위해 차량 입고지 접근 시 직원에게 알리는 등의 IoT 의존도가 높아지고 있습니다.

✅ 당신의 학교나 직장에 어떤 상용 IoT 기기를 가지고 있나요?

### 산업 IoT (IIoT)

산업용 IoT 또는 IIoT는 대규모로 기계를 제어하고 관리하기 위해 IoT 장치를 사용하는 것입니다. 여기에는 공장에서 디지털 농업에 이르기까지 광범위한 사용 사례가 포함됩니다.

공장들은 IoT 기기를 다양한 방식으로 사용합니다. 기계는 온도, 진동, 회전 속도와 같은 것들을 추적하기 위해 여러 센서로 모니터링될 수 있습니다. 그런 다음 이 데이터를 모니터링하여 특정 공차를 벗어날 경우 기계가 중지되도록 할 수 있습니다. 예를 들어, 너무 뜨거울 경우 기계가 종료됩니다. 이 데이터는 시간이 지남에 따라 수집 및 분석하여 예측 정비를 수행할 수 있으며, 여기서 AI 모델은 장애로 이어지는 데이터를 살펴보고 다른 장애가 발생하기 전에 예측에 사용할 수 있습니다.

지구의 증가하는 인구, 특히 [지속 농업](https://wikipedia.org/wiki/Subsistence_agriculture)으로 생존하는 5억 가구 20억 인구의 경우 디지털 농업이 중요합니다. 디지털 농업은 몇 개의 한 자릿수 달러 센서에서 대규모 상업 설정에 이르기까지 다양합니다. 농부는 온도를 모니터링하고 [일별 성장 비율](https://wikipedia.org/wiki/Growing_degree-day) 을 사용하여 농작물이 언제 수확할 수 있는지 예측할 수 있습니다. 그들은 토양 수분 모니터링과 자동 식수 시스템을 연결하여 식물들에게 필요한 만큼의 물을 줄 수 있지만, 물을 낭비하지 않고 농작물이 마르지 않도록 더 이상 보장할 수는 없습니다. 농부들은 심지어 그것을 더 나아가서 드론, 위성 데이터, AI를 이용하여 거대한 농경지의 농작물 성장, 질병, 토양의 질 등을 감시하고 있습니다.

✅ 농부들에게 도움이 될 수 있는 다른 사물인터넷 기기들은 무엇일까요?

### 사회 기반 시설(인프라) IoT

인프라 IoT는 사람들이 일상적으로 사용하는 지역적 인프라와 세계적 인프라를 감시하고 제어하는 것입니다.

[Smart Cities](https://wikipedia.org/wiki/Smart_city) 는 IoT 기기를 사용하여 도시에 대한 데이터를 수집하고 도시 운영 방식을 개선하는 도시 지역입니다. 이 도시들은 보통 지방 정부, 학계, 지역 기업들 간의 협업으로 운영되며, 교통에서부터 주차, 오염에 이르기까지 다양한 것들을 추적하고 관리합니다. 예를 들어 덴마크 코펜하겐은 대기오염이 지역 주민들에게 중요하기 때문에 이를 측정해 데이터를 활용해 가장 깨끗한 자전거와 조깅 경로에 대한 정보를 제공합니다.

[스마트 전력망](https://wikipedia.org/wiki/Smart_grid) 은 개별 가정 수준에서 사용 데이터를 수집하여 전력 수요를 더 잘 분석할 수 있도록 합니다. 이 데이터는 발전소를 새로 지을 장소를 포함한 국가 차원에서의 의사 결정을 안내할 수 있으며, 사용자가 얼마나 많은 전력을 사용하고 있는지, 언제 사용하는지에 대한 통찰력과 심지어 야간 전기차 충전과 같은 비용 절감 방법에 대한 제안까지 사용자에게 제공하여 개인 차원에서의 의사 결정을 안내할 수 있습니다.

✅ 만약 당신이 살고 있는 곳의 사물인터넷 장치를 추가하여 무엇이든 측정할 수 있다면, 무엇을 하고 싶나요?

## 주변에 있을 수 있는 IoT 장치의 예

주변에 IoT 기기가 얼마나 많은지 알면 놀라실거에요. 집에서 작성 중이며 앱 컨트롤, 음성 컨트롤 또는 전화기를 통해 데이터를 전송하는 기능과 같은 스마트 기능을 갖춘 다음과 같은 장치들이 인터넷에 연결되어 있습니다.

* 다중 스마트 스피커
* 냉장고, 식기세척기, 오븐 및 전자레인지
* 태양 전지판용 전기 모니터
* 스마트 플러그
* 비디오 초인종 및 보안 카메라
* 여러 개의 스마트 룸 센서가 장착된 스마트 온도 조절기
* 차고 문 개폐기
* 가정용 엔터테인먼트 시스템 및 음성 제어 TV
* 조명
* 피트니스 및 건강 추적기

이러한 모든 유형의 장치에는 센서 및/또는 작동기가 있으며 인터넷과 통신합니다. 우리는 휴대폰으로 차고 문이 열려 있는지 알 수 있고, 스마트 스피커에게 문을 닫아달라고 부탁할 수 있습니다. 타이머도 설정할 수 있어서 밤에 열려 있으면 자동으로 닫힙니다. 초인종이 울리면 세계 어디에 있든 휴대폰으로 누가 있는지, 초인종 안에 내장된 스피커와 마이크를 통해 대화할 수 있습니다. 나는 내 혈당, 심박수, 수면 패턴을 모니터링 할 수 있고 내 건강을 증진시키기 위해 데이터에서 패턴을 찾을 수 있습니다. 우리는 클라우드를 통해 조명을 제어할 수 있고, 인터넷 연결이 끊어졌을 때 어둠 속에 앉아 있을 수 있습니다.

---

## 🚀 도전

집, 학교 또는 직장에 있는 IoT 기기를 가능한 한 많이 나열해보세요 - 생각보다 많을 에요!

## 강의 후 퀴즈

[강의 후 퀴즈](https://black-meadow-040d15503.1.azurestaticapps.net/quiz/2)

## 복습 & 자기주도 학습

소비자 IoT 프로젝트의 이점과 실패에 대해 읽어보세요. 뉴스 사이트에서 개인 정보 보호 문제, 하드웨어 문제 또는 연결 부족으로 인한 문제와 같은 잘못된 기사를 확인해보세요.

예시 :

* 트위터 계정 **[Internet of Sh*t](https://twitter.com/internetofshit)** *(profanity warning)* 에서 소비자 IoT의 실폐사례로 좋은 몇가지 예시들을 확인해보세요.
* [c|net - My Apple Watch saved my life: 5 people share their stories](https://www.cnet.com/news/apple-watch-lifesaving-health-features-read-5-peoples-stories/)
* [c|net - ADT technician pleads guilty to spying on customer camera feeds for years](https://www.cnet.com/news/adt-home-security-technician-pleads-guilty-to-spying-on-customer-camera-feeds-for-years/) *(trigger warning - non-consensual voyeurism)*

## 과제

[IoT 프로젝트 조사](assignment.md)