# Control Statements

---

## 1. 조건문(Conditional Statement)

1. if 문
    - 조건식의 결과에 따라 블록 실행 여부가 결정
    - if 문과 else문의 기본구조
    
    ```java
    if (조건문) {
    <수행할 문장1>;
    <수행할 문장2>;
    } else {
    <수행할 문장a>;
    }
    ```
    
    - 조건식이 참일 경우 문장들을 실행하고, 거짓일 경우 else 블록의 문장들을 실행한다.
    - 중첩 if 문도 가능하다.
    - if - else if - else 문
2. switch 문
    - 인자로 선택변수를 받아 변수의 값에 따라서 실행문이 결정 된다.
    - swich/case 문의 기본구조
    
    ```java
    switch(입력변수) {
    case 입력값1: ...
    			break;
    case 입력값2: ...
    			break;
    
    default: ...
    			break;
    }
    ```
    
    - 입력변수의 값과 일치하는 case 입력값(입력값1, 입력값2,…)이 있다면 해당 case문에 속한 문장들이 실행된다. break문을 만나면 switch문을 빠져나가게 되고, 빠져 있다면 그 다음의 case 문이 실행된다.

## 2. 반복문(Loop)

1. for 문
    - for 문 기본구조
    
    ```java
    for(초기화식; 조건식; 증감식){
    	반복 수행할 문장
    }
    ```
    
    - 초기화는 반복문이 시작될 때 한 번 실행된다.
    - 조건식이 false이면, 반복문이 종료된다.
    - 필요하지 않은 부분은 생략할 수 있다. for(;;)
    - 예시 for 문
    
    ```java
    String[] numbers = {"one", "two", "three"};
    for(int i=0; i<numbers.length; i++) {
        System.out.println(numbers[i]);
    }
    
    /*
    one
    two
    three
    */
    ```
    
    - 중첩 for 문도 가능하다.
2. while 문
    - while문 기본구조
    
    ```java
    while(조건식){
    반복 수행할 문장;
    }
    ```
    
    - 조건식이 true일 경우에 계속해서 반복된다.
    - 조건식 생략 불가능하다.
    - do while 문
    
    ```java
    do{
    	반복 수행할 문장;
    } while (조건식);
    ```
    
    - 블록 내용을 먼저 수행하고, 조건식을 판단한다.
- break : switch, while, do-while, for 문의 블록에서 빠져나오기 위해서 사용한다.
- continue : 반복문의 특정지점에서 제어를 반복문의 처음으로 보낸다.