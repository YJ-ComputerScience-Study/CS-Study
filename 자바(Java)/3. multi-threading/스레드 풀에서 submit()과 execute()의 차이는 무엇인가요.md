## 스레드 풀에서 submit()과 execute()의 차이는 무엇인가요?

- **submit()** :

  - **Runnable 또는 Callable 작업을 수행**하며, **Future 객체**를 반환함.

  - 실행 중 예외가 발생하면, 예외가 Future.get() 메서드를 호출할 때 발생함.

- **execute()** :

  - **Runnable 작업을 수행**하며, **반환 값이 없음.**

  - 실행 중 예외가 발생하면, 예외가 Thread의 uncaughtExceptionHandler에 전달됨.

## 사용 예시

```java
import java.util.concurrent.*;

public class ExecutorExample {
    public static void main(String[] args) {
        ExecutorService executor = Executors.newFixedThreadPool(2);

        // execute() 사용 예제 (Runnable 작업)
        executor.execute(new RunnableTask());

        // submit() 사용 예제 (Runnable 작업)
        Future<?> runnableFuture = executor.submit(new RunnableTask());

        // submit() 사용 예제 (Callable 작업)
        Future<Integer> callableFuture = executor.submit(new CallableTask());

        try {
            // Future 객체로부터 결과를 가져옴
            runnableFuture.get();  // Runnable 작업의 경우 결과는 null입니다.
            Integer result = callableFuture.get();
            System.out.println("Result from CallableTask: " + result);
        } catch (InterruptedException | ExecutionException e) {
            e.printStackTrace();
        }

        executor.shutdown();
    }
}

// Runnable 구현
class RunnableTask implements Runnable {
    @Override
    public void run() {
        System.out.println("RunnableTask is running.");
    }
}

// Callable 구현
class CallableTask implements Callable<Integer> {
    @Override
    public Integer call() throws Exception {
        System.out.println("CallableTask is running.");
        return 42; // 작업 결과 반환
    }
}

```

### submit()과 execute()의 공통점

- ExecutorService 인터페이스의 메서드로, 스레드 풀에 작업을 제출할 때 사용됨.

### Future 객체

- Java에서 비동기적 연산 작업을 위해 만들어진 인터페이스.

- 비동기 처리가 완료되었는지 확인하고, 처리 완료를 기다리고, 처리 결과를 반환하는 메서드를 제공함.
