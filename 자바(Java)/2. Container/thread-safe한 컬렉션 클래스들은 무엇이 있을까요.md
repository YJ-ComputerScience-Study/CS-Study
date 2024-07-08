# thread-safe한 컬렉션 클래스들은 무엇이 있을까요?

thread-safe한 Collection에는 크게 **Synchronized Collection**과 **Concurrent Collection**이 존재합니다.

### Synchronized Collection (동기화 컬렉션)

내부적으로 메서드에 **synchronized 키워드**가 걸려 있기 때문에 한 번에 한 스레드만 내부의 값 사용이 가능합니다.

| 컬렉션 종류 | 컬렉션 |
| --- | --- |
| List | Vector |
| Map | HashTable |
| Collections.synchronizedXXX | synchronizedHashMap, HashSet, ArrayList….. |

### Concurrent Collection (병렬 컬렉션)

**변수에 접근하는 통로를 일련화**시켜 스레드 안전성을 확보합니다.


| 컬렉션 종류 | 컬렉션 |
| --- | --- |
| List | CopyOnWriteArrayList |
| Map | ConcurrentMap, ConcurrentHashMap |
| Set | CopyOnWriteArraySet |
| SortedMap | ConcurrentSkipListMap |
| SortedSet | ConcurrentSkipListSet |
| Queue | BlockingQueue, ConcurrentLinkedQueue |

---

#### 추가 설명

##### ConcurrentHashMap

동기화 컬렉션에서는 모든 연산에서 **단 하나의 락**을 사용하여 한 시점에 하나의 스레드만이 해당 컬렉션을 사용할 수 있도록 하였습니다.

ConcurrentHashMap은 **Lock Striping**을 사용하여, 동기화 컬렉션에 비해 **높은 동시성**을 보장합니다.

- Lock Striping: 컬렉션 데이터를 여러 개의 범위로 나누어, 각 범위마다 특정 락이 담당하도록 하는 것
    - 서로 영향을 주지 않는 작업에 대해 경쟁이 일어나지 않으므로 여러 스레드에서 동시 접근 가능, 락 획득을 위한 대기 시간 감소

##### CopyOnWriteArrayList

쓰기 작업 시 **명시적 락**을 사용합니다. 컬렉션 값이 변경되는 시점마다 원본 배열에 있는 요소의 복사본을 새로 만들고, 이 복사본에 변경 작업 수행 후 원본 배열을 갱신합니다.

읽기 작업엔 락이 걸리지 않습니다.