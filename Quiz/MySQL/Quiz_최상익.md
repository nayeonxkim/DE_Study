1번 아래와 같은 내용의 데이터베이스에서 id 2의 title ORACLE을 Oracle로 변경시키는 SQL 문의 빈칸을 완성시켜라 (UPDATE, SET, WHERE )

| id  | title      | description   | created  | author | profile        |
| --- | ---------- | ------------- | -------- | ------ | -------------- |
| 1   | MySQL      | MySQL is      | 23-01-01 | egoing | developer      |
| 2   | ORACLE     | ORACLE is     | 23-01-02 | egoing | developer      |
| 3   | SQL Server | SQL Server is | 23-01-03 | mike   | data scientist |
| 4   | PostgreSQL | PostgreSQL is | 23-01-04 | alice  | data engineer  |
| 5   | MongoDB    | MongoDB is    | 23-01-05 | egoing | developer      |

{           } topic {      } title='Oracle' {          } id=2;

    

    

    

2번  아래와 같은 SQL문에서  20 byte로 문자열의 크기를 지정하는 {A}와 반드시 데이터를 입력해야 함을 지정해주는 {B}를 알맞게 골라라 ( 2,3)

CREATE TABLE topic(author {       A      }{       B        });

1)LIMIT 2
2)VARCHAR(20)

3)NOT NULL
4)AUTO_INCREMENT

    

    

    

3번 토픽 테이블의 id를 저자가 egoing인 데이터를 id 기준으로 내림차순하여 2개만 보는 SQL문으로 알맞은 것은? 3

1)SELECT id FROM topic WHERE author = 'egoing' LIMIT 2 ORDER BY id DESC ;

2)SELECT id FROM topic ORDER BY id DESC WHERE author = 'egoing'  LIMIT 2;

3)SELECT id FROM topic WHERE author = 'egoing' ORDER BY id DESC LIMIT 2;
