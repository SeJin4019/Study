# 스프링 부트 3 둘러보기

### 첫 번째 스프링 부트 3 예제 만들기 
```java
@RestController
public class TestController{
  @GetMapping("/test")
  public String test(){
    return "Hello, world!";
  }
}
```
- 사용자가 /test GET 을 하면 "Hello, world!"문자열 반환
- http://localhost:8080/test localhost는 아이피로는 127.0.0.1
- 컴퓨터 네트워크에서 사용하는 루프백 호스트명 (현재 사용 중인 컴퓨터를 의미) 8080은 스프링 부트의 포트 번호
  ```java
  http://localhost:8080/test
        현재사용중인 컴퓨터 포트번호 / 매핑된 경로
  ```

### 스프링 부트 스타터 살펴보기
- 의존성이 모여 있는 그룹 필요한 기능을 간편하게 설정
- 스타터는 spring-boot-starter-{작업유형}이라는 명명규칙이 있음
- ex) jdbc관련 스타터는 spring-boot-starter-jdbc
```java
// build.gradle
dependencies{
  implementation 'org.springframework.boot:spring-boot-starter-web' 
  testImplementation 'org.springframework.boot:spring-boot-starter-test'
}
```
의존 관계를 보면 Spring MVC를 사용해 RESTful을 포함한 웹 애플리케이션 개발하는 데 사용 Tomcat도 보임 

### 자동 구성
- 스프링 부트의 중요한 개념
- 애플리케이션이 최소한의 설정만으로도 실행되게 여러 부분을 자동으로 구성
- 스프링부트는 서버를 시작할 때 구성 파일을 읽어와서 설정(이를 자동 설정)
- 자동 설정은 META-INF에 있는 spring.factories 파일에 담겨 있음 <br>
  -> 스프링 부트를 시작할 때 이 파일에 설정되어 있는 클래스는 모두 불러오고 이후에는 프로젝트에서 사용할 것들만 자동으로 구성해 등록
- 이렇게 스프링 부트에서는 빈이 자동으로 등록되고 구성

### 스프링 부트 3와 자바 버전 
- 스프링 부트 3은 자바 17버전 이상을 사용
- 자바 17의 주요 변환인 텍스트 블록, 레코드, 패턴 매치등을 공부
- 텍스트 블록
  - 이전에는 여러 줄의 텍스트를 작성하려면 \n을 추가, 이제는 """로 감싼 텍스트를 사용해 여러 줄의 텍스트를 표현할 수 있음
    ```java
    String query17 = """
    """
  
    ```

- formatted() 메서드
  - 또한 값을 파싱하기 위한 formatted() 메서드도 제공
     ```java
    String textBlock17 = """
     {
       "id": %d,
       "name": %s
     }
    """.formatted(2, "juice");
    ```

- 레코드
  - 레코드는 데이터 전달을 목적으로 하는 객체를 더 빠르고 간편하게 만들기 위한 기능 <br>
    상속을 할 수 없고 파라미터에 정의한 필드는 private final로 정의 <br>
    레코드는 게터를 자동으로 만들기 때문에 애너테이션이나 메서드로 게터 정의를 하지 않아도 됨
    ```java
    record Item(String name, int price){
    }
    Item juice = new Item("juice", 3000);
    juice.price(); // 30000
    ```

- 패턴 매칭
  - 타입 확인을 위해 사용하던 instanceof 키워드를 조금 더 쉽게 사용할 수 있게 해줌
    ```java
    // 11버전
    if (o instanceof Integer){
      Integer i = (Integer) i;
    }

    // 17버전
     if (o instanceof Integer){
    }
    ```

- 자료형에 맞는 case 처리
  - switch-case문으로 자료형에 맞게 case 처리를 할 수 있음
    ```java
    static double getIntegervalue(Object o){
      return switch(o){
      case Double d -> d.intValue();
      case Float f -> f.intValue();
      case String s -> s.intValue();
      default -> 0d;
      }
    }

- Servlet, JPA의 네이 스페이스가 Jakarta로 대체
- 패키지 네임스페이스가 javax.*에서 jakarta.*로 변경 


    
  
