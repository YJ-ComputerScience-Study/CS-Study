# runnable과 callable의 차이는 무엇인가요?

Runnable과 Callable은 둘 다 스레드로 실행될 수 있는 작업을 나타내지만 몇 가지 차이점이 있습니다.

Runnable은 `run()` 메서드를 통해 작업을 수행하고, 리턴값이 존재하지 않으며 예외를 던질 수 없습니다. 스레드 실행의 결과를 찾지 않는 상황에 적합합니다. Callable은 `call()` 메서드를 통해 작업을 수행하고, 제네릭 타입의 리턴값이 존재하며 예외를 던질 수 있습니다. 발생 가능한 예외를 미리 선언한다면 예외 처리가 강제되기 때문에 안정성에서 큰 장점이 있습니다.

Runnable은 Thread 클래스 또는 ExecutorService를 사용하여 실행할 수 있지만, Callable은 ExecutorService를 사용해서만 실행할 수 있습니다.