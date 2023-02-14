# week_3

복습: No
작성일시: 2023년 2월 13일 오후 11:28

### 이클립스 기본 형태

```java
package study;

public class Feb13 {

	public static void main(String[] args) {
		System.out.println("Hello World");
	}

}
```

### 숫자와 문자

```java
//사칙연산
System.out.println(1+2); //3
System.out.println(1.2+1.3); //2.5
System.out.println(2*5); //10
System.out.println(6/2); //3
//문자와 문자열
System.out.println('자'); //자
System.out.println("자바"); //자바
System.out.println("생"); //생
//이스케이프
System.out.println("JAVA is the \"BEST\" language."); //JAVA is the "BEST" language.
//줄바꿈
System.out.println("JAVA\nPython\nC++");
//문자 연산
System.out.println("JA"+"VA"); //JAVA
```

### 변수

```java
//정수
int a;
a = 1;
System.out.println(a+1); //2
//실수
double b = 1.1;
System.out.println(b+1.1); //2.2
b = 2.1;
System.out.println(b+1.1); //3.2

//문자
String first, second;
first = "JAVA"; second = "Script";
System.out.println(first+second); //JAVAScript
```

### 주석

```java
//한 줄 주석
		
/*
 여러 줄 주석
 여러 줄 주석
 */

/**
 * JavaDoc 주석
 * 자바의 문서를 만들 때 사용
 */

//여러 문장 한줄에 표현
int aa = 100; double bb = 10.1;
```

### 자료형

| 자료형 | 메모리 크기 |  표현 가능 범위 |
| --- | --- | --- |
| byte | 1byte | -128 ~ 127 |
| short | 2byte | -32,768 ~ 32,767 |
| int | 4byte | -2,147,483,648~2,147,483,647 |
| long | 8byte | -9,223,372,036,854,775,808 ~ 9,223,372,036,854,775,807 |
| float | 4byte | ±(1.40129846432481707e-45 ~ 3.40282346638528860e+38) |
| double | 8byte | ±(4.94065645841246544e-324d ~ 1.79769313486231570e+308d) |
| char | 2byte | 모든 유니코드 문자 |

### 상수 표현, 형 변환

```java
//상수 자료형 표현
//long l = 2147483648; 에
long l = 2147483648L;
System.out.println(l); //2147483648

//자동 형 변환
int a = 3;
float b = 1.0F;
double c = a + b; //4.0

//명시적 형 변환
float a = (float)100.0;
int b = (int)100.0F;
```

### 연산자, 비교연산자와 boolean

```java
//단항 연산자
int i = 3;
i++;
System.out.println(i); //4
++i'
System.out.println(i); //5
System.out.println(++i); //6
System.out.println(i++); //6
System.out.println(i); //7

//비교연산자
String a = "Hello World";
String b = new String("Hello World");
System.out.println(a == b); //False, 객체의 일치 여부
System.out.println(a.equals(b)); //True, 객체의 값 일치 여부
```

### 조건문

```java
//if
if(true){
    System.out.println("true");
} //true

if(false){
    System.out.println("true");
} //출력되지 않음

if(false){
    System.out.println(1);
}
System.out.println(2); // 2

//if, else
if(true) {
    System.out.println(1);
} else {
    System.out.println(2);
} //1

if(false) {
    System.out.println(1);
} else {
    System.out.println(2);
} //2

//if, else if, else
if(false) {
    System.out.println(1);
} else if (true) {
    System.out.println(2);
} else (true) {
    System.out.println(3);
} //2

//중첩
String id = args[0];
String password = args[1];
if (id.equals("asdf")) {
    if (password.equals("11111111")) {
        System.out.println("right");
    } else {
        System.out.println("wrong");
    }

} else {
    System.out.println("wrong");
}

//switch
switch(1) {
case 1:
    System.out.println("one");
case 2:
    System.out.println("two");
case 3:
    System.out.println("three");
} //one two three

switch(2) {
case 1:
    System.out.println("one");
case 2:
    System.out.println("two");
case 3:
    System.out.println("three");
} //two three

switch(2) {
case 1:
    System.out.println("one");
case 2:
    System.out.println("two");
    break;
case 3:
    System.out.println("three");
} //two

switch(4) {
case 1:
    System.out.println("one");
case 2:
    System.out.println("two");
case 3:
    System.out.println("three");
default:
    System.out.println("D");
} //D
```

### 논리연산자

```java
if (true && true) {
    System.out.println(1);
} //1
if (true && false) {
    System.out.println(1);
} //출력되지 않음
if (true || false) {
    System.out.println(1);
} //1
if (!false) {
    System.out.println(1);
} //1
if (!true) {
    System.out.println(1);
} //출력되지 않음
```

### 반복문

```java
//while
while (true) {
    System.out.println("Hello");
} //Hello 무한반복

int i = 0;
while(i<10){
    System.out.println(i);
    i++;
} //0, 1, 2...8, 9

//for
for (int i = 0; i < 10; i++) {
    System.out.println(i);
} // 0, 1, 2...8, 9

//break
for (int i = 0; i < 10; i++) {
    if (i == 5)
        break;
    System.out.println(i);
} // 0, 1, 2, 3, 4

//continue
for (int i = 0; i < 10; i++) {
    if (i == 5)
        continue;
    System.out.println(i);
} //0, 1, 2, 3, 4, 6, 7, 8, 9

//중첩
for (int i = 0; i < 10; i ++) {
    for (int j = 0; j < 10; j++) {
        System.out.println(i + "" + j);
    }
} //00, 01, 02...98, 99
```

### 배열

```java
//생성
String[] lesserafim = {"김채원", "카즈하", "허윤진", "사쿠라", "홍은채"};
System.out.println(lesserafim[0]); // 김채원
System.out.println(lesserafim.length); // 5

//사용
String[] lesserafim = {"김채원", "카즈하", "허윤진", "사쿠라", "홍은채"};
for (int i = 0; i < lesserafim.length; i++) {
    String member = lessearfim[i];
    System.out.println(member);
} // 김채원, 카즈하, 허윤진, 사쿠라, 홍은채

//for-each
String[] lesserafim = {"김채원", "카즈하", "허윤진", "사쿠라", "홍은채"};
for (String e : lessearfim) {
    System.out.println(e);
} // 김채원, 카즈하, 허윤진, 사쿠라, 홍은채
```