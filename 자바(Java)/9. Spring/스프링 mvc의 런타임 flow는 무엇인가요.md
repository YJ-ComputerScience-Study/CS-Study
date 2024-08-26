# 스프링 mvc의 런타임 flow는 무엇인가요?

스프링 MVC의 런타임 flow는 다음과 같이 진행됩니다.

1. **클라이언트 요청(Request)**: 클라이언트가 URL을 통해 HTTP 요청을 보냅니다.
2. **DispatcherServlet**: 클라이언트의 요청은 스프링의 `DispatcherServlet`에게 전달됩니다.
3. **HandlerMapping**: `DispatcherServlet`은 요청 URL에 적절한 컨트롤러를 검색하기 위해 `HandlerMapping`을 사용합니다.
4. **Controller**: `HandlerMapping`에서 찾은 컨트롤러에게 요청을 전달해 이를 처리하고, 비즈니스 로직을 수행한 후 `ModelAndView` 객체를 반환합니다.
5. **ViewResolver**: `DispatcherServlet`은 `ViewResolver`를 사용해 실행 결과를 실제 뷰로 변환합니다.
6. **뷰 렌더링**: 최종적으로 뷰가 렌더링되고 클라이언트에게 응답이 전송됩니다.

![](https://user-images.githubusercontent.com/79154652/138597373-ca8967ce-fee1-4f27-8c8e-06ce6510727c.png)

![](https://velog.velcdn.com/images/ryuneng2/post/be77df6e-eeff-45fb-8c89-a06a87adc435/image.png)

---

### 참고

[[Java]Spring MVC 이해하기(Spring MVC Flow)](https://russell-seo.tistory.com/23)

[Spring MVC의 주요 컴포넌트](https://velog.io/@ryuneng2/Spring-MVC%EC%9D%98-%EC%A3%BC%EC%9A%94-%EC%BB%B4%ED%8F%AC%EB%84%8C%ED%8A%B8)