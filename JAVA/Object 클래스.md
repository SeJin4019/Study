# Object 클래스
## Java.lang 패키지
- 가장 기본적인 동작을 수행하는 클래스들의 집합 java.lang 패키지의 클래스들은 import 문을 사용안해도 클래스 이름으로만 사용할 수 있음

## Java.lang.Object 클래스
- 가장 많이 사용되는 클래스 Object 클래스
- Object 클래스는 모든 자바 클래스의 최고 조상 클래스
- 자바의 모든 클래스는 Object 클래스의 모든 메소드를 바로 사용할 수 있음
- 필드를 가지지 않으며, 총 11개의 메서드만으로 구성

### toString() 메서드
- 해당 인스턴스에 대한 정보를 문자열로 반환
- 반환되는 문자열은 클래스 이름과 함께 구분자로 '@'가 사용, 뒤로 16진수 해시 코드 추가
- 16진수 해시 코드 값은 인스턴스의 주소를 가리키는 값, 인스턴스마다 모두 다르게 반환

``` java
Car car01 = new Car();

Car car02 = new Car();

 

System.out.println(car01.toString());

System.out.println(car02.toString());

Car@15db9742
Car@6d06d69c
```

### equals()
해당 인스턴스를 매개변수로 전달받는 참조 변수와 비교하여, 결과를 반환 
참조 변수가 가리키는 값을 비교, 서로 다른 두 객체는 언제나 false를 반환
``` java
Car car01 = new Car();

Car car02 = new Car();

 

System.out.println(car01.equals(car02));

car01 = car02; // 두 참조 변수가 같은 주소를 가리킴.

System.out.println(car01.equals(car02));

//
false
true
```
