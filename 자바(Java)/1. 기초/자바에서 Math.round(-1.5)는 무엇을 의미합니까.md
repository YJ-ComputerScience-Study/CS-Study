## 자바에서 Math.round(-1.5)는 무엇을 의미합니까?

**Math.round(-1.5)** 는 -1을 의미합니다.

### Math.round() 메서드

- 소수점 이하의 값을 반올림하여 가장 가까운 정수로 반환함.

  - 양수 : 소수점 이하가 0.5 이상이면 올림

  - 음수 : 소수점 이하가 0.5 이하이면 버림

```java
public class Main {
    public static void main(String[] args) {
        System.out.println(Math.round(1.4));  // 1
        System.out.println(Math.round(1.5));  // 2
        System.out.println(Math.round(1.6));  // 2

        System.out.println(Math.round(-1.4)); // -1
        System.out.println(Math.round(-1.5)); // -1
        System.out.println(Math.round(-1.6)); // -2
    }
}
```
