# 스프링 mvc 컴포넌트는 무엇이 있나요?

1. **DispatcherServlet**
    - 서블릿 클래스
    - 프론트 컨트롤러의 역할 수행: 모든 HTTP 요청을 가장 먼저 전달받으며, 요청 처리의 전 과정을 주도적으로 수행하는 **핵심 컴포넌트**임
2. **HandlerMapping**
    - 인터페이스이며, 다양한 구현 클래스 존재
    - 컨트롤러 클래스의 매핑 정보 분석
    - DispatcherServlet의 지시를 받아 클라이언트의 요청과 **매핑되는 적절한 컨트롤러/요청핸들러 메서드 검색**
    - 컨트롤러/요청핸들러 메서드를 실행하는 HandlerAdapter 제공
3. **HandlerAdapter**
    - 인터페이스이며, 다양한 구현 클래스 존재
    - 요청핸들러 메서드 **실행에 필요한 작업** 수행
        - 적절한 객체 제공
        - 적절한 요청 파라미터 값 바인딩
        - 객체를 생성하여 매개변수로 전달
    - 반환값을 분석해 **ModelAndView 객체** 반환
4. **Controller**
    - 비즈니스 로직을 처리하고, 요청에 따라 응답을 생성
5. **ModelAndView**
    - 뷰 렌더링 시 사용할 **모델 데이터**를 뷰에 전달하고, **뷰 이름**을 지정
6. **ViewResolver**
    - 뷰 이름에 맞는 **실제 뷰 객체**를 반환
    - Controller가 반환한 결과를 어떤 View를 통해 처리하면 좋을지 해석
    - 가장 흔히 사용: `InternalResourceViewResolver`
7. **View**
    - 최종적으로 사용자에게 **응답을 렌더링**하는 역할
    - Model에 저장된 데이터를 **특정 컨텐츠 타입으로 변환**해 제공

---

### 참고

[[Java]Spring MVC 이해하기(Spring MVC Flow)](https://russell-seo.tistory.com/23)

[[Spring] Spring MVC의 주요 컴포넌트(Model, View 전달 과정)](https://velog.io/@ryuneng2/Spring-MVC의-주요-컴포넌트)

[[Spring] Spring MVC 구조와 컴포넌트](https://gangintheremark.tistory.com/238)