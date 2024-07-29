## 4개의 jsp scope에는 무엇이 있나요?

jsp scope는 **객체의 유효 범위**를 결정하며, 이는 **객체의 생명 주기**를 정의함.

1. **Page Scope**

   - 객체는 해당 JSP 페이지 내에서만 유효함. 다른 페이지로 전달되지 않음.

   - 생명 주기 : JSP 페이지가 처리될 때만 존재
   - 예) `<jsp:useBean id="myBean" scope="page" class="com.example.MyBean"/>`

2. **Request Scope**

   - 객체는 하나의 HTTP 요청 동안 유효함. 요청이 포워드되거나 인클루드될 때도 유지됨.

   - 생명 주기 : 클라이언트의 요청이 완료될 때까지 존재
   - 예) `<jsp:useBean id="myBean" scope="request" class="com.example.MyBean"/>`

3. **Session Scope**

   - 객체는 사용자의 세션 동안 유효함. 사용자가 웹 애플리케이션을 탐색하는 동안 지속됨.

   - 생명 주기 : 세션이 종료될 때까지 또는 명시적으로 무효화될 때까지 존재
   - 예) `<jsp:useBean id="myBean" scope="session" class="com.example.MyBean"/>`

4. **Application Scope**

   - 객체는 애플리케이션의 모든 세션 및 요청에서 유효함. 모든 사용자에게 공유됨.

   - 생명 주기 : 서버가 시작되어 애플리케이션이 종료될 때까지 존재
   - 예) `<jsp:useBean id="myBean" scope="application" class="com.example.MyBean"/>`
