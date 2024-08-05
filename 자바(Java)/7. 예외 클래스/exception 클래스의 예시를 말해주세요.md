## exception 클래스의 예시를 말해주세요.

- Checked Exception : `IOException`, `SQLException`, `FileNotFoundException`

- Unchecked Exception (RuntimeException) : `NullPointerException`, `ArrayIndexOutOfBoundsException`, `IllegalArgumentException`

### 표로 정리한 Exception 클래스

| Exception 클래스               | 설명                                                            |
| ------------------------------ | --------------------------------------------------------------- |
| **Checked Exceptions**         |                                                                 |
| IOException                    | 입출력 작업 중 발생하는 예외                                    |
| FileNotFoundException          | 파일을 찾을 수 없을 때 발생하는 예외                            |
| ClassNotFoundException         | 클래스 파일을 찾을 수 없을 때 발생하는 예외                     |
| SQLException                   | 데이터베이스 작업 중 발생하는 예외                              |
| InterruptedException           | 스레드가 작업 도중 인터럽트될 때 발생하는 예외                  |
| **Unchecked Exceptions**       |                                                                 |
| ArrayIndexOutOfBoundsException | 배열에 잘못된 인덱스를 사용하여 접근할 경우                     |
| NullPointerException           | null 객체의 인스턴스 메소드를 호출하는 등의 경우                |
| ArithmeticException            | 산술 연산에서 정수를 0으로 나누는 등 연산을 수행할 수 없는 경우 |
| IllegalArgumentException       | 메서드에 잘못된 인자를 전달할 때 발생하는 예외                  |
| IllegalStateException          | 메서드를 호출할 수 없는 상태일 때 발생하는 예외                 |
| NumberFormatException          | 문자열을 숫자로 변환할 때 발생하는 예외                         |
| NoSuchElementException         | 요청한 요소가 존재하지 않을 때 발생하는 예외                    |
| UnsupportedOperationException  | 메서드가 지원되지 않는 경우 발생하는 예외                       |
| IndexOutOfBoundsException      | 인덱스가 범위를 벗어날 때 발생하는 예외                         |
| RuntimeException               | 모든 런타임 예외의 상위 클래스                                  |

# 더 알아보기

자바의 예외는 크게 3가지로 나눌 수 있음 : 체크 예외, 에러, 언체크 예외

![image](https://github.com/user-attachments/assets/e7689197-e72d-41af-a655-923bb9b56ac0)

- 에러 : 시스템에 비정상적인 상황 발생할 때임. ex) 메모리 부족, 스택오버플로우

- 예외 : 프로그램 실행 중 개발자의 실수로 예기치 않은 상황 발생할 때임.

  - 체크 예외는 반드시 예외 처리(try/catch or throw) 해야 함

  - 언체크 예외는 예외 처리를 강제하지 않음
    ![image](https://github.com/user-attachments/assets/a8defc13-4c3f-46f2-8e19-7b3256c10593)

### 참고

[[Java] Checked Exception vs Unchecked Exception 정리](https://devlog-wjdrbs96.tistory.com/351)
