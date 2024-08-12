## 왜 TCP는 3 handshakes를 필요로 하나요? 왜 2개가 아니죠?

3-way handshake는 연결을 설정하기 위해 클라이언트와 서버가 서로 준비 상태임을 확인하고, 데이터 전송을 안전하게 시작하기 위해 필요합니다. 2번의 핸드셰이크는 양쪽의 준비 상태를 충분히 확인하지 못해 신뢰성이 떨어질 수 있습니다.

### 기존 네트워크 공부 내용 참고

[네트워크/4. TCP & UDP/TCP의 연결 및 해제 과정을 설명해 보세요.md](https://github.com/YJ-ComputerScience-Study/CS-Study/blob/main/%EB%84%A4%ED%8A%B8%EC%9B%8C%ED%81%AC/4.%20TCP%20%26%20UDP/TCP%EC%9D%98%20%EC%97%B0%EA%B2%B0%20%EB%B0%8F%20%ED%95%B4%EC%A0%9C%20%EA%B3%BC%EC%A0%95%EC%9D%84%20%EC%84%A4%EB%AA%85%ED%95%B4%20%EB%B3%B4%EC%84%B8%EC%9A%94.md)
