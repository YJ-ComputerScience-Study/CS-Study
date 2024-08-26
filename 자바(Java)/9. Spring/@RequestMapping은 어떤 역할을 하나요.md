# @RequestMapping은 어떤 역할을 하나요?

`@RequestMapping`은 **특정 URL로 요청(Request)**이 들어왔을 때 이를 **특정 메서드와 매핑**하기 위해 사용하는 어노테이션입니다. 이는 **Controller**에서 사용되며, DispatcherServlet이 Controller 파일을 찾고 논리적 주소가 매핑된 메서드를 찾기 위해서는 `@Controller` 와 `@RequestMapping` 이 작성되어야 합니다.

`@RequestMapping` 에서 주로 사용하는 속성은 **value와 method**입니다.

- value: 요청받을 **URL 패턴** 지정
- method: **어떤 요청**으로 받을지 정의(HTTP 메서드 - GET, POST, PUT, DELETE 등)

```java
@RestController
public class MainController {    
 
	@RequestMapping(value = "/main", method = RequestMethod.GET)    
	public String mainGet(...) {
        ...    
  }
}
```

위의 예시에서 `@RequestMapping` 은 `*“/main”*` 경로로 들어오는 모든 요청을 해당 메서드나 컨트롤러에서 처리하게 하는 역할을 수행합니다. 이외에도 추가 속성을 통해 더 구체적인 매핑 설정이 가능합니다.

---

#### 참고

[RequestMapping 옵션](https://backendcode.tistory.com/228)

[[Spring] @RequestMapping이란 그리고 동작 방식](https://backendcode.tistory.com/227)