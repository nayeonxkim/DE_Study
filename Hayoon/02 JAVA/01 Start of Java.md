# Start of Java

---

## 1. 자바 소스코드의 구조

```java
/* 클래스 블록 */
public class 클래스명 {

    /* 메서드 블록 */
    [public|private|protected] [static] (리턴자료형|void) 메서드명1(입력자료형 매개변수, ...) {
        명령문(statement);
        ...
    }

    /* 메서드 블록 */
    [public|private|protected] [static] (리턴자료형|void) 메서드명2(입력자료형 매개변수, ...) {
        명령문(statement);
        ...
    }

    ...
}
```

- 소스코드의 가장 바깥쪽 영역은 클래스 블록이다. 클래스명은 소스파일의 이름(클래스명.java)과 동일하게 사용해야 한다.
- **형태**
    
    **[public] [static] (리턴자료형 or void) main(String [] args) {}**
    
    -main method : java실행시 가장 먼저 호출되는 부분
    
    - 만약 main() 메서드가 없다면 절대로 실행 될 수 없다.
    - (리턴자료형 or void) 이 부분도 생략 될 수 없다.
    - 명령문은 반드시 세미콜론(;)을 붙여 문장의 끝을 표시해야 한다.

## 2. 주석

- //내용 : 해당 기호가 있는 위치부터 그 줄 끝까지 주석처리(라인주석)
- /*내용*/ : 해당 범위의 내용 주석처리(블록주석)
- /**내용*/ : Documantation API를 위한 주석처리

```java
//해당 줄을 주석처리

/*
해당 범위의 내용을 주석처리
*/

/**
Documentation API를 위한 주석처리
*/
```

## 3. 출력문

- print
- println
- printf
    - %d : 정수
    - %f : 실수
    - %c : 문자
    - %s : 문자열

## 4. 변수와 자료형

1. 변수 : 데이터를 저장할 메모리의 위치를 나타내는 이름
- 규칙
    
    -대소문자를 구분한다.
    
    -공백은 허용되지 않는다.
    
    -숫자로 시작할 수 없다.
    
    -’$’와 ‘_’를 변수이름에 사용할 수 있다. 이외의 특수문자는 안된다.
    
    -예약어(keyword)는 사용할 수 없다.
    
    -합성어의 경우 주로 CamelCase를 활용한다.
    
    -한글을 이용한 변수 작명이 가능하다.
    

![Screenshot 2023-02-14 at 20.55.58.jpg](Start%20of%20Java%2033d51ee092984fd3ad060240a89bb456/Screenshot_2023-02-14_at_20.55.58.jpg)

1. 자료형
- 기본(원시) 자료형
- 참조 자료형(기본 자료형 8가지 외 모든것)
- 사용자 정의 자료형

## 5. 명명 규칙

1. 클래스명
    - 클래스명은 명사로 한다.
    - 여러개의 단어가 섞이는 경우 각 단어의 첫 문자는 대문자(CamelCase)
2. 메서드명
    - 메서드명은 동사로 한다.
    - 클래스명과 마찬가지로 여러개의 단어가 섞이는 경우 각 단어의 첫 문자는 대문자. 단, 처음 시작하는 문자는 항상 소문자로 시작한다.
3. 변수명
    - 변수 이름은 짧지만 의미가 있어야 한다.
    - 순서를 의하는 임시적인 경우 정수의 변수명은 i, j, k, m, n을 사용한다.(문자의 경우 c, d, e)
    - 변수명에 ‘_’, ‘$’기호를 사용할 수 있지만 시작 문자로 사용하지 않는다.