# String 클래스의 일반적인 메소드는 무엇이 있나요?

String 클래스에는 문자열 조작을 위한 여러 메소드가 존재합니다.

- `charAt()` 메소드: 해당 문자열의 특정 인덱스에 해당하는 문자를 반환합니다. 만약 문자열의 길이보다 큰 인덱스 값이나 음수를 전달한다면 오류가 발생합니다.
    
    ```java
    String str = new String("Java");
    System.out.println(str); // Java
    System.out.println(str.charAt(0)); // J
    System.out.println(str.charAt(2)); // v
    ```
    
- `compareTo()` 메소드: 해당 문자열을 인수로 전달된 문자열과 사전순으로 비교합니다. 비교할 때는 대소문자를 구분합니다. 두 문자열이 같다면 0, 해당 문자열이 인수로 전달된 문자열보다 작다면 음수, 크면 양수를 반환합니다.
    - 대소문자 구분 없이 비교할 때는 `compareToIgnoreCase()` 메소드를 사용합니다.
    
    ```java
    String str = new String("Java");
    System.out.println(str); // Java
    System.out.println(str.compareTo("aJav")); // -23
    System.out.println(str.compareTo("Java")); // 0
    System.out.println(str.compareTo("java")); // -32
    System.out.println(str.compareToIgnoreCase("java")); // 0
    ```
    
- `concat()` 메소드: 해당 문자열의 뒤에 인수로 전달된 문자열을 추가한 새로운 문자열을 반환합니다.
    
    ```java
    String str = new String("Hello");
    System.out.println(str); // Hello
    System.out.println(str.concat("Java")); // HelloJava
    ```
    
- `indexOf()` 메소드: 해당 문자열에서 특정 문자나 문자열이 처음으로 등장하는 위치의 인덱스를 반환합니다. 등장하지 않는다면 -1을 반환합니다.
    
    ```java
    String str = new String("Hello");
    System.out.println(str); // Hello
    System.out.println(str.indexOf('o'));      // 4
    System.out.println(str.indexOf('a'));      // -1
    System.out.println(str.indexOf("Hello"));  // 0
    System.out.println(str.indexOf("llo"));    // 2
    ```
    
- `trim()` 메소드: 해당 문자열의 맨 앞과 맨 뒤에 포함된 공백 문자(” “)를 제거합니다.
    
    ```java
    String str = new String("   Hello ");
    System.out.println(str);                // "   Hello   "
    System.out.println(str.trim());         // "Hello"
    ```
    
- toLowerCase(), toUpperCase() 메소드: 해당 문자열을 각각 모두 소문자, 대문자로 변환합니다.
    
    ```java
    String str = new String("HeLlO");
    System.out.println(str);               // HeLlO
    System.out.println(str.toLowerCase()); // hello
    System.out.println(str.toUpperCase()); // HELLO
    ```
    
---
코드 출처: [IT is True - tistory](https://ittrue.tistory.com/104)