# ArrayList
- List 인터페이스를 상속받은 여러 클래스 중 하나
- 일반 배열과 동일하게 연속된 메모리 공간을 사용, 인덱스는 0부터 시작
- 배열과의 차이점은 배열은 크기가 고정인 반면 ArrayList는 크기가 가변적으로
- 저장 가능한 메모리 용량(Capacity), 현재 사용 중인 크기(Size) -> 가용량(Capacity) 이상을 저장하려고 할때 더 큰 공간의 메모리를 새롭게 할당

```Java
import java.util.ArrayList;

ArrayList<Integer> integers1 = new ArrayList<Integer>(); // 타입 지정
ArrayList<Integer> integers2 = new ArrayList<>(); // 타입 생략 가능 보통 이렇게 생성
ArrayList<Integer> integers3 = new ArrayList<>(10); // 초기 용량(Capacity) 설정
ArrayList<Integer> integers4 = new ArrayList<>(integers1); // 다른 Collection 값으로 초기화
ArrayList<Integer> integers5 = new ArrayList<>(Arrays.asList(1,2,3,4,5)); // Arrays.asList() 일반 배열을 ArrayList로 변환
```

1. ArrayList 엘레멘트 추가/변경
- add(), set()
```Java
import java.util.ArrayList;

public class ArrayListTest {
    public static void main(String[] args) {
        ArrayList<String> colors = new ArrayList<>();
        // add() method
        colors.add("Black");
        colors.add("White");
        colors.add(0, "Green"); // 인덱스 지정
        colors.add("Red");

        // set() method
        colors.set(0, "Blue");

        System.out.println(colors);
    }
}
```
add() 기본적으로 리스트의 가장 끝에 값을 추가
별도 인덱스를 지정하면 해당 인덱스에 값이 추가 값들이 한칸씩 밀림 ->    
set()은 데이터 값이 교체되어버림 

2. ArrayList 엘리먼트 삭제
- remove() 메서드 호출
- 인덱스를 입력하거나 엘레멘트를 직접 입력 할 수 있음
- remove(0), remove("Red"), clear() // 전체 삭제
``` Java
import java.util.ArrayList;
import java.util.Arrays;

public class ArrayListTest {
    public static void main(String[] args) {
        ArrayList<String> colors = new ArrayList<>(Arrays.asList("Black", "White", "Green", "Red"));
        String removedColor = colors.remove(0);
        System.out.println("Removed color is " + removedColor);

        colors.remove("White");
        System.out.println(colors);

        colors.clear();
        System.out.println(colors);
    }
}
```
3. ArrayList 전체 값 확인
ArrayList의 모든 값들을 순회해서 출력하고 싶은 경우 다양한 방법을 사용할 수 있음
```java
import java.util.ArrayList;
import java.util.Arrays;
import java.util.Iterator;
import java.util.ListIterator;

public class ArrayListTest {
    public static void main(String[] args) {
        ArrayList<String> colors = new ArrayList<>(Arrays.asList("Black", "White", "Green", "Red"));
        // for-each loop
        for (String color : colors) {
            System.out.print(color + "  ");
        }
        System.out.println();

        // for loop
        for (int i = 0; i < colors.size(); ++i) {
            System.out.print(colors.get(i) + "  ");
        }
        System.out.println();

        // using iterator
        Iterator<String> iterator = colors.iterator();
        while (iterator.hasNext()) {
            System.out.print(iterator.next() + "  ");
        }
        System.out.println();

        // using listIterator
        ListIterator<String> listIterator = colors.listIterator(colors.size());
        while (listIterator.hasPrevious()) {
            System.out.print(listIterator.previous() + "  ");
        }
        System.out.println();
    }
}
```
4. 값 존재 유무 확인
- ArrayList의 안에 값이 존재하는지 존재한다면 어느 위치에 존재하는지?!
- 값이 존재하는지만 알고 싶은 경우 contains() 사용
- 값이 존재할때 어느 위치에 존재하는지 알고 싶은 경우 indexOf()를 사용
```java
import java.util.ArrayList;
import java.util.Arrays;

public class ArrayListTest {
    public static void main(String[] args) {
        ArrayList<String> colors = new ArrayList<>(Arrays.asList("Black", "White", "Green", "Red"));
        boolean contains = colors.contains("Black");
        System.out.println(contains);

        int index = colors.indexOf("Blue"); // 인덱스를 리턴, 값이 존재하지 않을 때 -1 리턴
        System.out.println(index);

        index = colors.indexOf("Red");
        System.out.println(index); // 있는 경우 true, 없는 경우 false
    }
}
```
