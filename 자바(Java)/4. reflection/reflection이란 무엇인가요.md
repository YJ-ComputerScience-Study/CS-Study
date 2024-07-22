## reflection이란 무엇인가요?

**reflection(리플렉션)** : **구체적인 클래스 타입을 알지 못하더라도 그 클래스의 메서드, 타입, 변수들에 접근할 수 있도록 해주는 자바 API**

- 컴파일 시간이 아닌 실행 시간에 동적으로 특정 클래스의 정보를 추출할 수 있는 프로그래밍 기법이라 할 수 있다.

## 더 알아보기

### reflection 장점

- 런타임에 동적 로딩과 동적 객체 생성이 가능하여 유연한 코드를 작성할 수 있다.

- 클래스의 내부 구현에 대한 정보를 얻을 수 있어, IDE 플러그인 개발이나 프레임워크 개발에 유용하다.

### reflection 단점

- 성능이 저하될 수 있다. 컴파일 타임에 결정되는 게 아니라 런타임에 결정되기 때문에 일반적인 메서드 호출보다 느리다.

- 안전하지 않을 수 있으며, 보안 문제를 야기할 수 있다.

### reflection의 주요 기능

- 클래스 정보 조사 : 클래스의 이름, 슈퍼 클래스, 인터페이스 등의 정보를 확인할 수 있다.

- 필드 접근 및 수정 : 클래스의 필드 값을 가져오거나 수정할 수 있다.
- 메서드 호출 : 클래스의 메서드를 동적으로 호출할 수 있다.
- 생성자 호출 : 클래스를 인스턴스화할 수 있다.
- 어노테이션 확인 : 클래스나 메서드에 사용된 어노테이션을 확인할 수 있다.

### reflection 사용 예제

ExampleClass의 정보를 탐색하고, 특정 메서드를 호출하는 방법을 보여주는 예제이다.

#### 예제 클래스 정의

```java
public class ExampleClass {
    private String name;
    private int value;

    public ExampleClass() {
        this.name = "Default";
        this.value = 0;
    }

    public ExampleClass(String name, int value) {
        this.name = name;
        this.value = value;
    }

    public void printInfo() {
        System.out.println("Name: " + name + ", Value: " + value);
    }

    private void privateMethod() {
        System.out.println("This is a private method.");
    }

    // Getters and Setters
    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public int getValue() {
        return value;
    }

    public void setValue(int value) {
        this.value = value;
    }
}

```

#### Reflection을 적용해보자

```java
import java.lang.reflect.Constructor;
import java.lang.reflect.Field;
import java.lang.reflect.Method;

public class ReflectionExample {
    public static void main(String[] args) {
        try {
            // ExampleClass에 대한 클래스 객체를 가져온다.
            Class<?> clazz = Class.forName("ExampleClass");

            // 클래스 이름 출력
            System.out.println("Class Name: " + clazz.getName());

            // 클래스의 필드 출력
            System.out.println("\nFields:");
            Field[] fields = clazz.getDeclaredFields();
            for (Field field : fields) {
                System.out.println(field.getName() + " - Type: " + field.getType());
            }

            // 클래스의 생성자 출력
            System.out.println("\nConstructors:");
            Constructor<?>[] constructors = clazz.getConstructors();
            for (Constructor<?> constructor : constructors) {
                System.out.println(constructor);
            }

            // 클래스의 메서드 출력
            System.out.println("\nMethods:");
            Method[] methods = clazz.getDeclaredMethods();
            for (Method method : methods) {
                System.out.println(method.getName() + " - Return Type: " + method.getReturnType());
            }

            // 인스턴스 생성
            Constructor<?> constructor = clazz.getConstructor(String.class, int.class);
            Object exampleInstance = constructor.newInstance("ExampleName", 42);

            // printInfo 메서드 호출
            Method printInfoMethod = clazz.getMethod("printInfo");
            printInfoMethod.invoke(exampleInstance);

            // private 메서드 접근
            Method privateMethod = clazz.getDeclaredMethod("privateMethod");
            privateMethod.setAccessible(true); // 접근 허용
            privateMethod.invoke(exampleInstance);

        } catch (Exception e) {
            e.printStackTrace();
        }
    }
}

```

- 클래스 객체 가져오기 : `Class.forName("ExampleClass")`

- 필드 탐색 : `getDeclaredFields()`
- 생성자 탐색 : `getConstructors()`
- 메서드 탐색 : `getDeclaredMethods()`
- 인스턴스 생성 : Reflection의 `Constructor` 객체를 통해 클래스의 인스턴스를 생성. 이때 적절한 생성자 선택해야 함.
- 메서드 호출 : `getMethod()`
- 프라이빗 메서드 호출 : `getDeclaredMethod()` 사용해 프라이빗 메서드에 접근하고, `setAccessible(true)` 을 통해 접근 허용한 후 메서드를 호출
- 메서드를 실제로 실행 : `invoke()`

> Reflection은 강력한 도구이지만 신중하게 사용해야 하며, 필요한 경우에만 사용하도록 권장됨.
