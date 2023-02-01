#### 데이터 베이스의 목적

- 파일 : 정보 저장에 편리
  
  - 파일의 한계 : 성능, 보안, 편의성

->1960 파일의 한계를 극복하기 위해 데이터베이스 등장

- 데이터베이스 : 정보를 저장하기 위한 전문적인 프로그램

- 관계형 데이터베이스 : 정렬, 검색, 저장이 안전하고 편리

->1994 MySQL

- 오픈소스, 관계형 데이터베이스, 웹의 등장과 함께 폭발적 성장

|         | 공통             | 차이                     |
| ------- | -------------- | ---------------------- |
| 스프레드 시트 | 데이터를 표의 형태로 표현 | 사용자가 클릭을 통해서 데이터를 조작   |
| 데이터베이스  | 데이터를 표의 형태로 표현 | 명령어, 컴퓨터 언어를 통해 데이터 조작 |

- 데이터베이스의 정보를 웹사이트를 통해 누구나 볼 수 있다

- 직접 데이터베이스를 제어하지 않아도 웹에 글을 쓰는 것으로 데이터베이스에 정보가 저장

#### MySQL 구조

- table : 최종적으로 데이터를 저장하는 곳

->표가 많아지며 나눠진 표들을 정리정돈할 필요가 생김

->table들을 여러 개 그룹핑하여  schema(DB)생성

->이러한 스키마들을 저장하는 곳이 데이터베이스 서버

#### DB의 효용

- 자체적인 보안체계로 안전하게 데이터를 저장

- 권한 기능이 있어서 차등적으로 권한 부여

#### 서버접속

- mysql -u"사용자 이름" -p
  
                                          Enter password "비밀번호"

- uroot : 기본유저, 관리자, 모든 권한이 열려있음

     

#### 스키마

- DB 생성 : CREATE DATABASE "DB이름";

- DB 삭제 : DROP DATABASE "DB이름";

- DB 조회 : SHOW DATABASES;

- DB 삭제 : DROP DATABASE "DB이름";

- 테이블 생성 : USE "DB이름";

#### SQL과 테이블의 구조

- SQL : structured query language
  
  - 관계형 DB에서 데이터를 조작할 때 사용하는 언어

- 관계형 DB에 속하는 제품들을 다룰 때 SQL 사용

- table : 표
  
  - row, recored, 행 : 개별 데이터
  
  - column, 열 : 데이터의 타입, 구조

        

### CREATE 테이블 생성

- ./MySQL -uroot -p    (접속)

- USE 'DB 이름';           (사용할 DB 설정)

- <span style="color:red">CREATE TABLE table명(colunm명</span>datatype() NOT NULL AUTO_INCREMENT;

- CREATE TABLE topic(

id INT(11) NOT NULL AUTO_INCERMENT

,title VARCHAR(100) NOT NULL

,description TEXT NULL

,created DATATIME NOT NULL

,author VARCHAR(30) NULL

,profile VARCHAR(100) NULL

,primary key(id);

       

- VARCHAR(size) : 크기를 지정

- datatype() : 데이터  타입을 강제, ex) INT(11) int 타입으로 11자까지

- NOT NULL : 반드시 입력해야 하는 값 지정

- AUTO_INCREMENT : 자료 수 증가하면 +1 해줌

- primary key('') : 성능적인 측면, 중복을 방지(지정한 항목이 각각 고유한 값을 가진다)

        

    

#### CRUD

- 생성, CREATE : 가장 중요

- 읽기, READ : 두번째로 중요

- 수정, UPDATE : 상황에 따라 없음

- 삭제, DELETE : 상황에 따라 없음

    

#### INSERT (데이터 삽입)

- <span style="color:red">INSERT INTO 테이블 명(colunm명) VALUES('입력할 내용');</span>

- INSERT INTO topic()(title,description,created,author,profile) VALUES()('mysql', 'mysql is ...',now(),'egoing','developer');

    

#### SELECT (테이블 읽기)

- <span style="color:red">SELECT * FROM 테이블명;</span>

- SELECT id FROM topic <span style="color:red">WHERE</span> author = 'egoing' <span style="color:red">ORDER BY id DESC  LIMIT 2;</span> 

- SELECT * : 테이블의 전체 데이터 보기

- SELECT '칼럼명' : 해당 칼럼의 데이터 보기

- WHERE '조건' : 조건에 해당하는 데이터만 보기

- ORDER BY '칼럼명' DESC/ASC : 내림차순/오름차순으로 보기

- LIMIT 2 : 제약, 2개의 데이터 값만 보기

        

        

#### UPDATE (데이터 수정)

- <span style="color:red">UPDATE 테이블명 SET 칼럼명='수정할 내용' WHERE 조건;</span>

- UPDATE topic SET description='ORACLE is ...', title='Oracle' WHERE id=2;

       조건을 입력하지 않으면 모든 데이터를 수정하므로 주의

        

#### DELETE (데이터 삭제)

- <span style="color:red">DELETE FROM 테이블명 WHERE 조건;</span>

         조건을 입력하지 않으면 모든 데이터를 삭제하므로 주의

    

정상

본질 : 데이터베이스 (공통적 특징), (CRUD)

혁신 : 관계형

    

### 관계형 데이터베이스의 필요성

- 스프레드 시트

| id  | title      | description   | created  | author | profile        |
| --- | ---------- | ------------- | -------- | ------ | -------------- |
| 1   | MySQL      | MySQL is      | 23-01-01 | egoing | developer      |
| 2   | ORACLE     | ORACLE is     | 23-01-02 | egoing | developer      |
| 3   | SQL Server | SQL Server is | 23-01-03 | mike   | data scientist |
| 4   | PostgreSQL | PostgreSQL is | 23-01-04 | alice  | data engineer  |
| 5   | MongoDB    | MongoDB is    | 23-01-05 | egoing | developer      |

데이터의 양이 많아지면, 개별 데이터의 용량이 커지면 > 중복데이터 > 기술적, 경제적 손해 > 유지보수, 해결이 어려움

- DB로 해결

- 저자 정보를 별도의 표로 빼고 본 테이블에서 참조

| id  | name   | profile        |
| --- | ------ | -------------- |
| 1   | egoing | developer      |
| 2   | mike   | data scientist |
| 3   | alice  | data engineer  |

| id  | title      | description   | created  | author_id |
| --- | ---------- | ------------- | -------- | --------- |
| 1   | MySQL      | MySQL is      | 23-01-01 | 1         |
| 2   | ORACLE     | ORACLE is     | 23-01-02 | 1         |
| 3   | SQL Server | SQL Server is | 23-01-03 | 2         |
| 4   | PostgreSQL | PostgreSQL is | 23-01-04 | 3         |
| 5   | MongoDB    | MongoDB is    | 23-01-05 | 1         |

#### 조인

- SELECT * FROM topic LEFT JOIN author ON topic.author_id = author.id;

- 저자 테이블을 참조하는 수많은 테이블이 존재할 수  있다

- 저자 테이블만 수정하면 이를 참조하는 모든 테이블도 수정하는 효과 >유지보수에 용이

##### 인터넷과 데이터 베이스

- 인터넷을 위해서는 최소 컴퓨터 2대가 필요

- 컴퓨터1 (DB client) 요청 <-> 컴퓨터2 (DB server) 응답

#### 마치며

- 데이터가 많을수록 index(색인) 중요 > 색인을 부여해 정리하면 검색이 쉬움

- 다형화 > modeling의 중요성(정규화, 비정규화 등)

- 클라우드를 통해 DB 저장 가능
