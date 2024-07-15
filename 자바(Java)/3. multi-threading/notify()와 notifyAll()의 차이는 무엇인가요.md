## notify()와 notifyAll()의 차이는 무엇인가요?

- **notify()** : **대기 중인 스레드 중 하나**를 깨운다.

  - 어떤 스레드가 깨어날지는 JVM의 구현에 따라 달라질 수 있다.

- **notifyAll()** : **대기 중인 모든 스레드**를 깨운다. 모든 스레드가 깨어나서 다시 경쟁하게 된다.

## 더 알아보기

### notify()와 notifyAll() 공통점

- 자바에서 스레드 간의 통신을 위해 사용되는 메서드

- wait()와 함께 사용됨
- 이들 메서드는 동기화된 블록 내에서 호출되어야 하고, 특정 객체의 모니터를 사용해 대기 중인 스레드를 깨우는 역할을 함.

### notify() 예시 코드

- notify() : WaitingThread1과 WaitingThread2 중 하나의 스레드만 깨움. 깨우는 스레드는 JVM에 의해 임의로 선택됨.

  ```java
  public class NotifyExample {
      private static final Object lock = new Object();

      public static void main(String[] args) {
          Thread waitingThread1 = new Thread(new WaitingRunnable(), "WaitingThread1");
          Thread waitingThread2 = new Thread(new WaitingRunnable(), "WaitingThread2");
          Thread notifyingThread = new Thread(new NotifyingRunnable(), "NotifyingThread");

          waitingThread1.start();
          waitingThread2.start();

          try {
              Thread.sleep(1000); // WaitingThreads가 먼저 실행되도록 잠시 대기
          } catch (InterruptedException e) {
              e.printStackTrace();
          }

          notifyingThread.start();
      }

      static class WaitingRunnable implements Runnable {
          @Override
          public void run() {
              synchronized (lock) {
                  System.out.println(Thread.currentThread().getName() + " 대기 시작");
                  try {
                      lock.wait();
                  } catch (InterruptedException e) {
                      e.printStackTrace();
                  }
                  System.out.println(Thread.currentThread().getName() + " 대기 종료");
              }
          }
      }

      static class NotifyingRunnable implements Runnable {
          @Override
          public void run() {
              synchronized (lock) {
                  System.out.println(Thread.currentThread().getName() + " 알림 시작");
                  lock.notify(); // 대기 중인 스레드 중 하나를 깨움
                  System.out.println(Thread.currentThread().getName() + " 알림 종료");
              }
          }
      }
  }

  ```

### notifyAll() 예시 코드

- notifyAll() : WaitingThread1과 WaitingThread2를 포함하여 대기 중인 모든 스레드를 깨움.

  ```java
  public class NotifyAllExample {
      private static final Object lock = new Object();

      public static void main(String[] args) {
          Thread waitingThread1 = new Thread(new WaitingRunnable(), "WaitingThread1");
          Thread waitingThread2 = new Thread(new WaitingRunnable(), "WaitingThread2");
          Thread notifyingThread = new Thread(new NotifyingRunnable(), "NotifyingThread");

          waitingThread1.start();
          waitingThread2.start();

          try {
              Thread.sleep(1000); // WaitingThreads가 먼저 실행되도록 잠시 대기
          } catch (InterruptedException e) {
              e.printStackTrace();
          }

          notifyingThread.start();
      }

      static class WaitingRunnable implements Runnable {
          @Override
          public void run() {
              synchronized (lock) {
                  System.out.println(Thread.currentThread().getName() + " 대기 시작");
                  try {
                      lock.wait();
                  } catch (InterruptedException e) {
                      e.printStackTrace();
                  }
                  System.out.println(Thread.currentThread().getName() + " 대기 종료");
              }
          }
      }

      static class NotifyingRunnable implements Runnable {
          @Override
          public void run() {
              synchronized (lock) {
                  System.out.println(Thread.currentThread().getName() + " 알림 시작");
                  lock.notifyAll(); // 대기 중인 모든 스레드를 깨움
                  System.out.println(Thread.currentThread().getName() + " 알림 종료");
              }
          }
      }
  }

  ```

### 더 안전한 방법?

일반적으로 notifyAll()이 더 안전한 방법으로 간주되며, 교착 상태(deadlock) 방지에 유용.
