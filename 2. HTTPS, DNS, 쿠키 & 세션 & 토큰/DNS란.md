# DNS란?

DNS(Domain Name System)란 사용자가 웹브라우저에 사람이 읽을 수 있는 도메인 네임을 컴퓨터가 이해할 수 있는 것으로 매핑하는 것을 말합니다. DNS 서버로 인해 클라이언트는 IP주소를 기억하지 않고 해당 주소의 웹사이트에 접근할 수 있습니다.

DNS의 IP 요청 과정은 다음과 같습니다.

1. 사용자가 브라우저에 www.example.com이라는 도메인을 입력한 뒤 엔터를 누른다.

2. 현재 컴퓨터에 해당 도메인명의 IP가 캐시되어 있거나 C:\Windows\System32\drivers\etc\에 있는 host라는 파일에 있는지 확인하고, 없으면 이 URL은 ISP(Internet Service Provider)가 관리하는 DNS resolver로 전송된다.

3. DNS resolver는 캐싱 여부를 확인하고, 없으면 root 서버에 도메인명을 보내 .com 도메인의 TLD 서버의 IP주소를 알아낸다.

4.  TLD 서버에 다시 URL을 요청하고 모든 도메인 네임에 대한 IP 주소를 가지고 있는 Authrotitative Name Server의 IP를 반환한다.

5. Authrotitative Name Server을 통해 질의 하여 해당 도메인과 매핑되는 DNS 레코드의 IP 주소 정보를 찾아 반환한다.

6. 해당 도메인과 일치하는 IP 주소를 응답 받는다.

7. DNS resolver는 이 IP 주소를 클라이언트에게 다시 전송한다.