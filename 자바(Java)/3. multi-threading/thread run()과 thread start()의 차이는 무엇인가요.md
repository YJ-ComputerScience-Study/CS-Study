## thread run()과 thread start()의 차이는 무엇인가요?

- **run()** : 스레드의 작업을 정의하는 메서드로, 직접 호출하면 일반 메서드 호출과 다르지 않습니다. 싱글 스레드로 동작합니다.

- **start()** : **새로운 스레드를 생성**하고, 이 새로운 스레드에서 내부적으로 run() 메서드를 호출합니다. 멀티 스레드로 동작합니다.

### 표로 정리하는 run() vs start()

| `run()`                                                                         | `start()`                                                                    |
| ------------------------------------------------------------------------------- | ---------------------------------------------------------------------------- |
| Thread가 생성되지 않으며, 메서드를 호출한 스레드에서 그냥 run() 메서드만 실행됨 | native 영역에서 새로운 Thread가 생성되며 그 스레드에서 run() 메서드가 실행됨 |
| 호출 수에 제한없이 계속 호출할 수 있음                                          | 동일한 객체에서 두 번 이상 호출 시 IllegalThreadStateException 예외가 발생됨 |
| 싱글 스레드로 동작함(병렬 실행 x)                                               | 멀티 스레드로 동작함(병렬 실행 o), 스레드가 독립적으로 실행됨                |

## 더 알아보기

### run()과 start() 공통점

- **Thread 클래스의 메서드**로 스레드와 관련된 작업을 처리함.

- **Runnable 인터페이스를 구현한 객체와 함께 사용**됨. Runnable 인터페이스는 run() 메서드를 하나 갖고 있으며, 스레드가 실행할 작업을 정의함.
- 스레드가 실행할 코드를 지정하는 데 사용됨.

### run() 예시 코드

```java
public class RunExample {
    public static void main(String[] args) {
        Thread thread = new Thread(new Runnable() {
            @Override
            public void run() {
                System.out.println("run() 메서드 호출");
            }
        });

        thread.run(); // 직접 run() 메서드를 호출
        System.out.println("메인 스레드에서 실행");
    }
}
```

출력 :

순차적으로 "run() 메서드 호출"과 "메인 스레드에서 실행"이 된다.

### start() 예시 코드

```java
public class StartExample {
    public static void main(String[] args) {
        Thread thread = new Thread(new Runnable() {
            @Override
            public void run() {
                System.out.println("run() 메서드 호출");
            }
        });

        thread.start(); // 새 스레드를 시작하고 run() 메서드를 호출
        System.out.println("메인 스레드에서 실행");
    }
}
```

출력 :

"메인 스레드에서 실행"과 "run() 메서드 호출"이 병렬로 실행될 수 있으며, 실행 순서는 JVM 스케줄러에 의해 결정된다.
