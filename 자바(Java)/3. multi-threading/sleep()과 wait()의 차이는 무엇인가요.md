# sleep()과 wait()의 차이는 무엇인가요?

`sleep()`과 `wait()`는 둘 다 스레드를 일시 정지시키는 메서드이지만 차이가 존재합니다. `sleep()`은 일정 시간 대기 동안 다른 작업을 수행할 필요가 있을 때 사용되고, `wait()`는 스레드 간의 동기화 및 통신을 위해 사용됩니다.

`sleep()`은 Thread 클래스의 메서드로, 지정된 시간 동안 스레드를 일시 정지시킵니다. 반면 `wait()`는 Object 클래스의 메서드로, synchronized 블록 안에서 사용되어야 하며 다른 스레드가 `notify()` 또는 `notifyAll()`을 호출할 때까지 스레드를 일시 정지시킵니다. `wait()`는 특정 시간이 지정되지 않은 경우 무한히 기다릴 수 있습니다.