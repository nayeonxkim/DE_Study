# MySQL

---

## MySQL

- **관계형 데이터베이스**
    - 데이터를 표의 형태로, 정렬・검색을 빠르고 편리하고 안전하게
- 무료・오픈소스
- “file”의 CRUD 한계 극복

---

### 1. 데이터베이스의 목적

스프레드시트 vs 데이터베이스(MySQL)

[제목 없음](https://www.notion.so/c6650189c4d24f5186e8aaee07695712)

### 2. MySQL 구조

TABLE ⊂ DATABASE(SCHEMA) ⊂ DATA SERVER

- TABLE(표) : 데이터를 기록하는 최종적인 곳
- DATABASE(SCHEMA, 데이터베이스) : 연관된 데이터들끼리 분류해주는 폴더 역할
- DATABASE SERVER(데이터베이스 서버) : 스키마들을 묶어주는 것

### 3. 데이터베이스 효용

- 보안 : 자체적인 보안
- 권한 : CRUD에 관한 권한을 차등적으로 부여 가능

### 4. 데이터베이스 사용

1. 용어정리
    - SQL(컴퓨터언어) : **S**tructured **Q**uery **L**anguage
    (구조화 되어있는 CRUD를 요청하는 언어)
    - table → 표
    - x축 → “row”, record, 행 (데이터 하나하나)
    - y축 → “column”, 열 (데이터 구조)
2. MySQL 실행
    - 터미널
    
    ```sql
    cd /usr/local/mysql/bin/
    ./mysql -u"사용자이름" -p
    password:*****
    mysql>
    ```
    
3. 테이블의 생성(**C**REATE)
    
    ```sql
    mysql> USE tutorials;
    Database changed
    mysql> CREATE TABLE topic(
        -> id INT(11) NOT NULL AUTO_INCREMENT,
        -> title VARCHAR(30) NOT NULL,
        -> description TEXT NULL,
        -> created DATETIME NOT NULL,
        -> author_id INT(11) NULL,
        -> PRIMARY KEY(id));
    Query OK, 0 rows affected, 2 warnings (0.01 sec)
    mysql> SHOW TABLES;
    +---------------------+
    | Tables_in_tutorials |
    +---------------------+
    | topic               |
    +---------------------+
    1 row in set (0.00 sec)
    mysql> DESC topic;
    +-------------+-------------+------+-----+---------+----------------+
    | Field       | Type        | Null | Key | Default | Extra          |
    +-------------+-------------+------+-----+---------+----------------+
    | id          | int         | NO   | PRI | NULL    | auto_increment |
    | title       | varchar(30) | NO   |     | NULL    |                |
    | description | text        | YES  |     | NULL    |                |
    | created     | datetime    | NO   |     | NULL    |                |
    | author_id   | int         | YES  |     | NULL    |                |
    +-------------+-------------+------+-----+---------+----------------+
    ```
    
4. 데이터 추가(**I**NSERT)
    
    ```sql
    mysql> INSERT INTO topic(id, title, description, created, author_id) VALUES(1, 'MySQL', 'MySQL is ...', '2023-01-30 22:18:55', 1);
    Query OK, 1 row affected (0.01 sec)
    ```
    
5. 데이터 보기(**S**ELECT)
    
    ```sql
    mysql> SELECT * FROM topic;
    +----+-------+--------------+---------------------+-----------+
    | id | title | description  | created             | author_id |
    +----+-------+--------------+---------------------+-----------+
    |  1 | MySQL | MySQL is ... | 2023-01-30 22:18:55 |         1 |
    +----+-------+--------------+---------------------+-----------+
    1 row in set (0.00 sec)
    ```
    
6. 데이터 수정(**U**PDATE)
    
    ```sql
    mysql> UPDATE topic SET description='Oracle is ...', title='Oracle' WHERE id=2;
    Query OK, 1 row affected (0.01 sec)
    Rows matched: 1  Changed: 1  Warnings: 0
    
    mysql> SELECT * FROM topic;
    +----+------------+------------------+---------------------+-----------+----------------+
    | id | title      | description      | created             | author    | profile        |
    +----+------------+------------------+---------------------+-----------+----------------+
    |  1 | MySQL      | MySQL is ...     | 2023-01-30 22:18:55 | egoing    | developer      |
    |  2 | Oracle     | Oracle is ...    | 2023-01-30 22:21:58 | egoing    | developer      |
    |  3 | SQL Server | SQL Server is... | 2023-01-30 22:23:41 | duru      | data engineer  |
    |  4 | PostgreSQL | PostgreSQL is... | 2023-01-30 22:24:40 | teaho     | data scientist |
    |  5 | MongoDB    | MongoDB is...    | 2023-01-30 22:27:08 | egoing    | developer      |
    +----+------------+------------------+---------------------+-----------+----------------+
    5 rows in set (0.00 sec)
    ```
    
    - WHERE문 안 써주면 데이터 전체가 바뀔 수 있으므로 조심!

1. 데이터 삭제(**D**ELETE)
    
    ```sql
    mysql> DELETE FROM topic WHERE id=5;
    Query OK, 1 row affected (0.01 sec)
    mysql> SELECT * FROM topic;
    +----+------------+-------------------+---------------------+--------+--------------------------+
    | id | title      | description       | created             | author | profile                  |
    +----+------------+-------------------+---------------------+--------+--------------------------+
    |  1 | MySQL      | MySQL is ...      | 2023-01-30 22:18:55 | egoing | developer                |
    |  2 | Oracle     | Oracle is ...     | 2023-01-30 22:21:58 | egoing | developer                |
    |  3 | SQL Server | SQL Server is ... | 2023-01-30 22:23:41 | duru   | data engineer            |
    |  4 | PostgreSQL | PostgreSQL is ... | 2023-01-30 22:24:40 | taeho  | data scientist,developer |
    +----+------------+-------------------+---------------------+--------+--------------------------+
    4 rows in set (0.00 sec)
    ```
    
2. 관계형 데이터베이스의 필요성
    - 중복된 데이터가 있다 → 개선할 것이 있다
    - 개선을 통해 유지・보수를 용이하게 한다
3. 관계형 DB의 꽃(**JOIN**)
    
    ```sql
    mysql> SELECT * FROM topic LEFT JOIN author;
    ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near '' at line 1
    mysql> SELECT * FROM topic LEFT JOIN author ON topic.author_id = author.id;
    +----+------------+-------------------+---------------------+-----------+------+--------+---------------------------+
    | id | title      | description       | created             | author_id | id   | name   | profile                   |
    +----+------------+-------------------+---------------------+-----------+------+--------+---------------------------+
    |  1 | MySQL      | MySQL is ...      | 2023-01-30 22:18:55 |         1 |    1 | egoing | developer                 |
    |  2 | Oracle     | Oracle is ...     | 2018-01-03 13:01:10 |         1 |    1 | egoing | developer                 |
    |  3 | SQL Server | SQL Server is ... | 2018-01-20 11:01:10 |         2 |    2 | duru   | database administrator    |
    |  4 | PostgreSQL | PostgreSQL is ... | 2018-01-23 01:03:03 |         3 |    3 | taeho  | data scientist, developer |
    |  5 | MongoDB    | MongoDB is ...    | 2018-01-30 12:31:03 |         1 |    1 | egoing | developer                 |
    +----+------------+-------------------+---------------------+-----------+------+--------+---------------------------+
    5 rows in set (0.00 sec)
    
    mysql> SELECT id,title,description,created,name,profile FROM topic LEFT JOIN author ON topic.author_id = author.id;
    ERROR 1052 (23000): Column 'id' in field list is ambiguous
    mysql> SELECT topic.id,title,description,created,name,profile FROM topic LEFT JOIN author ON topic.author_id = author.id;
    +----+------------+-------------------+---------------------+--------+---------------------------+
    | id | title      | description       | created             | name   | profile                   |
    +----+------------+-------------------+---------------------+--------+---------------------------+
    |  1 | MySQL      | MySQL is ...      | 2023-01-30 22:18:55 | egoing | developer                 |
    |  2 | Oracle     | Oracle is ...     | 2018-01-03 13:01:10 | egoing | developer                 |
    |  3 | SQL Server | SQL Server is ... | 2018-01-20 11:01:10 | duru   | database administrator    |
    |  4 | PostgreSQL | PostgreSQL is ... | 2018-01-23 01:03:03 | taeho  | data scientist, developer |
    |  5 | MongoDB    | MongoDB is ...    | 2018-01-30 12:31:03 | egoing | developer                 |
    +----+------------+-------------------+---------------------+--------+---------------------------+
    5 rows in set (0.00 sec)
    
    mysql> SELECT topic.id AS topic_id,title,description,created,name,profile FROM topic LEFT JOIN author ON topic.author_id = author.id;
    +----------+------------+-------------------+---------------------+--------+---------------------------+
    | topic_id | title      | description       | created             | name   | profile                   |
    +----------+------------+-------------------+---------------------+--------+---------------------------+
    |        1 | MySQL      | MySQL is ...      | 2023-01-30 22:18:55 | egoing | developer                 |
    |        2 | Oracle     | Oracle is ...     | 2018-01-03 13:01:10 | egoing | developer                 |
    |        3 | SQL Server | SQL Server is ... | 2018-01-20 11:01:10 | duru   | database administrator    |
    |        4 | PostgreSQL | PostgreSQL is ... | 2018-01-23 01:03:03 | taeho  | data scientist, developer |
    |        5 | MongoDB    | MongoDB is ...    | 2018-01-30 12:31:03 | egoing | developer                 |
    +----------+------------+-------------------+---------------------+--------+---------------------------+
    5 rows in set (0.01 sec)
    ```
    
    - 에러가 뜬 부분들은 조건을 명확히 해주지 않아서!
4.  DB
    - 인터넷에 필요한 컴퓨터 두대
    - 컴퓨터1(database client) ↔ 컴퓨터2(database server)
    - 요청하고 응답

### 5. 마무리

데이터가 많아질수록 index가 중요 → 그냥 막 넣으면 넣을땐 편하지만
찾을때 시간이 오래걸림 → index를 부여해서 정리하면 찾기 쉬움

모델링의 중요성

데이터를 안전하게 보관

클라우드를 통해 DB 저장