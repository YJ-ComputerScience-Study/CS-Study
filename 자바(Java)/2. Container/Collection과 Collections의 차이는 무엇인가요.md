## Collection과 Collections의 차이는 무엇인가요?

- **Collection** : java.util.Collection 인터페이스는 **컬렉션 프레임워크의 루트 인터페이스. 여러 요소를 저장하는 데 사용**됨. List, Set, Queue 인터페이스가 이를 상속받음.

  예 :

  - `List` 인터페이스: `ArrayList`, `LinkedList`

  - `Set` 인터페이스: `HashSet`, `TreeSet`
  - `Queue` 인터페이스: `LinkedList`, `PriorityQueue`

- **Collections** : java.util.Collections 클래스는 **컬렉션을 다루기 위한 static 유틸리티 메서드를 제공하는 클래스**. 정렬, 검색, 동기화된 컬렉션 반환 등의 기능을 제공함.

  주요 기능 :

  - 컬렉션 정렬 (`sort`)

  - 컬렉션 검색 (`binarySearch`)
  - 컬렉션 요소 채우기 (`fill`)
  - 컬렉션 복사 (`copy`)
  - 컬렉션 요소 바꾸기 (`swap`)
  - 스레드-안전 컬렉션 생성 (`synchronizedList`, `synchronizedSet`, etc.)
  - 불변 컬렉션 생성 (`unmodifiableList`, `unmodifiableSet`, etc.)

> Collections 클래스는 Collection 인터페이스를 구현한 클래스가 아니다!
