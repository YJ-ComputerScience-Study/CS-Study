# ArrayList와 Vector의 차이점을 말해주세요.

ArrayList와 Vector는 크기가 동적인 배열이 필요할 때 주로 사용되는데, 몇 가지 차이가 있습니다.

1. **동기화**
    
    Vector는 동기화가 가능하지만, ArrayList는 동기화가 되지 않습니다. 따라서 ArrayList는 Vector와 다르게 동시에 여러 스레드가 작업할 수 있고, 이때 개발자가 명시적으로 동기화하는 코드를 추가해 주어야 합니다.
    
2. **스레드 안전(Thread-Safe)**
    
    스레드 안전이란, multi thread programming에서 여러 스레드가 동시에 접근하여도 프로그램 실행에 문제가 없는 것을 말합니다. Vector는 동기화가 가능하기에 thread-safe합니다.
    
3. **성능**
    
    동기화되지 않는 ArrayList가 동기화되는 Vector보다 더 빠릅니다.
    
4. **최대 인덱스 초과 시 추가되는 인덱스 수**
    
    ArrayList와 Vector는 모두 동적 배열 클래스이지만 최대 인덱스 초과 시 추가되는 인덱스 수에 차이가 있습니다. Vector는 현재 배열 크기의 100%, ArrayList는 현재 배열 크기의 50%가 추가됩니다.