# 조건문 
- 조건문에는 if문, switch문이 있다.

## if문
- 특정 조건이 참인지 확인하고, 그 조건이 참일 경우 특정 코드 블록을 실행
``` java
if(condition){
  // 조건이 참일 때 실행되는 코드 
}
// 코드블록 {} 사이에 있는 코드 
```
- 헷갈렸던 부분 if문 다음 if문 있을 때 다른거임 각자임 

## else문
- if문에서 만족하는 조건이 없을 때 실행하는 코드를 제공

``` java
if (condition) {
// 조건이 참일 때 실행되는 코드
} else {
// 만족하는 조건이 없을 때 실행되는 코드
}
```
예) 18세 이하면 다 미성년자가 되는 코드가 됨 

- if문으로 계속 코드를 작성하며게 되면 불필요한 조건 검사를 하게 됨
- 코드의 효율성이 떨어지게됨
- 그래서 else if문을 사용
- else if문은 if 문의 조건이 것일 때 다음 조건을 검사 if문이 참이라면 else if를 실행하지 않음
``` java
if (condition1) {
// 조건1이 참일 때 실행되는 코드
} else if (condition2) {
// 조건1이 거짓이고, 조건2가 참일 때 실행되는 코드
} else if (condition3) {
// 조건2이 거짓이고, 조건3이 참일 때 실행되는 코드
} else {
// 모든 조건이 거짓일 때 실행되는 코드
}
```
- else문 생략 가능

if문에 else if를 함께 사용하는 것은 서로 연관된 조건일 때 사용
서로 관련이 없는 독립 조건이면 else if를 사용하지 않고 if문을 각각 따로 사용
``` java
// 예시1. if-else 사용: 서로 연관된 조건이어서, 하나로 묶을 때
if (condition1) {
// 작업1 수행
} else if (condition2) {
// 작업2 수행 }
// 예시2. if 각각 사용: 독립 조건일 때 if (condition1) {
// 작업1 수행 }
if (condition2) { // 작업2 수행
}
```
- 예시 1은 작업1, 작업2 둘 중 하나만 수행된다. 그런데 예시 2는 조건만 맞다면 둘다 수행될 수 있다.

``` java
 package cond;
 public class If5 {
     public static void main(String[] args) {
        int price = 10000;// 아이템 가격
        int age = 10;//나이
        int discount = 0;
        if (price >= 10000) {
          discount = discount + 1000;
          System.out.println("10000원 이상 구매, 1000원 할인");
        }
        if (age <= 10) {
          discount = discount + 1000; System.out.println("어린이 1000원 할인");
        }
          System.out.println("총 할인 금액: " + discount + "원"); }
        }
```
만약 `else if` 를 쓰면, 첫 번째로 충족하는 조건만 할인이 적용되고 나머지는 무시된다. 따라서 사용자는 나머 지 할인을 놓칠 수 있다.
true가 되면 코드블록 사이 {} 코드를 실행하고 빠져나오기 때문에 

### 참고 - if문 {} 중괄호 생략
```java
  if (true)
    System.out.println("if문에서 실행됨");
```
``` java
  if (true)
    System.out.println("if문에서 실행됨");
    System.out.println("if문에서 실행 안됨"); // 이 if문은 해당이 안됨 둘 다 포함하려면 중괄호 포함해야함
```
