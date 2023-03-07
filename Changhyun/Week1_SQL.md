# week_1

복습: No
작성일시: 2023년 1월 26일 오후 1:42

## Database 1

데이터를 가공해 소식과 지식을 전파, 대규모 데이터로부터 통찰력 있는 분석 결과 도출 가능

데이터를 저장하고 꺼낼 수 있는 수단 → 배우기가 쉽고 어디에서나 사용 가능, 전송 가능한 **file**

file은 성능, 보안, 편의성의 한계 → 한계를 극복하기 위한 전문화된 SW인 **DB**

---

DB의 data를 **어떻게 입/출력할지** 파악하는 것이 가장 중요

- **Input**: Create, Update, Delete
- **Output**: Read

---

**CRUD** → data를 다루는 데 핵심적인 작업

파일 내의 정보(ex. 작성자, 작성일시, 작성자 정보 등)를 분류하여 보고 싶을 때 단순 검색 기능을 이용할 경우 원치않는 데이터가 검색(노이즈 발생)될 수 있음

스프레드시트를 이용하면 ID, title, description, created, author, profile 등을 한꺼번에 정리정돈하여 저장 → **filter, sort** 등의 기능을 이용해서 노이즈 없이 원하는 대로 분류하여 확인할 수 있음

스프레드시트는 DB로 가는 관문, DB는 스프레드시트에 비해 프로그래밍 언어를 이용해 데이터를 가공할 수 있고 CRUD 과정을 자동화할 수 있다는 장점이 있음

---

어떤 DB를 선택하고 공부해야 하는가?

- 속한 조직이나 동료가 사용하는 DB
- 통계를 기반으로 선택

![Database Engine Ranking 2023](week_1%20568e8e47f9e5487b802d10a3e61987b4/Untitled.png)

Database Engine Ranking 2023

![Database Engines Trend Graph 2023](week_1%20568e8e47f9e5487b802d10a3e61987b4/Untitled%201.png)

Database Engines Trend Graph 2023

관계형 데이터베이스의 순위가 전반적으로 높게 포진, 하나의 DB를 사용할 수 있게 되면 다른 관계형 DB를 습득하기 쉬워짐

### DB의 종류 예시

- Oracle → 시장의 절대 강자 but 라이선스 및 컨설팅 비용이 비쌈
- MySQL → 오픈소스, 무료, 데이터의 질보다 양이 중요할 때 사용 가능
- MongoDB → Document store, 다양하고 많은 DB가 폭발적으로 증가할 때 관계형 DB는 거기에 잘 맞지 않는 DB에 억압으로 작용할 수 있다(?)

---

---

## Database 2 - MySQL

정보의 폭발적 증가로 파일 만으로 데이터를 관리하기 힘들어졌을 때 이를 극복하기 위한 시도로 등장한 **관계형 데이터베이스** → 데이터를 표의 형태로 정리 정돈, 정렬 검색 등의 기능을 빠르고 편리하고 안전하게 사용 가능(MySQL, Oracle, SQL Server, PostgreSQL, DB2, Access 등)

**MySQL**은 무료 오픈소스 DB 시스템으로 관계형 DB에 필요한 대부분의 기능을 가지고 있음. 웹의 등장과 함께 무료라는 장점을 통해 폭발적으로 성장

---

MySQL은 스프레드시트와 같이 데이터를 표의 형태로 표현하지만 **컴퓨터 언어를 통해 기능을 구현**할 수 있다는 점이 스프레드시트와 다름

---

```bash
# cmd로 mysql 실행

Microsoft Windows [Version 10.0.22621.1105]
(c) Microsoft Corporation. All rights reserved.

C:\Program Files\MySQL\MySQL Server 8.0\bin>mysql -uroot -p
Enter password: ****
Welcome to the MySQL monitor.  Commands end with ; or \g.
Your MySQL connection id is 21
Server version: 8.0.32 MySQL Community Server - GPL

Copyright (c) 2000, 2023, Oracle and/or its affiliates.

Oracle is a registered trademark of Oracle Corporation and/or its
affiliates. Other names may be trademarks of their respective
owners.

Type 'help;' or '\h' for help. Type '\c' to clear the current input statement.

mysql>
```

---

### MySQL의 구조

최종적으로 데이터를 저장하는 곳은 **table**. 연관된 table이 여러개 그룹핑된 것은 **schema**(DB). 이러한 데이터베이스가 모여있는 곳이 **database server**.

---

### DB의 효용

- 보안: 자체적인 보안 체계를 가지고 있어 안전하게 데이터를 저장 가능
- 권한: DB에 여러 사람이 차등적인 권한을 가지 CRUD를 할 수 있음

---

### DB 접근

```sql
# 서버 접속
mysql -u"사용자 이름" -p
Enter password: "비밀번호"

# 스키마
CREATE DATABASE "DB이름"; // DB 생성
DROP DATABASE "DB이름"; // DB 삭제
SHOW DATABASES; // DB 조회
+--------------------+
| Database           |
+--------------------+
| information_schema |
| mydatabase         |
| mysql              |
| performance_schema |
| sakila             |
| sys                |
| world              |
+--------------------+
7 rows in set (0.00 sec)
```

---

**SQL(Structured Query Language)**: 관계형 DB에서 표를 작성(구조화)하고 데이터를 요청하는 언어

SQL은 관계형 DB에 속하는 제품들이 데이터 서버를 제어할 때 공통으로 사용하는 표준화된 언어.

table에서 행은 **row, record(개별 데이터)**, 열은 **column(데이터의 구조)**

---

### 테이블 생성(CREATE)

DB에서 테이블 생성시, 컬럼별로 입력 데이터를 강제함으로써 관리를 용이하게 할 수 있도록 

```sql
mysql> USE mydatabase;
Database changed
mysql> CREATE TABLE topic(
    ->   id INT(11) NOT NULL AUTO_INCREMENT, // id는 INT 자료형으로 11자까지, 값을 꼭 가지며 자동으로 다른 값이 채워짐
    ->   title VARCHAR(100) NOT NULL,
    ->   description TEXT NULL,
    ->   created DATETIME NOT NULL,
    ->   author VARCHAR(30) NULL,
    ->   profile VARCHAR(100) NULL,
    ->   PRIMARY KEY(id)); // id가 가장 중요한 primary key
Query OK, 0 rows affected, 1 warning (0.01 sec)
```

---

### 데이터 추가(INSERT)

```sql
mysql> SHOW TABLES;
+----------------------+
| Tables_in_mydatabase |
+----------------------+
| topic                |
+----------------------+
1 row in set (0.01 sec)

mysql> DESC topic;
+-------------+--------------+------+-----+---------+----------------+
| Field       | Type         | Null | Key | Default | Extra          |
+-------------+--------------+------+-----+---------+----------------+
| id          | int          | NO   | PRI | NULL    | auto_increment |
| title       | varchar(100) | NO   |     | NULL    |                |
| description | text         | YES  |     | NULL    |                |
| created     | datetime     | NO   |     | NULL    |                |
| author      | varchar(30)  | YES  |     | NULL    |                |
| profile     | varchar(100) | YES  |     | NULL    |                |
+-------------+--------------+------+-----+---------+----------------+
6 rows in set (0.00 sec)

mysql> INSERT INTO topic (title, description, created, author, profile) VALUES('MySQL', 'MySQL is ...', NOW(), 'nochang', 'developer');
Query OK, 1 row affected (0.01 sec)

mysql> SELECT * FROM topic;
+----+-------+--------------+---------------------+---------+-----------+
| id | title | description  | created             | author  | profile   |
+----+-------+--------------+---------------------+---------+-----------+
|  1 | MySQL | MySQL is ... | 2023-01-29 17:32:21 | nochang | developer |
+----+-------+--------------+---------------------+---------+-----------+
1 row in set (0.00 sec)
```

---

### 데이터 보기(SELECT)

```sql
mysql> SELECT * FROM topic;
+----+------------+------------------+---------------------+-----------+----------------+
| id | title      | description      | created             | author    | profile        |
+----+------------+------------------+---------------------+-----------+----------------+
|  1 | MySQL      | MySQL is ...     | 2023-01-29 17:32:21 | nochang   | developer      |
|  2 | MongoDB    | MongoDB is...    | 2023-01-29 17:34:40 | nochang   | developer      |
|  3 | SQL Server | SQL Server is... | 2023-01-29 17:37:42 | hyeongmin | data scientist |
|  4 | PostgreSQL | PostgreSQL is... | 2023-01-29 17:38:10 | yongjun   | developer      |
|  5 | ORACLE     | ORACLE is...     | 2023-01-29 17:38:57 | youngjae  | data engineer  |
+----+------------+------------------+---------------------+-----------+----------------+
5 rows in set (0.00 sec)

mysql> SELECT id, title, created, author FROM topic;
+----+------------+---------------------+-----------+
| id | title      | created             | author    |
+----+------------+---------------------+-----------+
|  1 | MySQL      | 2023-01-29 17:32:21 | nochang   |
|  2 | MongoDB    | 2023-01-29 17:34:40 | nochang   |
|  3 | SQL Server | 2023-01-29 17:37:42 | hyeongmin |
|  4 | PostgreSQL | 2023-01-29 17:38:10 | yongjun   |
|  5 | ORACLE     | 2023-01-29 17:38:57 | youngjae  |
+----+------------+---------------------+-----------+
5 rows in set (0.00 sec)

mysql> SELECT id, title, created, author FROM topic where author='nochang';
+----+---------+---------------------+---------+
| id | title   | created             | author  |
+----+---------+---------------------+---------+
|  1 | MySQL   | 2023-01-29 17:32:21 | nochang |
|  2 | MongoDB | 2023-01-29 17:34:40 | nochang |
+----+---------+---------------------+---------+
2 rows in set (0.00 sec)

mysql> SELECT id, title, created, author FROM topic ORDER BY id DESC;
+----+------------+---------------------+-----------+
| id | title      | created             | author    |
+----+------------+---------------------+-----------+
|  5 | ORACLE     | 2023-01-29 17:38:57 | youngjae  |
|  4 | PostgreSQL | 2023-01-29 17:38:10 | yongjun   |
|  3 | SQL Server | 2023-01-29 17:37:42 | hyeongmin |
|  2 | MongoDB    | 2023-01-29 17:34:40 | nochang   |
|  1 | MySQL      | 2023-01-29 17:32:21 | nochang   |
+----+------------+---------------------+-----------+
5 rows in set (0.00 sec)

mysql> SELECT id, title, created, author FROM topic LIMIT 2;
+----+---------+---------------------+---------+
| id | title   | created             | author  |
+----+---------+---------------------+---------+
|  1 | MySQL   | 2023-01-29 17:32:21 | nochang |
|  2 | MongoDB | 2023-01-29 17:34:40 | nochang |
+----+---------+---------------------+---------+
2 rows in set (0.00 sec)
```

---

### 데이터 수정(UPDATE)

```sql
mysql> UPDATE topic SET description='Oracle is ...', title='Oracle' WHERE id=2;
Query OK, 1 row affected (0.01 sec)
Rows matched: 1  Changed: 1  Warnings: 0

mysql> SELECT * FROM topic;
+----+------------+------------------+---------------------+-----------+----------------+
| id | title      | description      | created             | author    | profile        |
+----+------------+------------------+---------------------+-----------+----------------+
|  1 | MySQL      | MySQL is ...     | 2023-01-29 17:32:21 | nochang   | developer      |
|  2 | Oracle     | Oracle is ...    | 2023-01-29 17:34:40 | nochang   | developer      |
|  3 | SQL Server | SQL Server is... | 2023-01-29 17:37:42 | hyeongmin | data scientist |
|  4 | PostgreSQL | PostgreSQL is... | 2023-01-29 17:38:10 | yongjun   | developer      |
|  5 | ORACLE     | ORACLE is...     | 2023-01-29 17:38:57 | youngjae  | data engineer  |
+----+------------+------------------+---------------------+-----------+----------------+
5 rows in set (0.00 sec)
```

WHERE이 매우 중요

---

### 데이터 삭제(DELETE)

```sql
mysql> SELECT * FROM topic;
+----+------------+------------------+---------------------+-----------+----------------+
| id | title      | description      | created             | author    | profile        |
+----+------------+------------------+---------------------+-----------+----------------+
|  1 | MySQL      | MySQL is ...     | 2023-01-29 17:32:21 | nochang   | developer      |
|  2 | Oracle     | Oracle is ...    | 2023-01-29 17:34:40 | nochang   | developer      |
|  3 | SQL Server | SQL Server is... | 2023-01-29 17:37:42 | hyeongmin | data scientist |
|  4 | PostgreSQL | PostgreSQL is... | 2023-01-29 17:38:10 | yongjun   | developer      |
|  5 | ORACLE     | ORACLE is...     | 2023-01-29 17:38:57 | youngjae  | data engineer  |
+----+------------+------------------+---------------------+-----------+----------------+
5 rows in set (0.00 sec)

mysql> DELETE FROM topic WHERE id=4;
Query OK, 1 row affected (0.01 sec)

mysql> SELECT * FROM topic;
+----+------------+------------------+---------------------+-----------+----------------+
| id | title      | description      | created             | author    | profile        |
+----+------------+------------------+---------------------+-----------+----------------+
|  1 | MySQL      | MySQL is ...     | 2023-01-29 17:32:21 | nochang   | developer      |
|  2 | Oracle     | Oracle is ...    | 2023-01-29 17:34:40 | nochang   | developer      |
|  3 | SQL Server | SQL Server is... | 2023-01-29 17:37:42 | hyeongmin | data scientist |
|  5 | ORACLE     | ORACLE is...     | 2023-01-29 17:38:57 | youngjae  | data engineer  |
+----+------------+------------------+---------------------+-----------+----------------+
4 rows in set (0.00 sec)
```

---

### 관계형 DB의 필요성

 중복되는 데이터에 대한 수정 등 복잡하고 어려운 절차에 있어 어떤 DB가 다른 DB를 참조하는 식으로 구성할 시 데이터 유지, 관리, 보수가 용이해짐

---

### 테이블 결합(JOIN)

```sql
mysql> SELECT * FROM author;
+----+---------+-----------+
| id | name    | profile   |
+----+---------+-----------+
|  1 | nochang | developer |
+----+---------+-----------+
1 row in set (0.00 sec)

mysql> INSERT INTO topic(id, title, description, created, author_id) VALUES(1, 'MySQL', 'MySQL is...', NOW(), 1);
Query OK, 1 row affected (0.01 sec)

mysql> SELECT * FROM topic;
+----+-------+-------------+---------------------+-----------+
| id | title | description | created             | author_id |
+----+-------+-------------+---------------------+-----------+
|  1 | MySQL | MySQL is... | 2023-01-29 18:33:16 |         1 |
+----+-------+-------------+---------------------+-----------+
1 row in set (0.00 sec)

mysql> SELECT * FROM topic LEFT JOIN author ON topic.author_id = author.id;
+----+-------+-------------+---------------------+-----------+------+---------+-----------+
| id | title | description | created             | author_id | id   | name    | profile   |
+----+-------+-------------+---------------------+-----------+------+---------+-----------+
|  1 | MySQL | MySQL is... | 2023-01-29 18:33:16 |         1 |    1 | nochang | developer |
+----+-------+-------------+---------------------+-----------+------+---------+-----------+
1 row in set (0.00 sec)

mysql> SELECT topic.id, title, description, created, name, profile FROM topic LEFT JOIN author ON topic.author_id = author.id;
+----+-------+-------------+---------------------+---------+-----------+
| id | title | description | created             | name    | profile   |
+----+-------+-------------+---------------------+---------+-----------+
|  1 | MySQL | MySQL is... | 2023-01-29 18:33:16 | nochang | developer |
+----+-------+-------------+---------------------+---------+-----------+
1 row in set (0.00 sec)

mysql> SELECT topic.id AS topic_id, title, description, created, name, profile FROM topic LEFT JOIN author ON topic.author_id = author.id;
+----------+-------+-------------+---------------------+---------+-----------+
| topic_id | title | description | created             | name    | profile   |
+----------+-------+-------------+---------------------+---------+-----------+
|        1 | MySQL | MySQL is... | 2023-01-29 18:33:16 | nochang | developer |
+----------+-------+-------------+---------------------+---------+-----------+
1 row in set (0.00 sec)
```

칼럼명이 겹칠 경우 해당 테이블명을 칼럼명 앞에 붙임, AS를 통해 칼럼명을 다르게 할 수도 있음

---

### 인터넷과 DB

인터넷은 한 대의 컴퓨터(클라이언트)가 데이터를 요청, 다른 컴퓨터(서버)는 이 요청에 대해 응답하는 구조

DB는 서버에 저장되어 있으며 이에 대한 가공은 클라이언트(MySQL)를 통해 가능

클라이언트는 CLI 상에서 사용하는 MySQL, GUI 상에서 사용하는 MySQL Workbench 등이 있음

---

### MySQL Workbench

GUI 방식을 통해 MySQL을 다룰 수 있음

다양한 동작 후에 Apply를 통해 SQL문을 적용시켜 DB를 관리할 수 있음

---

데이터가 많아질 수록 index가 중요해짐 → 정리된 데이터는 꺼낼 때 편함

정규화, 비정규화, 역정규화 등 기존에 존재하는 모델을 잘 활용해야 함

데이터를 안전하게 보관하는 것이 중요(mysqldump, binary log 등)

클라우드 서비스를 통해 DB를 관리할 수 있