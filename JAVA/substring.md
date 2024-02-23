# substring()
메서드 String 문자열을 잘라낼 수 있는 기능
0부터 시작 Start Index와 End Index를 지정해주면 사용자가 지정한 부분의 문자열을 잘라서 가져올 수 있다   
```java
public class TestGo {
 
    public static void main(String[] args) {
        
        String subStr = "안녕하세요.";
        
        String chStr = subStr.substring(0, 3);
        
        System.out.println("substring 값 :: " + chStr);
            
    }
    
}
// 결과 값 안녕하 0 ~ 2번 인덱스까지 짤린거임
// 0, 3 0~2라는 뜻 
```
