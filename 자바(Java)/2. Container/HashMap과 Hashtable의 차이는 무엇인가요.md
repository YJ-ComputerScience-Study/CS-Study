## HashMap과 Hashtable의 차이는 무엇인가요?

- **HashMap** (동기화 보장 X)

  - **비동기적 (thread-safe하지 않음)**

  - null 키와 null 값을 허용
  - 성능이 더 좋음

- **Hashtable** (동기화 보장)

  - **동기적 (thread-safe)**

  - null 키와 null 값을 허용하지 않음
  - 성능이 상대적으로 떨어짐

<br>

# 더 알아보기

## HashMap과 Hashtable의 공통점은?

> Map 인터페이스 구현, 둘 다 해시 테이블 기반

- 둘 다 **java.util.Map 인터페이스를 구현**하고 있고, 두 클래스 모두 **해시 테이블**을 기반으로 구현되어 있음. 내부적으로는 배열과 연결 리스트 또는 트리를 사용해 충돌 처리함.

- **키-값 쌍을 저장**하고 **관리**하는 데 사용됨.
- 기본적인 메서드

  - put(K key, V value) : 키와 값을 추가하거나 업데이트

  - get(Object key) : 키에 매핑된 값을 반환
  - remove(Object key) : 키에 매핑된 값을 제거
  - containsKey(Object key) : 키가 존재하는지 확인
  - containsValue(Object value) : 값이 존재하는지 확인
  - size() : 저장된 키-값 쌍의 개수 반환
  - isEmpty() : 비어 있는지 확인
  - keySet() : 모든 키를 반환
  - values() : 모든 값을 반환
  - entrySet() : 모든 키-값 쌍을 반환

## 요즘은 언제 무엇을 쓰나요?

> Hashtable보단 ConcurrentHashMap을 쓴다.

현대적인 코드에서는 일반적으로

- 스레드 안전이 필요하지 않은 경우, **HashMap** 사용

- 스레드 안전이 필요한 경우, **ConcurrentHashMap** 사용

  - ConcurrentHashMap : 동시성 지원 + 성능도 최적화됨. 여러 스레드가 동시에 데이터를 읽고 쓸 수 있도록 설계됨.

Hashtable은 주로 레거시 코드에서만 사용됨.
