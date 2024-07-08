# Queue에서, `poll()`과 `remove()`의 차이는 무엇인가요?

Queue에서 `poll()`과 `remove()`는 둘 다 데이터를 삭제하는 메서드이지만 큐가 비어 있을 시 동작에 차이가 있습니다.

`queue.poll()`과 `queue.remove()`는 큐의 **첫 번째** 요소를 **삭제 및 반환**합니다. 이때 큐가 비어 있다면 `queue.poll()`은 **null을 반환**하는 반면, `queue.remove()`는 **예외가 발생**합니다.