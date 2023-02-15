### 문제1. 다음 코드의 실행 결과로 옳은 것은? 2번

```java
int i = 0;
int j = 10;


System.out.println(i++);     // 증감 연산자에서 뒤에 오게되면 참조되고 난 후 더해짐
System.out.println(++j);     // 증감 연산자에서 앞에 오게되면 참조되기 전 더해짐
```

1. 0
   
   10

2. 0
   
   11

3. 1
   
   10

4. 1
   
   11

### 문제2. 다음 코드의 실행 결과로 틀린 것은? 3번

```java
public class ContainsTest{
    public static void main(String[] args){

        String str = "my java test";

        System.out.println( str.contains("java") );  // 1번
        System.out.println( str.contains("my") );  // 2번
        System.out.println( str.contains("JAVA") );  // 3번
        System.out.println( str.contains("java test") );  // 4번

    }

}     // contains 함수는 str 안에 문자가 있는지 확JAVA는 대문자이기 때문에 str 에 없어서 
```

1. true

2. true

3. true

4. true

### 문제3. 다음중 숫자의 데이터 타입이 아닌것은? 2번

1. int

2. char

3. float

4. double
