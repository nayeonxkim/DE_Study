# Java study

> # 1. 튜토리얼

- Package Explorer : 우리의 프로젝트를 관리하는 도구

- Outline : 어떤 소스코드가 있는데 그 소스코드에는 여러가지 문법적인  요소들이 있는데 그런 요소들을 시각적으로 표시해서 어떤 명령어 어떤 요소들로 이 프로그램들이 이루어져 있는지 일목요연하게 보여주고 자신이 필요한 것들을 빠르게 찾을 수 있는 것.

- Consol : 출력창

- source (src) : .java 라는 확장자를 가지고 있는 파일들

- binary(bin) : 실행파일, 확장자가 .class로 끝나는 파일들

- package 만들기(상위폴더?)

- class 만들기 (.py랑 비슷한것 같음)

> # 2. 숫자와 문자

- 정수형과 실수형
  
  - ```java
    System.out.println(1+2);
    System.out.println(1.2+1.3);
    System.out.println(2*5);
    System.out.println(6/2);
    ```

- 문자와 문자열
  
  - 문자는 '작은 따옴표'로 감싸야 한다
  
  - 문자열은 "큰 따옴표"로 감싸야 한다
  
  - 문자열 앞에 따옴표를 넣고 싶다면 따옴표 안에 \ 이것을 넣어주면 된다
  
  - ```java
    system.out.println("\"생활코딩\" 입니다); //"생활코딩" 입니다
    ```

> # 3. 변수

- 사용하고자 하는 변수 앞에 변수형을 선언해주어야 한다
  
  - ```java
    int a;
    a = 1;
    System.out.println(a+1); //2
    
    a = 2;
    System.out.println(a+1); //3
    ```

> # 4. 주석과 세미콜론

- 주석은 // 을 통해 달수 있다

- 여러줄주석은 /*  사이와 */ 사이에 할 수 있다

- JavaDoc 주석 : /**로 시작하는 주석은 JavaDoc 주석이라고 해서 자바의 문서를 만들 때 사용한다. 아래 예제는 다음 URL의 문서를 생성한다.

- 세미콜론 : 문장의 끝을 의미한다. 자바에서의 문장의 끝에 세미콜론을 사용하지 않으면 컴파일 에러가 발생한다

- 세미콜론을 이용하면 여러개의 문장을 한줄에 표현할 수 있다.
  
  - ```java
    int a = 100; double b = 10.1;
    ```

> # 5. 숫자

- 정수
  
  - int  : -2147483648 ~ 2147483647
  
  - long : -9223372036854775808 ~ 9223372036854775807

- 실수
  
  - float : -3.4 * 10^38 ~ 3.4 * 10^38
  
  - double : -1.7 * 10^308 ~ 1.7 * 10^308(디폴트)

- 진수
  
  - octal : 8진수
  
  - hex : 16진수

> # 6. 문자열

- 원시(primitive) 자료형

- int, long, double, float, boolean, char 자료형을 원시(primitive) 자료형 이라고 부른다. 이런 primitive 자료형은 `new` 키워드로 그 값을 생성할 수 없다.

- | 원시자료형   | Wrapper 클래스 |
  | ------- | ----------- |
  | int     | Integer     |
  | long    | Long        |
  | double  | Double      |
  | float   | Float       |
  | boolean | Boolean     |
  | char    | Char        |

- 문자열 내장 메서드
  
  - a.equals(b) = 이면 a와 b의 문자열을 비교
    
    - == 를 사용하면 같은 문자열이라도 객체가 달라져 버리면 false를 리턴
  
  - indexOf : 문자열에서 특정 문자열이 시작되는 위치를 리턴
  
  - contains : 문자열에서 특정 문자열이 포함되어 있는지의 여부를 리턴
  
  - chartAt : 문자열에서 특정 위치의 문자(char)를 리턴
  
  - replaceAl : 문자열 중 특정 문자열을 다른 문자열로 바꾸고자 할 때 사용
  
  - substring : 문자열 중 특정 부분을 뽑아낼 경우 사용
  
  - toUpperCasr : 문자열을 모두 대문자
  
  - Split : 문자열을 특정 구분자로 나누어 문자열 배열로 리턴
  
  - 포맷
    
    - ```java
      System.out.println(String.format("I eat %d apples.", 3));  // "I eat 3 apples." 출력
      ```
    
    - ```java
      System.out.println(String.format("I eat %s apples.", "five"));  // "I eat five apples." 출력
      ```
    
    - ```java
      int number = 3;
      System.out.println(String.format("I eat %d apples.", number));  // "I eat 3 apples." 출력
      ```
    
    - ```java
      int number = 10;
      String day = "three";
      System.out.println(String.format("I ate %d apples. so I was sick for %s days.", number, day));
      ```

- 문자열 포맷 코드
  
  | 코드  | 설명                    |
  | --- | --------------------- |
  | %s  | 문자열(String)           |
  | %c  | 문자 1개(character)      |
  | %d  | 정수(Integer)           |
  | %f  | 부동소수(floating-point)  |
  | %o  | 8진수                   |
  | %x  | 16진수                  |
  | %%  | Literal % (문자 `%` 자체) |

- StringBuffer
  
  - append : 계속해서 문자열을 추가
  
  - insert : 특정 위치에 원하는 문자열을 삽입할 수 있다
  
  - substring : substring(시작위치, 끝위치)와 같이 사용하면 StringBuffer 객체의 시작위치에서 끝위치까지의 문자를 뽑아낸다

> ## 7. 배열

- int[] odds = {1,3,5,7,9};

- String[] weeks = {"월", "화", "수", "목", "금", "토", "일"};

혹은

```java
String[] weeks = new String[7];
weeks[0] = "월";
weeks[1] = "화";
weeks[2] = "수";
weeks[3] = "목";
weeks[4] = "금";
weeks[5] = "토";
weeks[6] = "일"; // 이렇게도 가능
```

- weeks[3] = "목"  요부분은 파이썬이랑 동일함

> # 8. List

- ArrayList
  
  - add(n,m) : n 번째 위치에 m 을 삽입
  
  - self.get(n) : 리스트에 n번째 위치 값을 출력
  
  - self.size : 리스트의 개수를 출력
  
  - self.contains(m) : 리스트에 m이 있는지 없는지 확인 있으면 true 없으면 false
  
  - self.remove(m) : 리스트에 m 을 삭제 후 삭제한 결과(true, false)를 리턴
  
  - self.remove(인덱스) : 해당항목을 삭제하고 , 삭제된 항목을 리턴 
  
  - join(",",list) : 리스트안에 모든 요소들 사이에  콤마(,)를 집어넣어 출력
  
  - 리스트 정렬 : import java.util.Comparator; -> 

                                    pitches.sort(Comparator.naturalOrder()); // 오름차순

                                    pitches.sort(Comparator.reverseOrder()); // 내림차순

> # 9. Map(key,value, 딕셔러니)

- HashMap(import java.util.HashMap;)
  
  - map.put(key,value) : 이용해 값을 집어넣음
  
  - map.get(key) = value
  
  - map.containsKey(Key) : 키가 있는지 없는지
  
  - map.remove(Key) : Key 에 해당되는 value 를 삭제후 값을 리턴
  
  - map.size() : map의 개수를 리턴
  
  - map.keySet() : map 의 모든 키를 모아서 리턴

> # 10. set

- Hashset(import java.util.HashSet;)
  
  ```java
  import java.util.Arrays;
  import java.util.HashSet;
  
  public class Sample {
      public static void main(String[] args) {
          HashSet<String> set = new HashSet<>(Arrays.asList("H", "e", "l", "l", "o"));
          System.out.println(set);  //  [e, H, l, o] 출력
      }
  }
  ```

- 교집합

```java
        HashSet<Integer> intersection = new HashSet<>(s1);  // s1으로 intersection 생성
        intersection.retainAll(s2);  // 교집합 수행
        System.out.println(intersection);
```

- 합집합

```java
        HashSet<Integer> union = new HashSet<>(s1);  // s1으로 union 생성
        union.addAll(s2); // 합집합 수행
        System.out.println(union);  // [1, 2, 3, 4, 5, 6, 7, 8, 9] 출력
```

- 차집합

```java
substract.removeAll(s2)
```

- 집합 자료형 관련 메서드
  
  - set.add
  
  - set.addAll
  
  - set.remove

> # 11. 형변환과 final

- 형변환
  
  - int n = Integer.parseInt(num); = 문자열을 정수로
  
  - String num = "" + n;  = 정수를 문자열로
  
  - String num1 = String.valueOf(n);  = 정수를 문자열로
  
  - String num2 = Integer.toString(n);  = 정수를 문자열로
  
  - double d = Double.parseDouble(num); = 문자열을 실수로
  
  - int n2 = (int) d2; = 정수와 실수 사이로 변환

- final
  
  - 자바의 final은 자료형에 값을 단 한번만 설정할수 있게 강제하는 키워드이다. 즉, 값을 한번 설정하면 그 값을 다시 설정할 수 없다는 말이다.



> ## 12. if 문

- if 문 구조
  
  ```java
  if (조건문) {
      <수행할 문장1>;
      <수행할 문장2>;
      ...
  } else if{
      <수행할 문장A>;
      <수행할 문장B>;
      ...
  } else{
      <수행할 문장>; 
  }
  ```

- `x && y` - x와 y 모두 참이어야 참이다
- `x || y` - x와 y 둘 중 적어도 하나가 참이면 참이다
- `!x` - x가 거짓이면 참이다
- contains : 리스트에서 해당 아이템이 있는지 조사하는 매서드
  
  ```java
  pocket.contains("money") // pocket 리스트 안에 "money" 가 있으면 true 없으면 false
  ```

> ## 13. case 문

```java
public class Sample {
    public static void main(String[] args) {
        int month = 8;
        String monthString = "";
        switch (month) {
            case 1:  monthString = "January";
                     break;
            case 2:  monthString = "February";
                     break;
            case 3:  monthString = "March";
                     break;
            case 4:  monthString = "April";
                     break;
            case 5:  monthString = "May";
                     break;
            case 6:  monthString = "June";
                     break;
            case 7:  monthString = "July";
                     break;
            case 8:  monthString = "August";
                     break;
            case 9:  monthString = "September";
                     break;
            case 10: monthString = "October";
                     break;
            case 11: monthString = "November";
                     break;
            case 12: monthString = "December";
                     break;
            default: monthString = "Invalid month";
                     break;
        }
        System.out.println(monthString);   // August
    }  
}
```

- switch/case 문은 if else 구조로 변경이 가능하지만 if else 구조로 작성된 모든 코드를 switch 문으로 변경할 수는 없다.
- switch 조건문에 들어갈 수 있는 입력 변수의 타입은 byte, short, char, int만 가능하다.



> # 14. while문

```java
while (조건문) {
    <수행할 문장1>;
    <수행할 문장2>;
    <수행할 문장3>;
    ...
}
```

```java
int treeHit = 0;
while (treeHit < 10) {
    treeHit++;
    System.out.println("나무를  " + treeHit + "번 찍었습니다.");
    if (treeHit == 10) {
        System.out.println("나무 넘어갑니다.");
    }
}
```

```java
나무를  1번 찍었습니다.
나무를  2번 찍었습니다.
나무를  3번 찍었습니다.
나무를  4번 찍었습니다.
나무를  5번 찍었습니다.
나무를  6번 찍었습니다.
나무를  7번 찍었습니다.
나무를  8번 찍었습니다.
나무를  9번 찍었습니다.
나무를  10번 찍었습니다.
나무 넘어갑니다.
```



> ## 15. for 문

```java
for (초기치; 조건문; 증가치) {
    ...
}
```



```java
String[] numbers = {"one", "two", "three"};
for(int i=0; i<numbers.length; i++) {
    System.out.println(numbers[i]);
}
```

```java
one
two
three
```





> ## 16. for each 문

```java
for (type var: iterate) {
    body-of-loop
}
```

```java
// 위 for 문을 이렇게 도 가능


String[] numbers = {"one", "two", "three"};
for(String number: numbers) {
    System.out.println(number);
}
```

```java
one
two
three
```
