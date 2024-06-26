## NoSQL이 무엇인지 관계형 데이터베이스와 비교해 설명해 보세요.

NoSQL은 **비관계형 데이터베이스**로, 2차원 형태의 관계형 데이터베이스보다 **유연한 데이터 구조**를 가질 수 있습니다. 그래서 **도큐먼트, 키-값, 그래프 등 다양한 형태로 데이터를 저장**할 수 있습니다. 또한, 서버 증설을 통한 데이터베이스 확장이 가능해서 **방대한 양의 데이터를 저장하는 데 유리**합니다. 하지만 **중복 데이터를 허용**하므로 데이터를 **갱신하는 경우** 관계형 데이터베이스보다 **처리 비용이 많이 든다**는 단점이 있습니다.

`#NoSQL비관계형DB`

`#유연한데이터구조(도큐먼트,키-값,그래프 등)`

`#방대한데이터저장에유리but중복데이터허용이라갱신할경우처리비용많이듦`

## 관계형 DB vs NoSQL DB

| 구분        | 관계형 데이터베이스                   | NoSQL 데이터베이스                                           |
| ----------- | ------------------------------------- | ------------------------------------------------------------ |
| 데이터 저장 | 2차원 테이블로 저장                   | 분산형 구조로, 도큐먼트, 키-값, 그래프 등 다양한 형태로 저장 |
| 데이터 중복 | 중복 없음                             | 중복 데이터가 있어서 데이터 갱신 시 이를 처리해야 함         |
| 스키마      | 스키마가 있어서 데이터의 무결성 보장  | 스키마가 없고 유연한 데이터 처리 가능                        |
| 데이터 확장 | 수직적 확장 지원(서버 자체 성능 향상) | 수평적 확장 지원(분산형으로 서버 추가)                       |
| DBMS        | Oracle, MySQL, SQLite                 | MongoDB                                                      |
