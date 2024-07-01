## ==와 equals의 차이점은 무엇입니까?

- **==** :

  - **기본 데이터 타입**에서는 **값**을 비교

  - **객체 타입**에서는 **메모리 주소**를 비교

- **equals()** :

  - **객체**의 논리적 동등성(**값**)을 비교

  - **메모리 주소**를 비교하는 경우

    - **Object 클래스 기본 구현 사용할 때** (원래 Object 클래스의 equals 메서드는 메모리 주소를 비교함)

  - 대부분의 경우, 표준 라이브러리 클래스나 사용자 정의 클래스에서 Object 클래스의 equals() 메서드를 오버라이드하여 객체의 논리적 동등성(값)을 비교
    대표적인 예 : String, Integer, ArrayList 등의 클래스

엄밀하게 서술하면 기본 데이터 타입의 객체는 Constant Pool의 특정한 값을 참조하는 변수이기에, 결국 Constant Pool 내의 동일한 주소를 비교한다.

# 더 알아보기

## 상수 풀(Constant Pool)이란?

- 자바에서 상수 값을 저장하는 특별한 메모리 영역

- 주로 문자열 상수와 기본 데이터 타입 상수를 저장함
- 자바 컴파일러는 상수 풀을 사용해 동일한 상수를 재사용하고, 메모리 사용을 효율적으로 관리함

## String에서 equals()와 ==

> **결론 : 자바에서 문자열 값 자체를 비교하려면 equals() 메서드 사용해야 한다.** String 클래스 안에 있는 equals 메서드 사용하면 두 비교 대상의 주소값이 아닌 데이터 값을 비교한다.

String 변수를 생성할 때는 두 가지 방법이 있음.

1. 리터럴 선언 : String Constant pool 영역에 존재함. 내부적으로 String의 intern() 메서드 호출되어 주어진 문자열이 String Constant Pool에 존재하는지 확인하고 있으면 그 주소값을 반환하고 없으면 String Constant Pool에 넣고 새로운 주소값을 반환함.

   ```java
   String str1 = "test";
   String str2 = "test";
   ```

2. new 연산자 이용해 선언 : Heap 영역에 존재함.

   ```java
   String str3 = new String("test");
   String str4 = new String("test");
   ```

참고 : [자바에서 equals()와 ==의 차이](https://velog.io/@ilil1/%EC%9E%90%EB%B0%94%EC%97%90%EC%84%9C-equals%EC%99%80-%EC%9D%98-%EC%B0%A8%EC%9D%B4)

## 자바의 기본 데이터 타입(Primitive Data Types)과 객체 타입(Reference Data Types)

### **자바의 기본 데이터 타입** 8개 :

값 자체를 저장함. `==` 연산자를 사용하여 값을 비교할 때 실제 값의 동등성을 비교함.

- **boolean** : true 또는 false 저장

- **byte** : 8비트 정수 (-128 ~ 127)
- **short** : 16비트 정수 (-32768 ~ 32767)
- **int** : 32비트 정수 (-2^31 ~ 2^31-1)
- **long** : 64비트 정수(-2^63 ~ 2^63-1)
- **float** : 32비트 부동 소수점 숫자
- **double** : 64비트 부동 소수점 숫자
- **char** : 16비트 유니코드 문자 (0 ~ 65535)

### **자바의 객체 타입** :

객체의 참조(메모리 주소)를 저장함. `==` 연산자를 사용하여 객체를 비교할 때 참조의 동등성을 비교함. 객체 타입은 여러 가지가 있지만, 대표적인 것은 다음과 같음.

1. **클래스(Class)**

   - 예) String, Integer, Double, UserDefinedClass 등 모든 사용자 정의 클래스와 자바의 표준 클래스

2. **인터페이스(Interface)**
   - 예) List, Map, Runnable 등 자바의 표준 인터페이스 및 사용자 정의 인터페이스
3. **배열(Array)**
   - 예) int[], string[], object[] 등 모든 타입의 배열
4. **열거형(Enum)**
   - 예) enum Days { MONDAY, TUESDAY, WEDNESDAY } 등 사용자가 정의한 열거형 타입
