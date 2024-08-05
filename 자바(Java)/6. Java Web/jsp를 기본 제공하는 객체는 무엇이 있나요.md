## jsp를 기본 제공하는 객체는 무엇이 있나요?

9개 기본 객체가 있음.

- 기본 객체 : jsp 내에서 선언하지 않고 사용할 수 있는 객체.

| 기본 객체   | 실제 타입                              | 설명                                                                                              |
| ----------- | -------------------------------------- | ------------------------------------------------------------------------------------------------- |
| request     | javax.servlet.http.HttpServletRequest  | 클라이언트의 요청 정보를 담고 있고 요청 파라미터, 헤더 등을 얻을 수 있음.                         |
| response    | javax.servlet.http.HttpServletResponse | 서버에서 클라이언트로 전송할 응답을 생성하는 데 사용됨. 응답 헤더와 상태 코드를 설정할 수 있음.   |
| session     | javax.servlet.http.HttpSession         | 사용자 세션 정보를 저장하고 관리함. 세션은 사용자가 웹 애플리케이션에 머무르는 동안 상태를 유지.  |
| application | javax.servlet.ServletContext           | 웹 애플리케이션 전체에서 공유할 수 있는 정보를 저장하고 관리함. 애플리케이션 스코프에 해당.       |
| out         | javax.servlet.jsp.JspWriter            | 클라이언트로 데이터를 출력하는 데 사용됨. JSP 페이지의 출력 버퍼를 제어할 수 있음.                |
| config      | javax.servlet.ServletConfig            | JSP 페이지에 대한 초기화 매개변수를 제공하는 객체. JSP 초기화 파라미터를 설정하고 접근할 수 있음. |
| pageContext | javax.servlet.jsp.PageContext          | JSP 페이지에 대한 정보를 제공하며, 페이지 범위 내에서 속성을 설정하고 얻는 데 사용됨.             |
| page        | java.lang.Object                       | 현재 JSP 페이지 자체를 나타냄. 일반적으로 잘 사용되지 않음.                                       |
| exception   | java.lang.Throwable                    | 오류 페이지에서 예외 정보를 제공하는 데 사용됨. JSP 페이지에서 발생한 예외를 처리함.              |
