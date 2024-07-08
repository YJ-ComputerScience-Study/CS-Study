# iterator와 listIterator의 차이는 무엇인가요?

ListIterator는 Iterator를 상속받아 기능을 추가한 것입니다. 컬렉션 요소 접근 시 Iterator는 **단방향**으로만 이동하지만, ListIterator는 **양방향** 이동이 가능합니다. 다음 값은 `hasNext()`로, 이전 값은 `hasPrevious()`로 확인할 수 있습니다.