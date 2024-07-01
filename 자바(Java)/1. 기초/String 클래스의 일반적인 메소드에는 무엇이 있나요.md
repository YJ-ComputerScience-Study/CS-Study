# String Ŭ������ �Ϲ����� �޼ҵ�� ������ �ֳ���?

String Ŭ�������� ���ڿ� ������ ���� ���� �޼ҵ尡 �����մϴ�.

- `charAt()` �޼ҵ�: �ش� ���ڿ��� Ư�� �ε����� �ش��ϴ� ���ڸ� ��ȯ�մϴ�. ���� ���ڿ��� ���̺��� ū �ε��� ���̳� ������ �����Ѵٸ� ������ �߻��մϴ�.
    
    ```java
    String str = new String("Java");
    System.out.println(str); // Java
    System.out.println(str.charAt(0)); // J
    System.out.println(str.charAt(2)); // v
    ```
    
- `compareTo()` �޼ҵ�: �ش� ���ڿ��� �μ��� ���޵� ���ڿ��� ���������� ���մϴ�. ���� ���� ��ҹ��ڸ� �����մϴ�. �� ���ڿ��� ���ٸ� 0, �ش� ���ڿ��� �μ��� ���޵� ���ڿ����� �۴ٸ� ����, ũ�� ����� ��ȯ�մϴ�.
    - ��ҹ��� ���� ���� ���� ���� `compareToIgnoreCase()` �޼ҵ带 ����մϴ�.
    
    ```java
    String str = new String("Java");
    System.out.println(str); // Java
    System.out.println(str.compareTo("aJav")); // -23
    System.out.println(str.compareTo("Java")); // 0
    System.out.println(str.compareTo("java")); // -32
    System.out.println(str.compareToIgnoreCase("java")); // 0
    ```
    
- `concat()` �޼ҵ�: �ش� ���ڿ��� �ڿ� �μ��� ���޵� ���ڿ��� �߰��� ���ο� ���ڿ��� ��ȯ�մϴ�.
    
    ```java
    String str = new String("Hello");
    System.out.println(str); // Hello
    System.out.println(str.concat("Java")); // HelloJava
    ```
    
- `indexOf()` �޼ҵ�: �ش� ���ڿ����� Ư�� ���ڳ� ���ڿ��� ó������ �����ϴ� ��ġ�� �ε����� ��ȯ�մϴ�. �������� �ʴ´ٸ� -1�� ��ȯ�մϴ�.
    
    ```java
    String str = new String("Hello");
    System.out.println(str); // Hello
    System.out.println(str.indexOf('o'));      // 4
    System.out.println(str.indexOf('a'));      // -1
    System.out.println(str.indexOf("Hello"));  // 0
    System.out.println(str.indexOf("llo"));    // 2
    ```
    
- `trim()` �޼ҵ�: �ش� ���ڿ��� �� �հ� �� �ڿ� ���Ե� ���� ����(�� ��)�� �����մϴ�.
    
    ```java
    String str = new String("   Hello ");
    System.out.println(str);                // "   Hello   "
    System.out.println(str.trim());         // "Hello"
    ```
    
- toLowerCase(), toUpperCase() �޼ҵ�: �ش� ���ڿ��� ���� ��� �ҹ���, �빮�ڷ� ��ȯ�մϴ�.
    
    ```java
    String str = new String("HeLlO");
    System.out.println(str);               // HeLlO
    System.out.println(str.toLowerCase()); // hello
    System.out.println(str.toUpperCase()); // HELLO
    ```
    
---
�ڵ� ��ó: [IT is True - tistory](https://ittrue.tistory.com/104)