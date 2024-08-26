# @Autowired의 기능은 무엇인가요?

`@Autowired` 는 스프링 컨테이너에 등록한 빈에 의존관계 주입이 필요할 때, **의존성 주입을 도와주는 어노테이션**입니다. 스프링 컨테이너에 **빈들을 모두 등록한 후** 의존성 주입 단계가 이루어지며, 이때 `@Autowired` 어노테이션이 부여된 메서드가 실행되면서 **필요한 인스턴스를 주입**합니다.

이 @Autowired는 총 **3가지**의 경우로 사용 가능한데, 각각 **생성자, setter, 필드**입니다. 스프링 컨테이너는 이 어노테이션이 붙은 생성자, setter, 필드를 발견하면 **해당 타입에 맞는 빈**을 자동으로 주입해 줍니다. 만약 주입 가능한 빈이 여러 개 있거나 없을 경우, 추가적으로 `@Qualifier` 나 `@Primary` 를 활용해 어떤 빈을 주입할지 명시할 수 있습니다.

@Autowired 어노테이션을 사용하면 개발자가 수동으로 **의존성을 관리**할 필요가 없이 스프링이 **자동으로 이를 해결**해 주므로 편리합니다.

---

## Autowired 사용의 3가지 경우

### 생성자 주입

- 객체 생성 시 **딱 한번 호출**되는 것이 보장됨: 필수 의존관계에 사용
- 의존 관계에 있는 객체들을 **final**로 선언할 수 있음: 누락이 발생하지 않음
- **생성자 하나**일 시 `@Autowired` **생략 가능**

### 수정자 주입

- 선택적, **변화 가능**한 의존 관계에 사용

### 필드 주입

- 제일 간단함
- 단점이 많아 **테스트 코드에서만** 한정적으로 사용해야 함



## `@Primary` 란?

- 우선적으로 주입하고 싶은 특정 빈에 해당 어노테이션을 붙여 **우선순위를 지정**함
- 실무에서 많이 사용한다고 함

## `@Qualifier` 란?

- 빈에 **구분자를 같이 삽입**하여 사용할 의존 객체를 선택할 수 있도록 함
- 해당 **`@Qualifier` 가 붙은 빈을 조회**하며, 빈을 찾지 못하면 필드 또는 파라미터 이름으로 매칭을 시도함
    
    ```java
    @Qualifier("noticeBoardReposiroty")
    @Component
    public class noticeBoardRepository implements boardRepository {
    	// ...
    }
    ```
    
    ```cpp
    @Qualifier("noticeBoardRepository")
    @Autowired
    BoardRepository boardRepository
    ```
    

## @Primary VS @Qualifier

- **`@Primary`** : **하나의 구현체**만을 사용하게 함
- **`@Qualifier`** : @Primary보다 까다롭지만 그만큼 디테일하게 사용 가능, @Primary보다 **우선순위가 높음**

---

### 참고

[[Spring] @Autowired를 통한 의존 관계 주입](https://m42-orion.tistory.com/100)

[의존성 주입 방법: 스터디 내용 참고](https://github.com/YJ-ComputerScience-Study/CS-Study/blob/main/%EC%9E%90%EB%B0%94(Java)/9.%20Spring/%EA%B0%80%EC%9E%A5%20%EB%A7%8E%EC%9D%B4%20%EC%82%AC%EC%9A%A9%EB%90%98%EB%8A%94%20%EC%9D%98%EC%A1%B4%EC%84%B1%20%EC%A3%BC%EC%9E%85%20%EB%B0%A9%EB%B2%95%EC%9D%80%20%EB%AC%B4%EC%97%87%EC%9D%B8%EA%B0%80%EC%9A%94.md)