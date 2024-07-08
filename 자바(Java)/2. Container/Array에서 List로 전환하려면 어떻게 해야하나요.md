# Array에서 List로 전환하려면 어떻게 해야하나요?

1. **반복문**을 사용하여 직접 하나씩 원소를 추가하는 방법
    
    빈 List 객체를 새로 생성하고, 배열을 처음부터 끝까지 차례로 접근하며 배열의 요소를 하나씩 List 객체에 추가합니다.
    
    ```java
    Integer[] intArray = {1, 3, 5, 7, 9};
    List<Integer> intList = new ArrayList<>();
    
    for (Integer num : intArray) {
    	intList.add(num);
    }
    
    ```
    
2. **`Arrays.asList()`** 사용하는 방법
    
    java.util.Arrays 클래스의 `asList()` 메서드를 사용합니다.
    
    Arrays.asList() 메소드는 **고정길이**인 원배열의 list view를 리턴합니다. 따라서 원래 배열의 값을 변경하면 List 값도 같이 변경되며, List에 원소를 추가할 시 Exception이 발생합니다.
    
    ```java
    String[] arr = { "A", "B", "C" };
    List<String> list = Arrays.asList(arr);
    ```
    
3. **`new ArrayList<>(Arrays.asList())`** 사용하는 방법
    
    원본 배열의 값과 List의 값 동기화를 막기 위해, 새로운 ArrayList 객체를 생성하여 `asList()` 메서드를 사용한 List를 저장합니다.
    
    ```java
    String[] arr = { "A", "B", "C" };
    List<String> list = new ArrayList<>(Arrays.asList(arr));
    ```
    
4. **`Collectors.toList()`** 사용하는 방법
    
    Java 8 버전 이후부터는 **Stream**을 이용한 변환이 가능합니다.
    
    Stream의 `collect()`는 원하는 타입으로 데이터를 변경해 줍니다.
    
    ```java
    String[] arr = { "A", "B", "C" };
    // collect() 메서드에 Collectors.toList() 전달하여 List로 변환
    List<String> list = Stream.of(arr).collect(Collectors.toList());
    ```
    

---

#### 코드 출처

- [DevStory:티스토리](https://developer-talk.tistory.com/664)
- [어제 오늘 내일:티스토리](https://hianna.tistory.com/551)