# @SpringBootApplication
```java
@SpringBootApplication
public class SpringBootDeveloperApplication{
public static void main(String[] args){
  SpringApplication.run(SpringBootDeveloperApplication, args);
  }
}
```
- 여기서 스프링 부트가 시작
- 스프링 부트 사용에 필요한 기본 설정을 해줌
- SpringApplication.run() 메서드는 애플리케이션을 실행
- 첫번째 인수는 스프링 부트 3 애플리케이션의 메인 클래스로 사용할 클래스, 두 번째 인수는 커맨드 라인의 인수

### @SpringBootApplication 구성
```java
@SpringBootConfiguation
// 부트관련 설정 @Configuation을 상속

@ComponentScan
// 빈을 읽고 등록하는 애너테이션 @Component 애너테이션을 가진 클래스를 찾아서 빈으로 등록하는 역할
// 모든 빈에 Component만 사용하는게 아님 용도에 따라 Configuartion(설정 파일 등록), Repository(ORM 매핑), @Controller, @RestController(라우터), @Service(비즈니스 로직)

@EnableAutoConfiguration
// 자동구성을 활성화하는 애너테이션 (부트 서버가 실행될 때 부트 메타 파일을 읽고 정의도니 설정들을 자동으로 구성하는 역할
// spring.facctories 파일 클래스 모두 사용될 때 자동사용됨 
```

# @RestController
- 라우터 역할 -> HTTP 요청과 메서드를 연결, 클라이언트 요청에 맞는 메서드 실행

### @RestController 구성
```java
@RestController -> @Controller, @ResponseBody가 합쳐진
@Controller -> @Component // Controller가 스프링빈으로 등록되는 이유

@Configuration, @Repository, @Service -> 모두 @Component 애노테이션을 가지고 있다!
```


  
