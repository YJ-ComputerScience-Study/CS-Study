## throw와 throws의 차이는 무엇인가요?

|      | throw                   | throws                                        |
| ---- | ----------------------- | --------------------------------------------- |
| 용도 | 특정 예외를 발생시킬 때 | 메서드가 특정 예외를 던질 수 있음을 선언할 때 |
| 위치 | 메서드 내부             | 메서드 선언부                                 |

### throw 예시

```java
public void checkAge(int age) {
    if (age < 18) {
        throw new IllegalArgumentException("Age must be at least 18.");
    }
}
```

### throws 예시

```java
public void readFile(String filePath) throws IOException {
    // Method implementation
}
```
