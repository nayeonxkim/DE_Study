# JAVA

---

## 1. 자바에 대하여

- 1995년 제임스 고슬링(James Gosling)과 다른 연구원들이 개발한 객체 지향적 프로그래밍 언어
- 처음에는 가전제품 내에 탑재해 동작하는 프로그램을 위해 개발
- 현재는 웹 어플리케이션, 모바일 앱 개발에 가장 많이 사용하는 언어

## 2. 자바의 특징

- 간단하다(Simple)
    
    C++에 가깝지만 훨씬 간단하다.
    
- 객체 지향적이다(Object-oriented)
    
    숫자(int, float, long 등)나 논리값(True, False)을 제외한 거의 모든 것이 객체로 구성되어 있다.
    
- 인터프리터 언어이다(Interpreted)
    
    정확히 말하면 컴파일 언어인 동시에 인터프리터 언어이다.
    
- 강력하다(Robust)
    
    포인터 연산을 지원하지 않는다. 모든 메모리 접근을 자바 시스템이 관리하고 제한하며 또한 예외 핸들링을 하여 시스템 붕괴의 우려가 없다.
    
- 안전하다(Secured)
    
    프로그램 작성 시 자료형 타입에 민감하다. 이는 코드를 매우 명확하게 만들어주는 힘이 있다.
    
- 플랫폼 독립적이다(Platform independent)
    
    실행 파일이 이진 코드(클래스) 파일이다. 따라서 자바 런타임이 설치된 시스템에서는 어디서나(OS에 관계없이) 자바 프로그램을 실행할 수 있다.
    
- 멀티 쓰레딩을 지원한다(Multithreaded)
    
    하나의 프로그램 단위가 동일한 쓰레드를 동시에 수행할 수 있다.
    
- 동적이다(Dynamic)
    
    자바 인터페이스를 이용하면 하나의 모듈을 갱신할 때 다른 모듈을 모두 갱신할 필요가 없다.
    

## 3. 실행

- 코드
    
    코드(code) 혹은 소스(source)는 프로그램이 어떤 모습이고, 어떻게 동작해야 하는가를 표현한 일종의 설계도라고 할 수 있다. 프로그래밍에서의 설계도는 그 프로그램 자체라고도 할 수 있다. 코드는 자바의 문법에 맞게 만들어진 텍스트 파일이고, 이 파일의 확장자는 **.java**를 사용한다.
    
- 컴파일
    
    코드 자체를 바로 실행할 수는 없다. 코드를 컴퓨터가 이해할 수 있는 상태로 변환해주는 과정이 필요한데 이것을 컴파일(compile)이라고 하고, 이 작업을 하는 소프트웨어를 컴파일러(compiler)라고 부른다. 자바의 컴파일러는 **javac** 라는 이름을 가지고 있다.
    
- 실행
    
    ```bash
    javac Helloworld.java
    ```
    
    위의 명령을 실행하면 같은 디렉터리에 Helloworld.class라는 이름의 파일이 생성된다. 이 파일이 컴파일된 파일이고, 실행파일이라고 할 수 있다. 컴파일된 파일을 실행시켜주는 프로그램을 이용해야 한다. 이 작업을 하는 프로그램을 런쳐(launcher)라고 한다. 아래와 같이 실행한다.
    
    ```bash
    java Helloworld
    ```
    
    최종적으로 자바 가상머신을 통해 동작하게 된다.
    
    ![Untitled](JAVA%20e041ac7333c84df2bb65df8d5f792185/Untitled.png)
    

[Start of Java](https://www.notion.so/Start-of-Java-33d51ee092984fd3ad060240a89bb456)

[Data Type](https://www.notion.so/Data-Type-af8e272a10c542cfb6d94c100bce05b0)

[Control Statements](https://www.notion.so/Control-Statements-1da5bdfa35b4469791e34768bd9fce95)

[Quiz_박하윤](https://www.notion.so/Quiz_-f8603aba85204af2ab117206f98acb0e)

[Answer_박하윤](https://www.notion.so/Answer_-4d6294ca76f34220859fd887a4d5c6fd)