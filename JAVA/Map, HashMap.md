# Map, HashMap
Map 인터페이스 (key : value)
key의 경우 값을 저장하고 가져오기 위한 열쇠 Value의 경우 키(key)에 종속된 데이터    
key는 중복을 허용 x, value의 경우는 중복을 허용합니다.

Map 인터페이스의 경우 HashMap<K,V>를 제일 많이 사용함   
HashMap의 경우 key:value를 묶어 하나의 Entry형식으로 저장

put(k,v), get(k)
```java
public class TestGo {
 
    public static void main(String[] args) {
        
        // map<key : value> value의 자료형이 Object라 모든 Object는 다 들어갈수 있다. (어떠한 자료형이든 노상관) key : String, value : Object
        Map<String, Object> map = new HashMap<String, Object>();
        
        // Map에 문자열 데이터를 넣는다.
        map.put("testStr", "테스트 데이터 입니다."); // (key : String, value : String);
        
        // Map에 정수 데이터를 넣는다.
        map.put("testInt", 1234567890);(key : String, value : integer);
        
        System.out.println("문자열 데이터 표출 : " + map.get("testStr")); // 데이터 가져오기 get()
        System.out.println("정수 데이터 표출 : " + map.get("testInt")); 
        
        System.out.println("자료형 :: " + map.get("testStr").getClass().getName());
        System.out.println("자료형 :: " + map.get("testInt").getClass().getName());
        
        // map 데이터를 문자열에 셋팅
        String setStr = map.get("testStr").toString(); // 리턴값이 String인 "테스트 데이터 입니다."
        
        // map 데이터를 int에 셋팅
        int setInt = (int)map.get("testInt"); // 리턴값이 integer
        
    }
    
}
```
