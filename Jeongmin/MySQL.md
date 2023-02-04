### 접속 경로(cmd창)
```sql
cd /usr/local/mysql/bin/
./mysql -uroot -p
```
- root : 관리자 - 모든 권한을 갖고 있음
- -p : 비밀번호 입력

### SQL이란?
- **S**tructured : 구조적
- **Q**uery : 질의
- **L**anguage : 언어

### SQL의 구조
- 스키마(shema): 표(table)들을 서로 그룹핑 할 때 사용하는 일종의 폴더
- Database server: 스키마들이 나눠진 것을 저장해 놓은 공간
- 데이터베이스 서버(DB server) > 스키마(shema = DB) > 표(table)
---
- **table**의 구조
    - x축 : **row**(행) -> 데이터 하나하나를 의미
    - y축 : **column**(열) -> 데이터의 타입(구조)을 의미

### 스키마(DB)의 사용 방법
- Database **생성** : CREATE DATABASE __ ;
- Database **삭제** : DROP DATABASE __ ;
- Database를 **보려면?** : SHOW DATABASES;  # DB 다 볼 수 있음
- Database에 **접속하려면?** : USE __ ;

### table 생성
```sql
CREATE TABLE topic(
    id INT(11) NOT NULL AUTO_INCREMENT,
    title VARCHAR(100) NOT NULL,
    description TEXT NULL,
    created DATETIME NOT NULL,
    author VARCHAR(30) NULL,
    profile VARCHAR(100) NULL,
    PRIMARY KEY(id));
```
- INT() : 내가 받을 숫자 허용 범위
    - BIGINT()를 하게 되면 저장공간을 많이 차지하게 됨 -> 자신이 수용하려고 하는 데이터의 최대값을 하면 됨
- NOT NULL : 값이 없는 것을 허용하지 않겠다는 것임 = 공백 허용 x
- AUTO_INCREMENT : 중복되지 않는 식별자 만들려면? -> id 등에서 사용이 유용
- VARCHAR() : 원하는 문자 수 만큼까지만 그 이후는 ㄴㄴ 잘림
- TEXT : 좀 더 길게 텍스트를 받기 위해
- DATETIME : 날짜와 시간까지 나오게끔 하는
- PRIMARY KEY() : 메인 키 설정
    - 식별자는 중복되면 안 됨 - DB야 id column은 각각의 값이 고유해야 해! -> PRIMARY KEY 지정

### INSERT
```sql
INSERT INTO topic (title, description, created, author, profile) VALUES('MongoDB', 'MongoDB is ...', NOW(), 'egoing', 'developer');
```
- SHOW DATABASES; -> DB확인
- USE opentutorials; -> opentutorials 사용
- SHOW TABLES; -> 어떤 table 있는지 보여주기
- DESC topic; -> topic 테이블을 볼 수 있음
---
```sql
SELECT * FROM topic;
```
- topic에 있는 것을 * (모두) select 한 것임

### SELECT
- SELECT id, title, author FROM topic; -> 원하는 col만 추출 가능
- SELECT - FROM - WHERE - ORDER BY - DESC LIMIT <- 순서
---
```sql
SELECT id, title, author FROM topic WHERE author='egoing' ORDER BY id DESC LIMIT 2;
```
- 코드 해석: topic에 있는 id, title, author 라는 col을 선택하고 author가 ‘egoing’인 것을 선택한다. id를 기준으로 오름차순(DESC) 정렬한다. 보여지는 data는 2개 정도로 제한
- SELECT를 잘 다루는 것이 중요함!

### UPDATE
```sql
UPDATE topic SET description = 'Oracle is ...', title = 'Oracle' WHERE id = 2;
```
- 코드 해석: topic에 있는 title은 Oracle이고 id 2에 있는 description =  ‘Oracle is …’으로 바꾼다.
- WHERE문을 빠뜨리면 재앙이 올 수 있다는 점 주의...

### DELETE
```sql
DELETE FROM topic WHERE id = 5;
```
- 코드 해석: topic에 있는 id 5를 삭제한다.
- 여기도 WHERE을 빠뜨리면 큰일이 벌어짐 -> 모든 행이 삭제되는 불상사 발생…

### 관계형 데이터베이스의 필요성
- 데이터가 많게 되면 수정하기가 힘듦
- 하나의 table로 보면 직관적으로 알 수 있으나, table을 쪼개서 참조 값만 적어 놓으면 별도의 표를 열어서 비교를 해야 함
- table을 나눈 후, JOIN을 통해 결합시킬 수 있음

### JOIN
```sql
SELECT * FROM topic LEFT JOIN author ON topic.author_id = author.id;
```
- 코드 해석: topic과 author를 LEFT JOIN해라. topic의 author_id랑 author.id를 기준으로 한다.
```sql
SELECT topic.id AS topic_id, title, description, created, name, profile  FROM topic LEFT JOIN author ON topic.author_id = author.id;
```
- 코드 해석: 원하는 것만 골라서 볼 수 있게 함. topic.id를 하는 이유는 어떤 id를 가르키는지 알기 위해서