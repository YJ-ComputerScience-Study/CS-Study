# Context switching이란 무엇인가요?


> 프로세스 기준 설명

컨텍스트 스위칭이란, CPU가 어떤 하나의 프로세스를 실행하고 있는 상태에서 다른 프로세스가 실행되어야 할 때 실행 중이던 프로세스의 상태를 저장하고 로드시키는 과정을 말합니다.

프로세스 A를 실행하고 있을 때, 인터럽트 또는 시스템 콜이 발생하면 시스템은 프로세스 A의 상태를 PCB에 저장합니다. 이후 프로세스 B의 PCB를 로드하고, PCB의 정보를 읽어 이전에 중단된 작업부터 다시 프로세스 B를 실행합니다.

컨텍스트 스위칭을 진행하는 동안은 다른 작업을 할 수 없으나, 보통 이 시간보다 I/O 작업이 더 오래 걸리기 때문에 컨텍스트 스위칭을 하는 것이 효율적입니다. 또한 컨텍스트 스위칭이 있기 때문에 여러 프로세스를 처리할 수 있습니다.


![context switching](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FcLs4ee%2Fbtq6zCgeEaS%2FeMkhgp9failtca7VYSgbkk%2Fimg.png)