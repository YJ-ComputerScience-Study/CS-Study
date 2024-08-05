# catch가 반환되면 finally가 실행되나요?

그렇습니다. catch 절에서 return이 실행되더라도, **finally 절은 항상 실행**됩니다. finally 절은 try 블록에서 일어난 일과 관계없이 **무조건 실행**되는 부분입니다.

### 참고

try 절이 일부라도 실행되면 finally 절은 실행이 보장된다.
- try 블록이 **종료**되는 상황
    - 정상적으로 try 블록의 끝에 도달했을 때
    - break, continue 또는 return 문에 의해 종료
    - 예외 발생하였지만 catch 절에서 처리했을 때
    - 예외 발생하고 catch되지 않은 채 전파될 때