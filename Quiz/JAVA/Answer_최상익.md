1) 다음 코드 중 각 번호의 실행 결과로 맞는 것을 고르시오 4)

```java
package org.opentutorials.javatutorials.array;

public class LengthDemo {

    public static void main(String[] args) {
        String[] classGroup = new String[4];
        classGroup[0] = "김철수";  
        System.out.println(classGroup.length);  // 1)
        classGroup[1] = "박영희";  
        System.out.println(classGroup.length);  // 2)
        classGroup[2] = "유재석";  
        System.out.println(classGroup.length);  // 3)
        classGroup[3] = "강호동";  
        System.out.println(classGroup.length);  // 4)

    }

}
```

1)    1    # 4

2)    2    # 4

3)    3    # 4

4)    4    # 4 

    ## length는 최초 배열 생성 시 지정한 최대 원소의 개수를 의미한다.

          때문에 현재 원소의 개수와는 별개로 항상 4가 결과

    

2. 다음 수식의 결과의 데이터 타입이 틀린 것들 고르시오 1)

1)    60 + 13.1 : float           int + double = double

2)    16 / 3 : int                     int + int = int

3)    21  ==  50 : boolean    논리연산자로 연산 -> 결과는 false로 boolean

4)    3 + 1.0F : float              int + float = float

      # 표현범위가 더 넓은 데이터 타입으로 자동 형변환

    

3. 파이썬과 자바에 대한 설명으로 틀린 것을 모두 고르시오  2), 4)

1)    자바는 변수를 선언할 때 int a와 같이 데이터 타입을 명시해야 한다.

2)    파이썬과 자바 모두 10/3을 했을 때의 결과는 같다.

3)    파이썬과 달리 자바는 증감연산자를 사용할 수 있다.

4)    파이썬과 달리 자바는 여러줄 주석을 할 수 없다.

    # 2) 파이썬은 3.333333...   / 자바는 3

        4) 자바 또한 /*        */   를 통해서 여러줄 주석을 할 수 있다
