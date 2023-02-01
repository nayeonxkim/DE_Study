# Mysql

1. DB 구조
   
   - 표 : 데이터를 기록하는 곳
   
   - DB : 연관된 표를 그룹화하여 표와 분리하는 파일의 폴더 같은 것
   
   - 스키마 : 표들을 그룹핑할 때 사용하는 표
   
   - DB 서버 : 스키마가 많아질때 저장되는 곳

2. 서버접속
   
   - 로그인? : mysqpl -u root -p

3. 스키마 사용
   
   - CREATE : DB 만들기 (CREATE DATABSE <DBName>;)
   
   - Drop : DB 삭제 (DROP DATABASE <dbName>;)
   
   - SHOW : DB 리스트 출력. (SHOW DATABASES;)
   
   - USE : DB 사용 (USE <dbName>;)

4. 테이블 생성
   
   - CREATE TABLE <tableName>(<varName> <varType> [<option>] , ... , PRIMARY KEY(id));
   
   - INT(n) : n번째 자리까지 노출
   
   - VARCHAR(size) : 문자열
   
   - DATE : 날짜 표현
   
   - PRIMARY KEY(id) : 기본키, DB에게 id column이 기본키라는 것을 알려준다, id column 은 각각의 행을 식별하는 식별자
   
   - NULL : NULL 값을 허용함
   
   - NOT NULL : 값이 없는채로 추가되는 것을 방지함
   
   - AUTO INCREMENT : id 와 같은 값이 자동으로 증가

5. CRUD
   
   - CREATE , READ, UPDATE, DELETE의 의미
   
   - INSET INTO <table>  (<var1> ...) VALUES(<val1> ...) => CREATE 의 느낌

6. SELECT
   
   - SELECT <col1>, <col2> ... FROM <table> WHERE <val>=<var~>;
   
   - SELECT <col1>, <col2> ... FROM <table> [WHERE <val>=<val1~>] ORDER BY <val1> [<option>];
   
   - SELECT <col1>, <col2> ... FROM <table> [WHERE <val>=<val1~>] ORDER BY <val1> [<option>] LIMIT <N>;

7. UPDATE
   
   - UPDATE <table> SET <val1>=<val1~>, <val2>=<val2~>, ... WHERE id=<N>;

8. DELETE
   
   - DELETE FROM <table> WHERE id=<N>;

9. JOIN
   
   - SELECT * FROM <table1> LEFT JOIN <table2> ON <table1>.<val1> = <table2>.<val2>;
