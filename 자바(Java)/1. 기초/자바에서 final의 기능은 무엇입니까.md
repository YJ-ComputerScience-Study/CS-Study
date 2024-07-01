## 자바에서 final의 기능은 무엇입니까?

final은 크게 변수, 메서드, 클래스에 사용할 수 있음.

- final 변수 : **재할당**할 수 없음(초기화 후 값을 변경할 수 없는 상수 정의에 사용)

- final 메서드 : **오버라이드**될 수 없음
- final 클래스 : **상속**할 수 없음(부모 클래스가 될 수 없음)

## 더 알아보기

### final 변수에 초기값 설정하는 방법 2가지

1. **클래스의 필드에 선언**(상수의 형태로 사용하게 됨)

   상수의 경우, 보통 접근제어자(private 또는 public)와 static 키워드를 함께 사용 `private(public) static final`

   - static 사용하면 컴파일 타임에 메모리 할당을 1번 해서 효율성 측면에서 좋음

   ```java
   class Car {
       private static final int MOVE_STEP = 1;
       // ...
   }
   ```

2. **생성자에서 초기화**

   ```java
   class Car {
       private final int position;

       Car() {
           this.position = 0;
       }
   }
   ```

### final 메서드는 언제 사용하는가?

- 코어 부분에서 변경을 원치 않는 메서드를 명시할 때

### final 클래스 대표 예시?

- java.lang 패키지의 String 클래스

  ![String 클래스](https://github.com/YJ-ComputerScience-Study/CS-Study/assets/49242646/583abe36-05fb-4504-a908-61229b1843f8)

### final은 불변을 의미하는가?

- 안타깝게도 final을 사용하는 것이 완벽한 불변성을 의미하진 않음.

- **final은 해당 변수의 재할당만을 막아줄 뿐**, 참조하고 있는 객체 내부의 상태가 변하지 않았음을 보장해주지는 않음.

  ```java
  final List<Integer> numbers = new ArrayList<>(Arrays.asList(1, 2, 3));
  System.out.println(numbers); // [1, 2, 3]

  numbers.add(4);
  System.out.println(numbers); // [1, 2, 3, 4]
  ```

### 참고

[Java 에서 final 키워드 사용하기](https://hudi.blog/java-final/)
