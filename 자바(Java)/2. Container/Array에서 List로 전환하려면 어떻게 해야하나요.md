# Array���� List�� ��ȯ�Ϸ��� ��� �ؾ��ϳ���?

1. **�ݺ���**�� ����Ͽ� ���� �ϳ��� ���Ҹ� �߰��ϴ� ���
    
    �� List ��ü�� ���� �����ϰ�, �迭�� ó������ ������ ���ʷ� �����ϸ� �迭�� ��Ҹ� �ϳ��� List ��ü�� �߰��մϴ�.
    
    ```java
    Integer[] intArray = {1, 3, 5, 7, 9};
    List<Integer> intList = new ArrayList<>();
    
    for (Integer num : intArray) {
    	intList.add(num);
    }
    
    ```
    
2. **`Arrays.asList()`** ����ϴ� ���
    
    java.util.Arrays Ŭ������ `asList()` �޼��带 ����մϴ�.
    
    Arrays.asList() �޼ҵ�� **��������**�� ���迭�� list view�� �����մϴ�. ���� ���� �迭�� ���� �����ϸ� List ���� ���� ����Ǹ�, List�� ���Ҹ� �߰��� �� Exception�� �߻��մϴ�.
    
    ```java
    String[] arr = { "A", "B", "C" };
    List<String> list = Arrays.asList(arr);
    ```
    
3. **`new ArrayList<>(Arrays.asList())`** ����ϴ� ���
    
    ���� �迭�� ���� List�� �� ����ȭ�� ���� ����, ���ο� ArrayList ��ü�� �����Ͽ� `asList()` �޼��带 ����� List�� �����մϴ�.
    
    ```java
    String[] arr = { "A", "B", "C" };
    List<String> list = new ArrayList<>(Arrays.asList(arr));
    ```
    
4. **`Collectors.toList()`** ����ϴ� ���
    
    Java 8 ���� ���ĺ��ʹ� **Stream**�� �̿��� ��ȯ�� �����մϴ�.
    
    Stream�� `collect()`�� ���ϴ� Ÿ������ �����͸� ������ �ݴϴ�.
    
    ```java
    String[] arr = { "A", "B", "C" };
    // collect() �޼��忡 Collectors.toList() �����Ͽ� List�� ��ȯ
    List<String> list = Stream.of(arr).collect(Collectors.toList());
    ```
    

---

#### �ڵ� ��ó

- [DevStory:Ƽ���丮](https://developer-talk.tistory.com/664)
- [���� ���� ����:Ƽ���丮](https://hianna.tistory.com/551)