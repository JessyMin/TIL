
### 정의
- Inner 쿼리의 WHERE 절에 있는 조건이, Outer 쿼리의 컬럼을 참조함.
- Row별로 Iterate함. Looping 메커니즘을 사용. (Nested Query 먼저 처리한 뒤 Outer 쿼리 순차적으로 처리하는게 아니라)
- Alias를 반드시 사용해야.

### 예시
```SQL
SELECT *
FROM customers AS c
WHERE 4 > -- Select all customers with a minimum rating smaller than 4
	(SELECT MIN(rating)
	FROM renting AS r
	WHERE r.customer_id = c.customer_id);
```

위 쿼리를 만약 Correlated query를 사용하지 않으면, 아래와 같이 길어진다.
```SQL
SELECT *
FROM customers AS c
WHERE c.customer_id IN
    (SELECT r.customer_id
    FROM renting AS r
    GROUP BY r.customer_id
    HAVING MIN(r.rating) < 4);

```

### 더 찾아볼 내용/궁금
- 어떨 때 쓰는 거지? 실행속도의 문제인가, 쿼리 가독성의 문제인가?
- 근데 이렇게 하면 MIN(r.rating)은 어떻게 SELECT해야 하는지?
