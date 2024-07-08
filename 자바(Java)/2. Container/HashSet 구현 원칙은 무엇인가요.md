## HashSet 구현 원칙은 무엇인가요?

Set 인터페이스를 구현하는 HashSet은 **내부적으로 HashMap을 사용**하여 요소의 고유성을 유지하고, 빠른 삽입, 삭제, 검색을 제공합니다.

각 요소는 HashMap의 키로 저장되고, 값은 고정된 객체(`PRESENT`)로 설정됩니다. 이로 인해 중복된 요소가 들어오면 기존 키가 덮어쓰여져서 중복된 요소를 자동으로 제거할 수 있습니다.

- `PRESENT`는 HashSet의 내부에 있는 HashMap의 Value에 들어가는 Dummy값

### HashSet이 HashMap을 사용해 구현되는 이유?

고유성 유지, 효율적인 데이터 관리를 위해서.

HashMap의 키의 고유성을 이용해 Set의 특성을 구현함.
