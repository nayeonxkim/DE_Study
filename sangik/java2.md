## 조건문

### if

- True

```java
package org.opentutorials.javatutorials.condition;

public class Condition1Demo {

    public static void main(String[] args) {
        if(true){
            System.out.println("result : true");
        }
    }

}
```

- False

```java
if(false){
    System.out.println("result : true");
}
```

```java
package org.opentutorials.javatutorials.condition;

public class Condition2Demo {

    public static void main(String[] args) {
        if (true) {
            System.out.println(1);
            System.out.println(2);
            System.out.println(3);
            System.out.println(4);
        }
        System.out.println(5);
    }     // 12345 출력 

}
```

### else

- if가 false일 때 else절 실행

```java
package org.opentutorials.javatutorials.condition;

public class Condition3Demo {

    public static void main(String[] args) {
        if (false) {
            System.out.println(1);
        } else {
            System.out.println(2);
        }

    }        // 2 출력 

}
```

### else if

-  if false / else if true

```java
package org.opentutorials.javatutorials.condition;

public class ElseDemo {

    public static void main(String[] args) {
        if (false) {
            System.out.println(1);
        } else if (true) {
            System.out.println(2);
        } else if (true) {
            System.out.println(3);
        } else {
            System.out.println(4);
        }

    }

}
```

### 변수와 비교연산자

- 변수, 비교연산자, 조건문

```java
package org.opentutorials.javatutorials.condition;

public class LoginDemo {
    public static void main(String[] args) {
        String id = args[0];
        if(id.equals("egoing")){
            System.out.println("right");
        } else {
            System.out.println("wrong");
        }
    }
}
```

```java
if(id.equals("egoing")){
```

### 조건문의 중첩

```java
package org.opentutorials.javatutorials.condition;

public class LoginDemo2 {
    public static void main(String[] args) {
        String id = args[0];
        String password = args[1];
        if (id.equals("egoing")) {
            if (password.equals("111111")) {
                System.out.println("right");
            } else {
                System.out.println("wrong");
            }

        } else {
            System.out.println("wrong");
        }
    }
}
```

- 입력을 2개 받는다. if 안에 if

### swich문

```java
package org.opentutorials.javatutorials.condition;

public class SwitchDemo {

    public static void main(String[] args) {

        System.out.println("switch(1)");
        switch(1){
        case 1:
            System.out.println("one");
        case 2:
            System.out.println("two");
        case 3:
            System.out.println("three");
        }

        System.out.println("switch(2)");
        switch(2){
        case 1:
            System.out.println("one");
        case 2:
            System.out.println("two");
        case 3:
            System.out.println("three");
        }

        System.out.println("switch(3)");
        switch(3){
        case 1:
            System.out.println("one");
        case 2:
            System.out.println("two");
        case 3:
            System.out.println("three");
        }

    }

}
```

```
switch(1)
one
two
three
switch(2)
two
three
switch(3)
three
```

- switch 뒤의 괄호에 숫자로 1이 주어지면 case 1에 해당하는 로직 이후의 모든 case들이 실행된다.

- break문을 만나면 실행이 즉시 중지

```java
package org.opentutorials.javatutorials.condition;

public class SwitchDemo {

    public static void main(String[] args) {

        System.out.println("switch(1)");
        switch(1){
        case 1:
            System.out.println("one");
            break;
        case 2:
            System.out.println("two");
            break;
        case 3:
            System.out.println("three");
            break;
        }

        System.out.println("switch(2)");
        switch(2){
        case 1:
            System.out.println("one");
            break;
        case 2:
            System.out.println("two");
            break;
        case 3:
            System.out.println("three");
            break;
        }

        System.out.println("switch(3)");
        switch(3){
        case 1:
            System.out.println("one");
            break;
        case 2:
            System.out.println("two");
            break;
        case 3:
            System.out.println("three");
            break;
        }

    }

}
```

```java
package org.opentutorials.javatutorials.condition;

public class SwitchDemo2 {

    public static void main(String[] args) {

        int val = 1;
        if(val == 1){
            System.out.println("one");
        } else if(val == 2){
            System.out.println("two");
        } else if(val == 2){
            System.out.println("three");
        }

    }

}
```

- if문으로 변환

- default : 주어진 케이스가 없는 경우 실행

```java
package org.opentutorials.javatutorials.condition;

public class SwitchDemo {

    public static void main(String[] args) {

        System.out.println("switch(1)");
        switch(1){
        case 1:
            System.out.println("one");
            break;
        case 2:
            System.out.println("two");
            break;
        case 3:
            System.out.println("three");
            break;
        default:
            System.out.println("default");
            break;
        }

        System.out.println("switch(2)");
        switch(2){
        case 1:
            System.out.println("one");
            break;
        case 2:
            System.out.println("two");
            break;
        case 3:
            System.out.println("three");
            break;
        default:
            System.out.println("default");
            break;
        }

        System.out.println("switch(3)");
        switch(3){
        case 1:
            System.out.println("one");
            break;
        case 2:
            System.out.println("two");
            break;
        case 3:
            System.out.println("three");
            break;
        default:
            System.out.println("default");
            break;
        }

        System.out.println("switch(4)");
        switch(4){
        case 1:
            System.out.println("one");
            break;
        case 2:
            System.out.println("two");
            break;
        case 3:
            System.out.println("three");
            break;
        default:
            System.out.println("default");
            break;
        }

    }

}
```

cf) 스위치는 제한된 데이터 타입만을 사용할 수 있다. byte, short, char, int, enum, String, Character, Byte, Short, Integer

    

## 논리연산자

- && : and : 좌항과 우항의 값이 모두 참일 때 true

```java
package org.opentutorials.javatutorials.conditionaloperator;

public class AndDemo {

    public static void main(String[] args) {
        if (true && true) {
            System.out.println(1);
        }

        if (true && false) {
            System.out.println(2);
        }

        if (false && true) {
            System.out.println(3);
        }

        if (false && false) {
            System.out.println(4);
        }

    }

}
```

- 논리연산자를 이용하여 중첩된 if문 줄일 수 있음

```java
package org.opentutorials.javatutorials.conditionaloperator;

public class LoginDemo3 {
    public static void main(String[] args) {
        String id = args[0];
        String password = args[1];
        if (id.equals("egoing") && password.equals("111111")) {
            System.out.println("right");
        } else {
            System.out.println("wrong");
        }
    }
}
```

- || : or : 둘 중 하나라도 참이면 True

```java
package org.opentutorials.javatutorials.conditionaloperator;

public class OrDemo {

    public static void main(String[] args) {
        if (true || true) {
            System.out.println(1);
        }
        if (true || false) {
            System.out.println(2);
        }
        if (false || true) {
            System.out.println(3);
        }
        if (false || false) {
            System.out.println(4);
        }

    }

}
```

- ! : not : boolean의 값을 역전

```java
package org.opentutorials.javatutorials.conditionaloperator;

public class NotDemo {

    public static void main(String[] args) {
        if (!true) {
            System.out.println(1);
        }
        if (!false) {
            System.out.println(2);
        }

    }

}
```

    

## 반복문

#### while

- 반복조건이 참이면 중괄호 구간을 반복적으로 실행

```java
while(조건){
    반복 실행 영역
}
```

```java
package org.opentutorials.javatutorials.loop;

public class WhileDemo {

    public static void main(String[] args) {
        while (true) {
            System.out.println("Coding Everybody");
        }

    }

}
```

- 종료조건 설정

```java
int i = 0;
// i의 값이 10보다 작다면 true, 크다면 false가 된다. 현재 i의 값은 0이기 때문에 이 반복문은 실행된다. 
while(i<10){         
    System.out.println("Coding Everybody"+i);
    // i의 값에 1을 더한다. 반복문의 중괄호의 마지막 라인에 도달하면 반복문은 반복문을 재호출한다. 이때 i<10의 값을 검사하게 된다.
    i++;
}
```

#### for

- 특정한 횟수만큼 반복 실행

```java
for(초기화; 종료조건; 반복실행){
    반복적으로 실행될 구문
}
```

```java
package org.opentutorials.javatutorials.loop;

public class ForDemo {

    public static void main(String[] args) {
        for (int i = 0; i < 10; i++) {
            System.out.println("Coding Everybody " + i);
        }

    }   // 1234

}
```

- 종료조건:
  
  - 초기화 : 반복문이 실행될 때 1회 실행된다.
  
  - 종료조건 : 초기화가 실행된 후에 종료조건이 실행된다. 종료조건의 값이 false일 때까지 반복문의 중괄호 구간의 코드가 반복 실행된다.
  
  - 중괄호 구간의 실행이 끝나면 반복 실행이 실행된다. 일반적으로 이 곳에 i++와 같이 변수를 증가시키는 로직이 위치하고, 이것이 실행된 후에 종료조건이 실행된다. 종료조건이 false가 될 때까지 이 과정이 반복된다.

#### 반복문이 없다면

- 규모가 큰 데이터를 다룰 때 중복 작업 최소화

- 수정 시 하나하나의 코드를 다 바꿔야 함

### 반복문의 제어

- break : 중간에 중단

```java
package org.opentutorials.javatutorials.loop;

public class BreakDemo {

    public static void main(String[] args) {
        for (int i = 0; i < 10; i++) {
            if (i == 5)
                break;
            System.out.println("Coding Everybody " + i);
        }

    }

}
```

- continue : 실행을 즉시 중단하면서 반복은 지속

```java
package org.opentutorials.javatutorials.loop;

public class ContinueDemo {

    public static void main(String[] args) {
        for (int i = 0; i < 10; i++) {
            if (i == 5)
                continue;
            System.out.println("Coding Everybody " + i);
        }

    }   // 12346789

}
```

### 반복문의 중첩

```java
package org.opentutorials.javatutorials.loop;

public class LoopDepthDemo {

    public static void main(String[] args) {
        for (int i = 0; i < 10; i++) {
            for (int j = 0; j < 10; j++) {
                System.out.println(i + "" + j);
            }
        }

    }

}
```

    

## 배열

- 배열 : 연관된 데이터를 모아서 관리

- 배열 생성

```java
package org.opentutorials.javatutorials.array;

public class DefineDemo {

    public static void main(String[] args) {

        String[] classGroup = { "최진혁", "최유빈", "한이람", "이고잉" };

    }

}
```

- 각각의 데이터들은 쉼표로 구분

- 데이터 타입 뒤에 []

#### 데이터 제어

```java
package org.opentutorials.javatutorials.array;

public class GetDemo {

    public static void main(String[] args) {
        String[] classGroup = { "최진혁", "최유빈", "한이람", "이고잉" };
        System.out.println(classGroup[0]);
        System.out.println(classGroup[1]);
        System.out.println(classGroup[2]);
        System.out.println(classGroup[3]);

    }

}
```

- length : 처음생성 시 지정한 배열의 크기

```java
package org.opentutorials.javatutorials.array;

public class LengthDemo {

    public static void main(String[] args) {
        String[] classGroup = new String[4];
        classGroup[0] = "최진혁";
        System.out.println(classGroup.length);
        classGroup[1] = "최유빈";
        System.out.println(classGroup.length);
        classGroup[2] = "한이람";
        System.out.println(classGroup.length);
        classGroup[3] = "이고잉";
        System.out.println(classGroup.length);

    }

}
```

- 원소 : 배열에 담긴 각각의 데이터

- 식별자 : 인덱스 : 원소를 식별

- length : 원소의 개수

    

### 반복문과 배열의 조합

```java
package org.opentutorials.javatutorials.array;

public class ArrayLoopDemo {

    public static void main(String[] args) {

        String[] members = { "최진혁", "최유빈", "한이람" };
        for (int i = 0; i < members.length; i++) {
            String member = members[i];
            System.out.println(member + "이 상담을 받았습니다");
        }

    }

}
```

- 반복문을 통해 배열의 내용을 하나씩 꺼낼 수 있음

### for each

```java
package org.opentutorials.javatutorials.array;

public class ForeachDemo {

    public static void main(String[] args) {
        String[] members = { "최진혁", "최유빈", "한이람" };
        for (String e : members) {  // 배열을 e로 받음  
            System.out.println(e + "이 상담을 받았습니다");
        }
    }

}
```

### 오류

```java
String[] members = { "최진혁", "최유빈", "한이람" };
System.out.println(members[3]);
```

- 인덱스가 0~2까지

```java
String[] members = new String[3];
members[0] = "최진혁";
members[1] = "최유빈";
members[2] = "한이람";
members[3] = "이고잉";
```

- 생성 시 배열 크기가 3인데 4개 원소를 넣으려해서

### 한계

-  초기화할 때 그 크기가 정해진다.

- 
