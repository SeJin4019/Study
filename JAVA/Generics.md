# Generics
- 제네릭은 클래스 내부에서 사용할 데이터 타입을 외부에서 지정하는 기법
- 객체별로 다른 타입의 자료가 저장될 수 있다
```Java
ArrayList<String> list = new ArrayList<>();
// String타입으로 지정되어 문자열 데이터만 리스트에 적재
```
- <> 꺾쇠 괄호가 제네릭 안에 타입명 기재
- 제네릭은 객체(Object)에 타입을 지정해주는 것이라고 보면 된다.
- <> 다이아몬드 연산자, 꺾쇠 괄호 안에 식별자 기호 지정함으로 파라미터화 할 수 있음
- 타입 매개변수 / 타입 변수라고 부른다
```Java
List<T> // 타입 매개 변수
List<String> stringList = new ArrayList<String>(); // 매개변수화된 타입
```


### 타입 파라미터 정의 

```Java
class FruitBox<T> {
    List<T> fruits = new ArrayList<>();

    public void add(T fruit) {
        fruits.add(fruit);
    }
}
```

```Java
// 제네릭 타입 매개변수에 정수 타입을 할당
FruitBox<Integer> intBox = new FruitBox<>(); 

// 제네릭 타입 매개변수에 실수 타입을 할당
FruitBox<Double> intBox = new FruitBox<>(); 

// 제네릭 타입 매개변수에 문자열 타입을 할당
FruitBox<String> intBox = new FruitBox<>(); 

// 클래스도 넣어줄 수 있다. (Apple 클래스가 있다고 가정)
FruitBox<Apple> intBox = new FruitBox<Apple>();
```
-  인스턴스 생성할 떄 타입명 할다해주면, 클래스 선언 부분으로 가서 T가 지정된 타입으로<br>
  모두 변환되어 클래스의 타입이 지정되게 됨 제네릭 타입 전파(구체화)


### 타입 파라미터 생략 
-  jdk 1.7 버전 이후부터,  new 생성자 부분의 제네릭 타입을 생략할 수 있게 되었다.<br>
  맨 앞에서 클래스명과 함께 타입을 지정해 주었는데 굳이 생성자까지 제네릭을 지정해 줄 필요가 없다<br>
   제네릭 나름대로 타입 추론을 해서 생략 된 곳을 넣어주기 때문에 문제가 없는 것
```Java
FruitBox<Apple> intBox = new FruitBox<Apple>();

// 다음과 같이 new 생성자 부분의 제네릭의 타입 매개변수는 생략할 수 있다.
FruitBox<Apple> intBox = new FruitBox<>();
```

### 타입 파라미터 할당 가능 타입
- 제네릭에서 할당 받을 수 있는 타입은 Reference 타입 뿐, int형이나 double형 같은 자바 원시타입은<br>
제네릭 타입 파라미터로 넘길 수 없음 --> Wrapper 클래스를 사용하는 이유


### 복수 타입 파라미터
- 타입 지정이 여러개 필요할 경우 2개, 3개 얼마든지 가능
- 제네릭 타입의 구분은 꺽쇠 괄호 안에서 쉽표(,)로 하며 <T, U> 와 같은 형식을 통해 복수 타입 파라미터를 지정
- 클래스 초기화할대 제네릭 타입을 두개 넘겨줘야함
```Java
import java.util.ArrayList;
import java.util.List;

class Apple {}
class Banana {}

class FruitBox<T, U> {
    List<T> apples = new ArrayList<>();
    List<U> bananas = new ArrayList<>();

    public void add(T apple, U banana) {
        apples.add(apple);
        bananas.add(banana);
    }
}

public class Main {
    public static void main(String[] args) {
    	// 복수 제네릭 타입
        FruitBox<Apple, Banana> box = new FruitBox<>();
        box.add(new Apple(), new Banana());
        box.add(new Apple(), new Banana());
    }
}
```

### 중첩 타입 파라미터
```Java
public static void main(String[] args) {
    // LinkedList<String>을 원소로서 저장하는 ArrayList
    ArrayList<LinkedList<String>> list = new ArrayList<LinkedList<String>>();

    LinkedList<String> node1 = new LinkedList<>();
    node1.add("aa");
    node1.add("bb");

    LinkedList<String> node2 = new LinkedList<>();
    node2.add("11");
    node2.add("22");

    list.add(node1);
    list.add(node2);
    System.out.println(list);
}
```


- 참고 <br>
  [Inpa Dev 자바 제네릭(Generics) 개념 & 문법 정복하기](https://inpa.tistory.com/entry/JAVA-%E2%98%95-%EC%A0%9C%EB%84%A4%EB%A6%ADGenerics-%EA%B0%9C%EB%85%90-%EB%AC%B8%EB%B2%95-%EC%A0%95%EB%B3%B5%ED%95%98%EA%B8%B0)
