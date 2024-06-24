# Java의 HashMap과 HashTable의 차이에 대해 설명하세요.

HashTable의 put 메소드에는 HashMap의 put 메소드와 달리 synchronized 키워드가 붙어 있어, 병렬 프로그래밍을 할 때 동기화를 지원합니다. 이는 해당 함수를 처리하는 시간이 조금 지연됨을 의미합니다. 따라서 병렬 처리를 하며 자원의 동기화를 고려해야 하는 상황에서는 HashTable, 그렇지 않은 상황에서는 HashMap을 사용하는 것이 좋습니다.

또한, HashMap은 보조해시를 사용하기 때문에 보조해시 함수를 사용하지 않는 HashTable에 비하여 해시 충돌이 덜 발생할 수 있다는 점에서 상대적으로 성능상 이점이 있습니다. 
