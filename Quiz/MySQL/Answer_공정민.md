## Week1 Quiz_jeongmin
### 1. 데이터베이스에서 가장 중요한 것은?
CRUD

### 2. 스키마(DB)의 사용 방법 4가지
- hint. 생성, 삭제, 보기, 접속
Database **생성** : CREATE DATABASE __ ;
Database **삭제** : DROP DATABASE __ ;
Database를 **보려면?** : SHOW DATABASES;  # DB 다 볼 수 있음
Database에 **접속하려면?** : USE __ ;


### 3. 다음의 코드를 해석하시오.
```sql
SELECT id, name, major, score FROM student WHERE name = 'jeongmin' ORDER BY id;
```

student에 있는 id, name, major, score 라는 col을 선택하고 name이 'jeongmin'인 것을 선택한다. id를 기준으로 정렬한다. 


- 순서
FROM WHERE GROUP BY HAVING ORDER BY