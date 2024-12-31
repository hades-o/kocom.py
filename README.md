# Hass.io Add-on: Kocom Wallpad with RS485 

![Supports aarch64 Architecture][aarch64-shield] ![Supports amd64 Architecture][amd64-shield] ![Supports armhf Architecture][armhf-shield] ![Supports armv7 Architecture][armv7-shield] ![Supports i386 Architecture][i386-shield]

## About
Kocom Wallpad with RS485

## Installation

1. 홈어시스턴트의 Hass.io > ADD-ON STORE에서 Add new repository by URL에 https://github.com/hades-o/kocom.py 를 입력한 다음 ADD 버튼을 누릅니다.
2. ADD-ON STORE 페이지 하단에서 "Kocom Wallpad with RS485" 클릭합니다.
3. "INSTALL" 버튼을 누르면 애드온이 설치됩니다. 최대 약 10분 정도 소요. 
4. INSTALL 버튼위에 설치 애니메이션이 동작하는데 이것이 멈추더라도 REBUILD, START 버튼이 나타나지 않는 경우가 있습니다.
5. 이 애드온은 이미지를 내려받는 것이 아니라 직접 여러분의 Hassio에서 이미지를 만듭니다.
6. INSTALL 버튼을 누른다음 설치 애니메이션이 실행되면 제대로 설치중인 것입니다.
7. share/kocom/ 폴더에 있는 kocom.conf 파일을 본인의 환경에 맞게 수정합니다.
8. "START" 버튼으로 애드온을 실행합니다.

만일 kocom.py 파일을 수정하시려면 한번 실행한 후 애드온을 Stop 하시고
share/kocom/ 폴더에 있는 파일을 알맞게 수정하신 다음에
애드온을 Start 하시면 이후부터는 수정된 파일을 적용합니다.

## Change log

(2024-03-12 수정) paho-mqtt-2.0.0 대응

(2022-07-24 수정) config.json을 config.yaml로 변환

(2022-04-10 수정) MQTT Discovery 지원

(2022-03-30 수정) Home Assistant Supervisor Add-on에서 실행되도록 수정

(2022-03-29 수정) 전열교환기(Fan) 프리셋모드 추가 및 초기모드 사용자 설정, 난방 초기온도 사용자 설정

-------------------------------------------------------------------------------------

(2020.9.25 수정) 엘리베이터 도착정보 추가, minor changes

(2019.12.9 수정) github 개설, serial 강제 종료시 error handling

(2019.11.19 수정) 패킷발송 후 기기상태 수신시까지 다음패킷 발송않도록 처리, 충돌시 random jump, 패킷타이밍 튜닝기능(read_write_gap변수)

(2019.11.18 추가수정) 연결 시작시에도 패킷충돌 감지, fan command오류수정

(2019.11.18 수정) polling 도중 command 발생시 간헐적 충돌 해결

(2019.11.17 수정) RS485연결 또는 mqtt연결이 끊어졌을 때 예외처리/자동복구, RS485 read/write 패킷충돌 방지

(2019.11.15 수정) 하나의 파이썬코드 kocom.py로 serial 및 socket 둘 다 지원하도록 바꿨습니다. kocom.conf에서 serial로 할지 socket으로 할지 등등 설정하시면 됩니다. 

(2019.11.14 수정) Rese님이 지적하신 mqtt log 오류 수정

(2019.11.13오후 수정) Rese님 요청으로, socket용 draft version도 올립니다. (압축파일 내 kocom.py를 대체하세요) serial 연결부분을 socket 연결로 바꾸고, read()-->recv(1), write()-->send()로만 딱 변경했습니다. ser2net python파일로 1분간 작동유무만 테스트하여, 장기적인 안정성은 테스트되지 않았습니다. python 소스코드 내에 소켓 연결할 ip/port 를 기입하도록 되어있으니 수정하셔서 사용하시면 됩니다.

(2019.11.13수정) checksum 을 계산하다보니 아무래도 header는 aa55까지인 것 같습니다. 다시 수정하였습니다. python 소스코드도 수정되었습니다

[forum]: https://cafe.naver.com/koreassistant
[github]: https://github.com/clipman/kocom.py
[aarch64-shield]: https://img.shields.io/badge/aarch64-yes-green.svg
[amd64-shield]: https://img.shields.io/badge/amd64-yes-green.svg
[armhf-shield]: https://img.shields.io/badge/armhf-yes-green.svg
[armv7-shield]: https://img.shields.io/badge/armv7-yes-green.svg
[i386-shield]: https://img.shields.io/badge/i386-yes-green.svg
