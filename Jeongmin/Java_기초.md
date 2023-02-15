# Java Study

---

## 숫자와 문자

### 숫자

```java
System.out.println(1+2);        // 3
System.out.println(1.2+1.3);    // 2.5
System.out.println(2*5);        // 10
System.out.println(6/2);        // 6
```

### 문자와 문자열

- 자바는 문자(Character)와 문자열(String)을 구분함
    - 문자는 한 글자, 문자열은 여러 개의 문자가 결합한 것

```java
System.out.println('생');
System.out.println("생활코딩");
System.out.println("egoing said \"Welcome programming world\"");
```

- 문자는 ' ', 문자열은 " "로 감싸야 함
    - 문자열을 ' '로 감싸면 에러 발생 O
    - 문자를 " "로 감싸면 에러 발생 X - 문자열 안에 포함되기 때문
- 문자열 안에 큰 따옴표를 넣고 싶다면?
    - \ 역슬래시를 “ 앞에 위치 시키면 문자를 해석하도록 할 수 있음
- 여러 줄을 표시하고 싶을 때는?  \n
- 문자와 문자를 더할 때는?  +

---

## 변수

### 정수

```java
int a;
a = 1;
System.out.println(a+1);    //2 

a = 2;
System.out.println(a+1);    //3
```

- 변수 a 를 선언, int 는 ‘정수’라는 의미
- 변수 a 에 숫자 1을 대입한 것임 → a에 숫자 1을 할당 했다고 함

### 실수

```java
double a = 1.1; 
System.out.println(a+1.1);    // 2.2
 
int a = 1.1; 
System.out.println(a+1.1);    // error
```

- double은 ‘실수’라는 의미
- int a에 정수인 1.1을 대입하려고 하면 에러가 발생함
    - 데이터 형식에 맞는 데이터를 입력해야 함

### 문자열

```java
String first = "coding"; 
System.out.println(first+" "+"everybody");

String a, b;
a = "coding";
b = " everybody";
System.out.println(a+b);
```

- String은 ‘문자열’이라는 의미

---

## 주석과 세미콜론

- // 을 통해 **한 줄** 주석 가능
- /* 와 */ 사이에 **여러 줄** 주석 가능
- /** 로 시작하는 주석은 Java Doc 주석임 → 자바의 문서를 만들 때 사용

- **세미콜론**은 문장의 끝을 의미
    - 문장의 끝에 세미콜론 사용하지 않으면 컴파일 에러 발생

```java
int a = 100; double b = 10.1;
```

- 세미콜론을 통해 여러 개의 문장을 한 줄에 표현할 수 있음

---

## 데이터 타입

## 정수형

- byte: 1byte
- short: 2byte
- int: 4byte
- long: 8byte

---

## 상수의 데이터 타입

### 실수의 표현

```java
float a = 2.2;    // error
double a = 2.2;

float a = 2.2F;
```

- 자바에서 실수형 상수는 double의 데이터 타입임
- float형 변수에 값을 대입하려면?
    - F는 기호 앞의 숫자가 float 데이터 타입이라는 것을 명시적으로 표현하는 방법임

### 정수의 표현

```java
int a = 2147483648;    // error
long a = 2147483648;    // error

long a = 2147483648L;
```

- 변수 a에 대입되는 상수가 여전히 int 타입이기 때문에 int로 표현할 수 있는 숫자를 초과함
    - L을 통해 변수가 long 타입이 되었다는 것을 알 수 있음
    - byte와 short 타입에 대해서는 int형을 허용하기에 오류 발생하지 않음

---

## 형 변환

### 자동 형 변환

- byte < short, char < int < long < float < double
- 표현 범위가 좁은 데이터 타입에서 넓은 데이터 타입으로의 변환만 허용됨

### 명시적 형 변환

```java
float a = (float)100.0;
int b = (int)100.0F;
```

- 자동 형 변환이 적용되지 않는 경우 수동으로 형 변환을 해야 함
- 방법: (데이터 타입) 데이터 값

---

## 연산자

- ++ : 증가 연산자, 항의 값을 1씩 증가 시킴
- -- : 감소 연산자

---

## 비교와 Boolean

### Boolean

- 참과 거짓을 의미하는 데이터 타입
- 참을 의미하는 True, 거짓을 의미하는 False

### 비교 연산자

- == : 같다, != : 같지 않다, >, >= : 대소를 구분
- .equals : 문자열을 비교할 때 사용하는 메소드임

```java
package org.opentutorials.javatutorials.compare;
 
public class EqualStringDemo {
 
    public static void main(String[] args) {
        String a = "Hello world";
        String b = new String("Hello world");
        System.out.println(a == b);        // False
        System.out.println(a.equals(b));   // True
    }
 
}
```

- == 은 2개의 데이터 타입이 동일한 객체인지 알아내는 연산자이기 때문에 b에 담긴 객체와 일치하지 않아서 False

---

## 조건문

### if

- if(true) { if절 then절 }

```java
package org.opentutorials.javatutorials.condition;
 
public class Condition1Demo {
 
    public static void main(String[] args) {
        if(true){
            System.out.println("result : true");
        }
    }
 
} 
// result : true
```

```java
if(false){
    System.out.println(1);
    System.out.println(2);
    System.out.println(3);
    System.out.println(4);
}
System.out.println(5);

// 5만 출력 -> 왜? false니까...
```

### else

- if(true) { } else { }

```java
package org.opentutorials.javatutorials.condition;
 
public class Condition3Demo {
 
    public static void main(String[] args) {
        if (true) {
            System.out.println(1);
        } else {
            System.out.println(2);
        }
 
    }
 
}
// 1
```

```java
if(false){
    System.out.println(1);
} else {
    System.out.println(2);
}
// 2
```

### else if

- if ( ) { } else if ( ) { } else { }

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
// 2
```

```java
if(false){
    System.out.println(1);
} else if(false) {
    System.out.println(2);
} else if(true) {
    System.out.println(3);
} else {
    System.out.println(4);
}

// 3
```

### switch문

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

/*
switch(1)
one
switch(2)
two
switch(3)
three
switch(4)
default
/*
```

- 가장 마지막은 default로 끝남
- 주어진 케이스가 없는 경우 default 문이 실행된다는 것을 알 수 있음

---

## 논리 연산자

- && : 모두 참일 때 True → **And**
- || : 좌우항 중에 하나라도 참이면 True → **OR**
- ! : 부정의 의미로 **not**, Boolean의 값을 역전시키는 역할을 함

---

## 반복문

### while

- while(조건) { 반복 실행 영역 }

### for

- 특정한 횟수만큼 반복 실행을 하는 경우에 자주 사용됨
- for(초기화; 종료조건; 반복실행) { 반복적으로 실행될 구문 }

```java
package org.opentutorials.javatutorials.loop;
 
public class ForDemo {
 
    public static void main(String[] args) {
        for (int i = 0; i < 10; i++) {
            System.out.println("Coding Everybody " + i);
        }
 
    }
 
}
```

- for문의 괄호 안에는 반복의 종료 조건이 들어옴
    - 초기화: 반복문이 실행될 때 1회 실행됨
    - 종료 조건 : 초기화가 실행된 후에 종료 조건이 실행됨. 종료 조건의 값이 False일때까지 반복문의 중괄호 구간의 코드가 반복 실행됨
    - 중괄호 구간의 실행이 끝나면 반복 실행이 실행됨. 일반적으로 이 곳에 i++ 와 같이 변수를 증가시키는 로직이 위치하고, 실행된 후에 종료 조건이 실행됨 - 종료 조건이 False가 될 때까지 반복됨

### 반복문의 제어

- **break** : 반복문을 즉시 종료시키며, 완전히 종료됨
- **continue** : 실행을 즉시 중단하며 반복은 지속하게 함

---

## 배열

- 배열(Array)은 연관된 정보를 그룹핑 하는데 사용함
- 변수가 하나의 데이터를 저장하기 위한 것이라면 배열은 여러 개의 데이터를 저장하기 위한 것임

### 생성

```java
package org.opentutorials.javatutorials.array;
 
public class DefineDemo {
 
    public static void main(String[] args) {
 
        String[] classGroup = { "최진혁", "최유빈", "한이람", "이고잉" };
 
    }
 
}
```

- String[] classGroup에서
    - classGroup은 배열이 담길 변수의 이름
    - String[]은 배열에 담길 데이터의 타입이 문자열의 배열이라는 의미
    - 배열을 선언할 때는 데이터 타입 뒤에 []를 붙여야 함
    - 배열에 소속될 데이터들은 중괄호 안에 위치함, 데이터들은 쉼표로 구분됨
    

### 제어

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
/*
최진혁
최유빈
한이람
이고잉
*/
```

- .length는 배열을 처음 생성할 때 지정한 배열의 크기를 의미함

### 사용

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

/*
최진혁이 상담을 받았습니다
최유빈이 상담을 받았습니다
한이람이 상담을 받았습니다
*/
```

- 반복문을 돌면서 i를 1씩 증가시킨 후, 학생의 수가 작다면 반복하고 같아지면 종료

### for-each

```java
package org.opentutorials.javatutorials.array;
 
public class ForeachDemo {
 
    public static void main(String[] args) {
        String[] members = { "최진혁", "최유빈", "한이람" };
        for (String e : members) {
            System.out.println(e + "이 상담을 받았습니다");
        }
    }
 
}
```

- 위와 동일하게 동작함
- for(String e : members)
- members의 값을 변수 e에 담아서 중괄호 구간 안으로 전달해 줌
- 반복문의 종료 조건이나 종료 조건을 위해서 기준값을 증가시키는 등의 반복적인 작업을 내부적으로 감춘 것임

### 오류와 한계

- 오류
    - 존재하지 않는 인덱스를 사용하려고 했을 때
    - 배열의 크기를 지정 했으나 그것보다 더 많은 데이터를 추가하려고 할 때
- 한계
    - 배열은 초기화 할 때 크기가 정해짐 - 정해진 크기 이상의 값을 넣을 수 없음