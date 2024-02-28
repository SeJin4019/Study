# switch문
- switch문은 단순히 값이 같은지만 비교할 수 있다.
``` java

switch (조건식) {
  case value1:
    // 조건식의 결과 값이 value1일 때 실행되는 코드
     break;
 case value2:
    // 조건식의 결과 값이 value2일 때 실행되는 코드
     break;
 default:
    // 조건식의 결과 값이 위의 어떤 값에도 해당하지 않을 때 실행되는 코드 }
```
- 조건식의 결과 값이 어떤 case의 값과 일치하면 해당 case의 코드 실행
- break문은 현재 실행 중인 코드를 끝내고 switch문을 빠져나가게 하는 역할
- break가 없다면 일치하는 case 이후 모든 case 코드가 순서대로 실행
- default는 조건식의 결과값이 모든 case의 값과 일치하지 않을 때 실행

``` java
package cond;
public class Switch2 {
    public static void main(String[] args) {
        //grade 1:1000, 2:2000, 3:3000, 나머지: 500
        int grade = 2;
        int coupon;
         switch (grade) {
             case 1:
                 coupon = 1000;
                 break;
             case 2:
                 coupon = 2000;
                 break;
             case 3:
                 coupon = 3000;
                 break;
              default:
                 coupon = 500

            }
            System.out.println("발급받은 쿠폰 " + coupon); }
// 결과는 2000
```

```java
package cond;
 public class Switch3 {
public static void main(String[] args) {
//grade 1:1000, 2:3000(변경), 3:3000, 나머지: 500 int grade = 2;
         int coupon;
         switch (grade) {
             case 1:
                 coupon = 1000;
                 break;
             case 2:
             case 3:
                 coupon = 3000;
                 break;
             default:
                coupon = 500;
                break;
            }
          System.out.println("발급받은 쿠폰 " + coupon); }
        }
```
case 2` 에는 `break` 문이 없다. 그러면 중단하지 않고 바로 다음에 있는 `case 3` 의 코드를 실행한다.        
여기서 coupon = 3000; 을 수행하고 `break` 문을 만나서 `switch` 문 밖으로 빠져나간다. `발급받은 쿠폰 3000` 이 출력된다.

## if문 vs switch문
- switch문의 조건식을 넣는 부분은 참 거짓을 결과가 나오는게 아니라, 단순히 값만 넣을 수 있음
- case와 같은지만 체크할 수 있다. 값이 같은지 확인하는 연산만 가능(문자도 가능)
- if문은 참 거짓의 결과가 나오는 조건식을 자유롭게 적을 수 있다.

## 새로운 switch문
java14부터 도입
``` java
package cond;
 public class Switch3 {
public static void main(String[] args) { //grade 1:1000, 2:2000, 3:3000, 나머지: 500 int grade = 2;
         int coupon = switch (grade) {
             case 1 -> 1000;
             case 2 -> 2000;
             case 3 -> 3000;
             default -> 500;
};
System.out.println("발급받은 쿠폰 " + coupon); }
}
```
`->` 를 사용한다.
선택된 데이터를 반환할 수 있다.

## 삼항연산자
- (조건) ? 참_표현식 : 거짓_표현식
