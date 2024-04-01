# HTTP와 HTTPS의 차이점은?


HTTP는 평문 데이터를 전송하는 프로토콜이기 때문에, HTTP로 중요한 정보를 주고 받으면 제 3자에 의해 조회될 수 있습니다. 이러한 문제를 해결하기 위해 HTTP에 암호화가 추가된 프로토콜이 HTTPS입니다. HTTP는 원래 TCP와 직접 통신했지만, HTTPS에서 HTTP는 SSL과 통신하고 SSL이 TCP와 통신함으로써 좀 더 안전하게 데이터를 주고받을 수 있습니다. 

또한, HTTPS 웹 애플리케이션은 HTTP 애플리케이션보다 로드 속도가 더 빠르고 참조 링크를 더 잘 추적합니다. 

※ SSL(Secure Socket Layer): 인터넷을 통해 전달되는 정보를 보호하기 위해 개발한 통신 규약

|  | HTTP | HTTPS |
| --- | --- | --- |
| 의미 | Hypertext Transfer Protocol | Hypertext Transfer Protocol Secure |
| 기본 프로토콜 | HTTP/1과 HTTP/2는 TCP/IP를 사용합니다. HTTP/3은 QUIC 프로토콜을 사용합니다. | HTTP 요청 및 응답을 추가로 암호화하기 위해 SSL/TLS와 함께 HTTP/2 사용 |
| 포트 | 기본 포트 80 | 기본 포트 443 |
| 용도 | 이전 텍스트 기반 웹 사이트 | 모든 최신 웹 사이트 |
| 보안 | 추가 보안 기능 없음 | 퍼블릭 키 암호화에 SSL 인증서 사용 |
| 이점 | 인터넷을 통한 통신 지원 | 웹 사이트에 대한 권위, 신뢰성 및 검색 엔진 순위 개선 |