# Quiz_김나연

- SQL에 대하여 틀린 설명을 고르시오.
  
  1) 데이터베이스 서버를 제어할 때 사용하는 컴퓨터 언어다.
  2. 데이터베이스에 무언가를 요청(질의)할 때 사용하는 언어다.
  
  3. ~~S는 Strategic으로, 표로 정리되어 전략적으로 사용할 수 있다는 뜻이다.~~
  
  4. MySQL은 SQL을 사용하여 데이터베이스를 관리하는 관계형 데이터베이스 서버 프로그램이다.

→ S는 Structured로, 표로 정리되어 구조화된 데이터에서 사용한다는 뜻이다.

---

- 다음 SQL문을 보고 맞는 것을  모두 고르시오.
  
  ```sql
  CREATE TABLE ssafy_student (
      id INT(11) NOT NULL AUTO_INCREMENT,
      name VARCHAR(10) NOT NULL,
      class_number int NOT NULL,
      enrolled DATETIME NOT NULL,
      major VARCHAR(30) NULL,
      PRIMARY KEY(id)
      )
  ```

        1. `ssafy_student` 테이블을 생성하는 SQL문이다.

        2~~. `id` 칼럼에 같은 값이 입력되면 `id` 칼럼이 두 개로 분리되어 저장된다.~~

        ~~3. `ssafy_student` 테이블은 총 5행으로 이루어져있다.~~

        4. `enrolled`칼럼에는 반드시 값이 입력되어야한다.

        ~~5. `major` 칼럼에 값을 입력하지 않으면 해당 행의 모든 데이터는 NULL처리 된다.~~

→ `id` 칼럼은 기본키로 설정되어 같은 값을 입력할 수 없다.

→ `ssafy_student` 테이블은 총 5열로 이루어져있다.

→ `major` 칼럼은 NULL 설정되어 값을 입력하지 않아도 된다.

---

- `BUK_101` 테이블의 구조를 확인하는 SQL문을 작성하시오.
  
  ```sql
  
  ```

→ `DESC BUK_101`

    : DESC는 describe의 준말로, 파이썬 판다스 라이브러리에서 데이터프레임을 사용할 때,       데이터프레임의 통계 정보를 확인할 수 있는 `.describe()` 메서드와 비슷하다.
