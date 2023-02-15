1. 다음 중 실행 시 에러가 발생하지 않는 자바 코드는 ?
- `String name = '김나연';` 
  
  : 문자열을 `'` 로 감싸면 에러발생 → `"`를 사용해야한다.

- `long number = 2147483648;`
  
  : 2147483647까지는 int 범위라서 `long` 데이터타입에 할당해도 에러가 발생하지 않는다.  그러나 2147483648부터는 long의 범위이기 때문에 숫자 뒤에 `L`을 붙여주어야 에러가 발생하지 않는다.

- ~~`double number = 20.23F;`~~
  
  : double은 float보다 허용범위가 넓은 실수형 데이터타입이다. 따라서 `double` 데이터 타입에 float 상수를 할당해도 에러가 발생하지 않고 정상적으로 할당된다.

- `short class_number = "1";`
  
  : `short`는 2 byte의 메모리 크기를 가지는 정수형 데이터 타입이다. 데이터의 모양은 1로, 정수같아보이지만 `"` 로 묶어주어 문자열로 인식된다. 따라서 에러가 발생한다.

---

2. 다음 자바 코드의 실행 결과를 예상하여 작성하시오.

```java
package org.opentutorials.Javatutorials.loop;

public class switchDemo {

    public static void main(String[] args) {

        String[] DE_Study = new String[5];

        for (int i = 0; i < DE_Study.length;i++) {

            if (i%2 == 0)
                continue;

            DE_Study[i] = "스터디 완료! 데엔 뿌셔뿌셔!";    

        }

        switch(DE_Study.length) {
        case 2:
            System.out.println("one");
        case 5:
            System.out.println("two");
        case 3:
            System.out.println("three");
            break;
        case 4:
            System.out.println("four");
        default:
            System.out.println("default");
        }

    }

}


//정답
>>> one
>>> two
```

- `.length` 메서드는 배열을 처음 생성할 때 지정한 '초기 배열의 크기'를 반환한다. 따라서 `DE_Study.length` 는 5다.

- 반복문을 실행하면 `DE_Study`의 0부터 4 인덱스까지 순회하며 짝수 인덱스는 건너뛰고, 홀수 인덱스에 문자열을 할당한다.

- `switch(5)`와 일치하는 `case 5` 부터 실행된다.

- `case 3`까지 실행된 이후 `break` 가 작동되어 조건문 실행을 멈춘다.

---

3. 주석과 세미콜론에 대한 설명 중 틀린 것을 고르시오.
- `//`은 한 줄 주석을 의미하는 기호다.

- `/*` 로 시작해서 `*/` 로 문장을 묶어주면 여러 줄로 주석을 작성할 수 있다.

- `/**`로 시작해서 `*/`로 문장을 묶어주는 것은 JavaDoc 주석으로, 자바의 문서를 만드는 주석 형식이다.

- ~~`;` 세미콜론을 사용하여 문장을 구분해주며 한 줄에 한 문장만 입력할 수 있다.~~
  
  : 자바는 파이썬과 달리 모든 문장끝에 반드시 `;`을 붙여주어야한다. 다음과 같이 한 줄에 여러 문장을 입력할 수 있다.
  
  ```java
  int a = 70; String str = "스터디 끝!"; 
  ```
