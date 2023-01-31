# MySQL

### MySQL의 구조

- 데이터를 표 형태로 나타낸다.

- 서로 연관된 표들을 그룹핑한 것을 스키마(or 데이터베이스)라고 한다.

- 여러 스키마들을 저장하는 곳 = '데이터베이스 서버'

- MySQL = 데이터베이스 서버 프로그램

---

### SQL

**S**tructured **Q**uery **L**anguage

- 표로 정리정돈 되었다 = Structured

- 데이터베이스에 무언가를 요청(질의)한다 = Query

- 데이터베이스가 알아들을 수 있는 언어 = Language

=> SQL은 데이터베이스 서버를 제어할 때 사용하는 컴퓨터 언어

---

### 데이터베이스 서버 접근

- 사용자 등록

- uroot : 루트 사용자, 모든 권한 가짐
  
  - 루트 권한으로 작업하는 것은 위험하기 때문에 다른 사용자로 작업하고 중요한 작업이 있을 때만 루트로 작업하기.

- 데이터베이스에 로그인

```sql
bin ./mysql -uroot -p
```

- `-p` : 비밀번호를 입력할게요
  
  - 비밀번호 입력하면 로그인 완료

---

- 스키마 (데이터베이스) 생성

```sql
CREATE DATABASE dbname;
```

- 존재하는 데이터베이스 (스키마) 확인

```sql
SHOW DATABASES;
```

- 생성한 데이터베이스 (스키마)에 테이블 만들기
  
  - 우선, 어떤 스키마에서 작업할 것인지 명령어로 알려준다.

```sql
USE dbname;
# dbname이라는 스키마에서 작업할거야~
```

**모든 명령어는 외우지말고 그때그때 검색하면서 찾아쓰기 (cheat sheet)**

```sql
CREATE TABLE tablename(
    id INT(11) NOT NULL AUTO_INCREMENT,
    title VARCHAR(100) NOT NULL,
    description TEXT NULL,
    ㅊ
    )
```

- `tablename` 이라는 테이블에

- `id`라는 칼럼을 생성한다.
  
  - `id` 칼럼은 정수값 11자리까지 들어올 수 있고,
  
  - 무조건 존재해야한다.
  
  - 하나씩 자동으로 증가한다.

- `title` 칼럼을 생성한다.
  
  - `title`칼럼은 문자열 100개까지만 들어갈 수 있고,
  
  - 그 이상으로 입력된 값은 자동으로 버려진다.
  
  - 무조건 존재해야한다.

- `description` 칼럼을 생성한다.
  
  - 문자가 들어올 수 있고,
  
  - 입력하지 않아도 된다.

---

### PRIMARY KEY

- 중복 방지 : 어떤 칼럼을 기본키로 지정하면 해당 칼럼은 입력값 중복을 방지한다.
- 성능적 측면 : 추후

---

### CREATE/INSERT

- 테이블에 데이터 입력하기
- 먼저, 테이블의 구조를 확인해보자.

```sql
DESC topic;
```

- 테이블 구조를 참고하여 MySQL에 대한 행을 추가하자.

```sql
INSERT INTO topic (title, description,created) VALUES('MySQL', 'MySQL is DataBase program', NOW())
```

- 테이블 (칼럼명) VALUES (데이터)
- NOW() : 현재 일자 출력 함수

---

### READ (=SELECT)

- 토픽 테이블에서 모든 데이터 확인하기

```sql
SELECT * FROM topic;
```

FROM

WHERE

GROUP BY

HAVING
ORDER BY

- MySQL은 매우매우 큰 데이터를 저장해두기 때문에 데이터를 가져올 때 제약을 걸어야한다. -

→ 무작정 SELECT * 하지말 것 그럼 1억 건 다 불러옴 ㄷㄷ

---

### UPDATE

```sql
UPDATE topic SET description = 'Oracle' WHERE id =2;
```

- id가 2인 행에 대하여
- description 칼럼의 값을 ‘Oracle’로
- topic 테이블을 수정한다.

---

### DELETE

```sql
DELETE FROM topic WHERE id = 5;
```

- id 값이 5인 행에 대하여
- topic 테이블을 삭제한다.
