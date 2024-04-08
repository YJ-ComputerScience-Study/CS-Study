## HTTP Keep Alive와 TCP Keep Alive를 설명해 보세요.

HTTP Keep Alive와 TCP Keep Alive 모두 **클라이언트와 서버 간에 연결을 유지하지 위한 방법**입니다.

HTTP Keep Alive는 HTTP 프로토콜의 연결을 **정해진 시간** 동안 유지하는 방식으로, 정해진 **시간이 끝나면 연결을 해제**합니다.

반면 TCP Keep Alive는 3-way 핸드셰이킹으로 연결된 세션을 계속 유지하기 위한 방식으로, **일정 시간 동안 패킷 교환이 없으면 연결 유지 여부를 확인하는 패킷을 던집니다.** 이에 대한 **응답이 있으면 추가로** 일정 시간 동안 **연결을 유지**합니다. 이러한 방식을 통해 클라이언트와 서버 간에 불필요한 연결과 해제의 반복을 줄일 수 있습니다.

`#HTTPKeepAlive정해진시간끝나면연결해제`

`#TCPKeepAlive일정시간패킷교환없으면패킷또던져`

`#칼같은HTTPKeepAlive와한번더기회주는TCPKeepAlive`

> HTTP Keep Alive와 TCP Keep Alive 모두 연결 유지를 위한 개념
>
> But, 각각 다른 계층에서 이뤄져 && 연결 유지 방식 다르다는 점 인지하기
