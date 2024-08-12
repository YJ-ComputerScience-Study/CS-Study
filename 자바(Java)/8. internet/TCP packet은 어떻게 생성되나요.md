## TCP packet은 어떻게 생성되나요?

TCP 패킷은 **헤더**와 **데이터**로 구성된다.

헤더는 출발지/목적지 포트, 시퀀스 넘버, 확인 응답(ACK) 번호, 플래그 비트, 창 크기, 체크섬 등의 필드를 포함하며, 이 헤더와 데이터를 묶어 패킷을 생성한다.

### TCP 헤더 구조

![image](https://github.com/user-attachments/assets/168e6174-f0cd-4817-9d94-c2ef384926e5)

### TCP/IP의 데이터 전송과 데이터 단위

![image (1)](https://github.com/user-attachments/assets/66284589-b897-45c4-93c7-156304fd8985)

송신할 때 계층 지날 때마다 각 계층에서 헤더가 붙게 되고, 수신 측은 역순으로 헤더를 분석하게 된다.

### 참고

[쉽게 이해하는 네트워크 11. 인터넷의 TCP/IP 프로토콜과 패킷 교환 방식](https://better-together.tistory.com/110)

[TCP/IP 정리](https://medium.com/@rlatla626/tcp-ip-정리-204e8a986d98)
