# String str ="i"와 String str = new String("i")가 동일합니까?

큰따옴표를 사용한 방식은 리터럴 방식입니다. Java는 문자열 리터럴을 Heap 영역 내 String Constant Pool에 저장하며, 이는 동일한 문자열 리터럴이 여러 번 사용될 경우에 재사용이 가능합니다. 따라서 내용이 같다면 동일한 메모리 주소를 가리키게 됩니다.

new 연산자를 사용한 방식은 새로운 String 객체를 힙 메모리에 생성하는 것이며, 같은 값이 String Pool 에 이미 존재하더라도 heap 영역 내 별도의 객체를 가리키게 됩니다.

따라서 “i” 와 new String(”i”) 는 내용은 동일하지만 서로 다른 객체를 참조합니다.