1번

{UPDATE} topic {SET} title='Oracle' {WHERE} id=2;

 UPDATE 테이블명 SET 칼럼명='수정할 내용' WHERE 조건;   

    

2번 

CREATE TABLE topic(author { 2 }{ 3 });

1)LIMIT 2 : select에서 데이터를 2개 행만 보게 제약하는 조건
2)VARCHAR(20) : 데이터 타입 문자열로 20바이트까지로 지정

3)NOT NULL         : 반드시 데이터를 입력해야 함을 지정  
4)AUTO_INCREMENT : 자료가 늘어날 때 +1 해주는 sql문

    

3번  3

3)SELECT id FROM topic WHERE author = 'egoing' ORDER BY id DESC LIMIT 2

3, 조건을 설정해주는 WHERE, 정렬해주는 ORDER, 데이터를 제약해주는 LIMIT 순으로 온다


