# AssertJ
- JUint과 함께 사용해 검증문의 가독성을 높여주는 라이브러리 
```java
// JUnit Assertions 기댓값과 비교값이 잘 구분되지 않는 
Assertions.assertEquals(sum, a+b)

assertThat(a + b).isEqualTo(sum);
// 이 경우 a와 b를 더한 값이 sum과 같아야 한다는 의미로 명확하게 읽힘
```

### 어노테이션 정리
- @SpringBootTest
  - 메인 애플리케이션 클래스에 추가되는 애너테이션인 @SpringBootApplication이 있는<br>
    클래스를 찾고 그 클래스에 포함되어 있는 빈을 찾은 다음 테스트용 애플리케이션 컨텍스트라는 것을 만듭니다.
- @AutoConfigureMockMvc
  - MockMvc를 생성하고 자동으로 구성하는 애너테이션 <br>
    MockMvc는 애플리케이션을 서버에 배포하지 않고도 테스트용 MVC 환경을 만들어 요청 및 전송, 응답 기능을 제공하는<br>
    유틸리티 클래스, 즉 컨트롤러를 테스트할 때 사용되는 클래스
- @BeforeEach
  - 테스트를 실행하기 전에 실행하는 메서드에 적용하는 애너테이션
- @AfterEach
  - 테스트를 실행한 이후에 실행하는 메서드에 적용하는 애너테이션  
    
     
