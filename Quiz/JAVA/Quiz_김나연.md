1. 다음 중 실행 시 에러가 발생하지 않는 자바 코드는 ?
- `String name = '김나연';`

- `long number = 2147483648;`

- `double number = 20.23F;`

- `short class_number = "1";`

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
```

---

3. 주석과 세미콜론에 대한 설명 중 틀린 것을 고르시오.
- `//`은 한 줄 주석을 의미하는 기호다.

- `/*` 로 시작해서 `*/` 로 문장을 묶어주면 여러 줄로 주석을 작성할 수 있다.

- `/**`로 시작해서 `*/`로 문장을 묶어주는 것은 JavaDoc 주석으로, 자바의 문서를 만드는 주석 형식이다.

- `;` 세미콜론을 사용하여 문장을 구분해주며 한 줄에 한 문장만 입력할 수 있다.
