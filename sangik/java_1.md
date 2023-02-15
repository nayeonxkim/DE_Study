## 

## 1. 숫자와 문자

#### # 숫자

- 자바에서는 따옴표가 없는 숫자는 숫자로 인식한다
  
  ```java
  System.out.printin(1 + 2);   # 3
  ```

- 곱하기를 할 때는 *(에스터리스크, Asterisk, 키보드 자판상으로 숫자 8 위)를 사용한다.

```java
System.out.println(2*5);  # 10
```

- 나누기를 할 때는 /(슬래쉬, slash, 키보드 자판상으로 오른쪽 shift 키 왼쪽)를 사용한다

```java
System.out.println(6/2);   # 3
```

#### 문자

- 문자(Character) : 한 글자
  
  ```java
  System.out.println('생');  # 작은 따옴표로 감싼다
  ```

- 문자열(String) : 여러 개의 문자가 결합한 것

```java
System.out.println("생활코딩");  # 큰따옴표로 감싼다
```

- 만약 문자열을 작은 따옴표로 감싸면 에러가 발생한다

```java
System.out.println('생활코딩');   # err
```

- 하나의 문자를 큰따옴표로 감싼다고 에러가 발생하지는 않는다. 한 글자도 문자열이 될 수 있기 때문이다.

```java
System.out.println("생");
```

- 문자열과 문자열을 결합할 때도 + 연산자 사용

- 문자열과 문자열은 서로 붙여준다

```java
System.out.println('1' + '1');   # '11'
```

- 문자열 안에 큰 따옴표를 넣고 싶다면?

- 이스케이프 : \를 앞에 위치시키면 단순한 문자로 해석하도록 강제

- 즉 큰따옴표가 가진 문법적인 역할에서 도망(escape)쳐서 문자로 인식하도록 한다는 의미다.

```java
System.out.println("egoing said \"Welcome programming world\"");
```

- 여러 줄을 표시 ( \n : 줄바꿈)

```java
System.out.println("HTML\nCSS\nJavaScript\n");
```

    

    

# 2. 변수

- 변수 : 숫자나 문자 같은 데이터를 담는 컨테이너, 담겨진 데이터는 다른 데이터로 바꿀 수 있다.

#### 변수의 선언과 할당

정수

- 0을 기준으로 한 양수와 음수, 소수점 X

- int a : 위 구문은 a를 지금부터 사용하겠다고 변수를 선언한 것, int라는 키워드를 통해서 정수를 담는 그릇임을 명시한 것

- a=1 : 변수 a의 데이터가 1이라는 의미, <u>변수 a에 숫자 1을 할당했다</u>

```java
int a;
a = 1;
System.out.println(a+1); //2
a = 2;
System.out.println(a+1); //3
```

cf) // : 주석

    ;    하나의 구문이 끝났음을 명시적으로 나타내는 기호

    

실수

- 소수점이 있는 수

- double a : double로 실수를 담는 그릇임을 명시한 것

```java
double a = 1.1; 
System.out.println(a+1.1); // 2.2

a = 2.1; 
System.out.println(a+1.1); // 3.2
```

- 에러 발생 : 정수 int에 실수를 할당하려고 했기 때문에, 컨테이너를 생성할 때 지정한 데이터 형식에 맞는 데이터만 입력할 수 있다.

```java
int a = 1.1; 
System.out.println(a+1.1);
```

cf)자바와 스크립트

-  자바스크립트는 자바와 다르게 변수의 값으로 어떠한 값도 들어올 수 있다. 까다롭게 정수와 실수를 구분하지 않아도 된다

- 변수 a만 보고는 변수 안에 정수가 들어있는지 숫자가 들어있는지 파악 할 수 있는 방법이 없다

#### 문자열

```java
String first = "coding"; 
System.out.println(first+" "+"everybody");


String a, b;
a = "coding";
b = " everybody";
System.out.println(a+b);
```

    

### 변수의 효용성

- 코드의 재활용성을 높여줌

```java
System.out.println(100 + 10);
System.out.println((100 + 10) / 10);
System.out.println(((100 + 10) / 10) - 10);
System.out.println((((100 + 10) / 10) - 10) * 10);
```

- 100을 1000으로 바꾸려면 모두 하나하나 수정해야 함

```java
int a = 100;
System.out.println(a + 10);
System.out.println((a+ 10) / 10);
System.out.println(((a + 10) / 10) - 10);
System.out.println((((a + 10) / 10) - 10) * 10);
```

- 변수를 사용하면 대입하는 수만 바꾸면 끝

- 유지보수의 용이성, 중복 제거, 가독성

    

# 3. 주석과 세미콜론

### 주석

- 주석(comment)은 로직에 대한 설명이나 코드를 비활성화 할 때 사용한다. 주석은 프로그래밍적으로 해석되지 않는다.

- 한줄 주석

```java
// 두개의 변수가 같은 데이터 타입 일 때 아래와 같이 코드를 작성한다.
```

- 여러 줄 주석

```java
    /*
    a = "coding";
    b = "everybody";
    System.out.println(a+b);
    */
```

- javadoc 주석 : 자바의 문서를 만들 때 사용

```java
/**
 * Prints an integer and then terminate the line.  This method behaves as
 * though it invokes <code>{@link #print(int)}</code> and then
 * <code>{@link #println()}</code>.
 *
 * @param x  The <code>int</code> to be printed.
 */
```

- 세미콜론
  
  - 문장의 끝을 의미
  
  - 문장 끝에 ;을 사용하지 않으면 컴파일 에러 발생
  
  - 세미콜론을 이용하면 여러 개의 문장을 한줄에 표현할 수 있음
  
  ```java
  System.out.println("Hello World!");
  
  int a = 100; double b = 10.1;
  ```

    

## 데이터 타입

- bit : 0과 1

- 8 bit = 1byte

- byte > kb > mb > gb > .... 1024 배씩 늘어남

###### 정수형

| 데이터 타입 | 메모리 크기 | 표현 가능 범위                                               |
| ------ | ------ | ------------------------------------------------------ |
| byte   | 1 byte | -128~127                                               |
| short  | 2 byte | -32,768 ~ 32,767                                       |
| int    | 4 byte | -2,147,483,648~2,147,483,647                           |
| long   | 8 byte | -9,223,372,036,854,775,808 ~ 9,223,372,036,854,775,807 |

- 아래의 변수 a와 변수 b는 둘 다 똑같이 8byte의 메모리를 사용하게 된다. 데이터 타입이 같기 때문이다.

```java
long a = 2147483647;
long b = 1;
```

- 반대로 아래의 변수 a와 변수 b는 똑같은 수를 저장하고 있지만, 변수 b가 2배의 메모리를 사용한다. 데이터 타입이 다르기 때문이다

```java
int a = 2147483647;
long b = 2147483647;
```

- 즉, 어떤 데이터 타입을 사용하느냐에 따라서 메모리의 크기가 달라진다. 변수에 들어올 숫자의 크기를 잘 판단해서 데이터 타입을 지정해야 한다

- 결과적으로 정수를 저장할 때는 int 사용 : 처리속도 빠르고 충분히 큰 수

##### 실수형

| float  | 4byte | ±(1.40129846432481707e-45 ~ 3.40282346638528860e+38)     |
| ------ | ----- | -------------------------------------------------------- |
| double | 8byte | ±(4.94065645841246544e-324d ~ 1.79769313486231570e+308d) |

- 실수에서는 double를 사용

##### 

###### 문자

| char   | 2 byte  | 모든 유니코드 문자 |
| ------ | ------- | ---------- |
| string | 12 byte |            |

    

## 상수의 데이터 타입

- 상수 : 변하지 않는 값

- ```java
  1 = 3;   // 컴파일 불가능, 1은 변할 수 없다
  ```

### 실수의 표현

- 상수도 데이터 타입이 있다.

```java
int a = 2;
float a = 2.2F;
double a = 2.2;
```

### 정수의 표현

```java
int a = 2147483648;  // 오류 발생 > int의 최대범위 넘어섬
long a = 2147483648; //오류 발생 > int 타입의 상수
long a = 2147483648L; // long 타입의 상수와 변수
```

- int 보다 작은 byte나 short의 경우에는 범위 내에서 int형을 허용

```java
byte a = 100;
short b = 200;
```

    

## 형변환

- 형변환 : 데이터 타입을 변경하는 것

```java
00000000 00000000 00000000 11001000  // 정수 타입 200 bit 값
01000011 01001000 00000000 00000000  // float 타입 200 bit
```

- 형식이 다른 데이터들을 더하려면 한쪽의 데이터 타입을 완전히 전환

- 자동형 변환 (암시적) : 변환을 자동으로 처리

- 자동으로 float 타입이 double 타입으로 변환 : double가 더 넓은 범위

- 타입을 변경해도 정보 손실이 일어나지 않는 경우 자동형 변환

```java
double a = 3.0F; 
```

- 표현범위가 좁은 데이터 타입에서 >> 넓은 데이터 타입으로의 변환만 허용

```java
float a = 3.0;  // 오류발
```

- 규칙 : byte > shotr, char > int > long > float > double

```java
int a = 3;
float b = 1.0F;
double c = a + b;
```

-> 두 번의 형변환 : 1) 정수 a 가 float로 변환, 2)float a+b가 double로 변환

    

#### 명시적 형변환

- 수동 형 변환
- 괄호 안에 데이터 타입을 지정하여 값 앞에 위치

```java
float a = 100.0;     // 오류발생
int b = 100.0F;

float a = (float)100.0;  // 명시적 형변환
int b = (int)100.0F;
```

    

## 연산자

- 특정한 작업을 하기 위해 사용하는 기호 : 대입, 산술, 비교, 논리

#### 산술연산자

- 수학적인 계산에 사용되는 연산자

- (+, 더하기), (-, 빼기), (*, 곱하기), (/,나누기), (%, 나머지)

```java
public class ArithmeticDemo  {
    public static void main(String[] args) {
        // result 의 값은 3
        int result = 1 + 2;
        System.out.println(result); // 3

        // result 의 값은 2
        result = result - 1;
        System.out.println(result); // 2

        // result 의 값은 4
        result = result * 2;
        System.out.println(result); // 4

        // result 의 값은 2
        result = result / 2;
        System.out.println(result); // 2

        // result 의 값은 10
        result = result + 8;
        // result 의 값은 3
        result = result % 7;
        System.out.println(result); // 3
    }
}
```

```java
public class RemainerDemo {
    public static void main(String[] args) {
        int a = 3;
        System.out.println(0%a);  // 0
        System.out.println(1%a);  // 1
        System.out.println(2%a);  // 2  
        System.out.println(3%a);  // 0
        System.out.println(4%a);  // 1
        System.out.println(5%a);  // 2
        System.out.println(6%a);  // 0
    }
}
```

- 문자열과 문자열의 결합도 가능

```java
class ConcatDemo {
    public static void main(String[] args){
        String firstString = "This is";
        String secondString = " a concatenated string.";
        String thirdString = firstString+secondString;
        System.out.println(thirdString);
    }     // This is a concatenated string.
}
```

    

### 형변환과 연산

```java
public class DivisionDemo {

    public static void main(String[] args) {
        int a = 10;
        int b = 3;

        float c = 10.0F;
        float d = 3.0F;

        System.out.println(a/b);  // 3
        System.out.println(c/d);  // 3.33333
        System.out.println(a/d);  // 3.33333

    }

}
```

- 정수와 정수를 나눈 경우 몫만 남음

- 실수와 실수를 나눈 경우 몫과 소수점

- 정수에서 실수를 나눈 경우 몫과 소수점 : 암시적 형변환으로 정수->실수

    

### 단항 연산자

- 하나의 항을 대상으로 연산이 이루어지는 연산자

- (+, 양수 표현), (-, 음수 표현), (++, 중가 연산자 : 항의 값을 1씩 더함),(--, 감소 연산자)

```java
package org.opentutorials.javatutorials.operator;

public class PrePostDemo {
    public static void main(String[] args) {
        int i = 3;
        i++;
        System.out.println(i); // 4 출력
        ++i;
        System.out.println(i); // 5 출력
        System.out.println(++i); // 6 출력
        System.out.println(i++); // 6 출력
        System.out.println(i); // 7 출력
    }
}
```

- i++ , ++i   ==  i = i + 1

    

### 연산의 우선순위

        

### 비교와 boolean

#### boolean

- 참과 거짓을 의미하는 데이터 타입, 2개의 값

#### 비교연산자(관계 연산자)

- 비교란 주어진 값들이 같은지, 다른지, 큰지, 작은지를 구분하는 것을 의미

- 결과는 true나 false 중의 하나

- == : 좌항과 우항이 서로 같은 값이면 True

```java
package org.opentutorials.javatutorials.compare;

public class EqualDemo {

    public static void main(String[] args) {
        System.out.println(1==2);           //false
        System.out.println(1==1);           //true
        System.out.println("one"=="two");   //false
        System.out.println("one"=="one");   //true
    }

}
```

- != : 부정, 같지 않다

```java
package org.opentutorials.javatutorials.compare;

public class NotDemo {

    public static void main(String[] args) {
        System.out.println(1!=2);           //true
        System.out.println(1!=1);           //false
        System.out.println("one"!="two");   //true  
        System.out.println("one"!="one");   //false
    }

}
```

- `>`  : 좌항이 우항보다 크다면 참

```java
public class GreaterThanDemo {

    public static void main(String[] args) {
        System.out.println(10>20);       //false
        System.out.println(10>2);            //true
        System.out.println(10>10);           //false

    }

}
```

- `>=` : 좌항이 우항보다 크거나 같다

```java
public class GreaterThanOrEqualDemo {

    public static void main(String[] args) {

        System.out.println(10 >= 20); // false
        System.out.println(10 >= 2); // true
        System.out.println(10 >= 10); // true

    }

}
```

- .equals : 문자열을 비교할 때 사용하는 메소드

```java
package org.opentutorials.javatutorials.compare;

public class EqualStringDemo {

    public static void main(String[] args) {
        String a = "Hello world";
        String b = new String("Hello world");
        System.out.println(a == b);
        System.out.println(a.equals(b));
    }

}
```

- ==은 두개의 데이터 타입이 동일한 객체인지를 알아내기 위해서 사용하는 연산자이기 때문에 b에 담긴 객체와 일치하지 않는 것이다. 이를 보안하는 비교 방법이 equals이고 이를 이용해서 서로 다른 객체들간에 값이 같은지를 비교할 수 있다
