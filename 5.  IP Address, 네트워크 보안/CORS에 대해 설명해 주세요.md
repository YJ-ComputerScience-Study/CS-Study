# CORS에 대해 설명해 주세요.

CORS란 Cross-Origin Resource Sharing의 줄임말로, 한국어로는 교차-출처 리소스 공유라고 합니다. 여기서 출처란 Protocol, Host, 포트번호를 의미하고, 웹에서 다른 출처로 리소스를 요청할 때 브라우저는 Origin이라는 필드에 요청을 보내는 출처를 담아서 보냅니다.  

이후 서버가 이 요청에 대한 응답을 할 때, 응답 헤더의 Access-Control-Allow-Origin이라는 값에 이 리소스에 접근하는 것이 허용된 출처를 같이 보내주고, 응답을 받은 브라우저는 자신이 보낸 Origin과 서버가 보내준 응답의 Access-Control-Allow-Origin을 비교한 후 응답이 유효한지 판별합니다.