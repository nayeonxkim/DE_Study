### 1. 다음 빈칸에 들어갈 알맞은 명령어를 고르시오

INSERT INTO Reservation(ID, Name, ReserveDate, RoomNum)    **(빈칸)**   (1, '홍길동', '2016-01-05', 2014);

1. VALUES

2. AS

3. FROM

4. INSERT

### 2. AUTO_INCREMENT 에 대해 설명하시오

```python
id 를 지정하고 이 옵셔을 지정하면 데이터를 추가할 때 마다 1씩 자동으로 증가한다
```

### 3. 다음 테이블과 구문을 보고 결과를 예상하시오

![](Quiz_이세울_assets/2023-02-01-19-53-19-image.png)

```python
SELECT id,title,author FROM topic WHERE aurthor='egoing' ORDER BY id;d
```

autor = "egoing" 에서 id , title, author 을 선택
