### 문제1
다음 코드의 실행 결과로 올바른 것을 고르시오
```java
String a = "Hello World"; 
String b = new String("Hello World");
System.out.println(a == b);
System.out.println(a.equals(b));
```
1. true, true
2. true, false
3. false, true
4. false, false

### 문제2
다음 코드의 실행 결과로 올바른 것을 고르시오
```java
switch(2) { 
case 1: System.out.println("one"); 
case 2: System.out.println("two"); 
case 3: System.out.println("three");
default: System.out.println("D");
}
```
1. two
2. two, three
3. two, three, default
4. default

### 문제3
다음 코드의 실행 결과에서 포함되지 않는 멤버를 모두 고르시오
```java
String[] lesserafim = {"김채원", "카즈하", "허윤진", "사쿠라", "홍은채"}; 
for (int i = 2; i < lesserafim.length; ++i) { 
String member = lesserafim[i];
System.out.println(member);
}
```
1. 김채원
2. 카즈하
3. 허윤진
4. 사쿠라
5. 홍은채
