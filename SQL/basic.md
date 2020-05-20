
### 날짜 변경

```SQL
SELECT reference,
       due_date AS new_date   
       due_date + interval '90 days' AS new_date   
FROM invoices
ORDER BY new_date, reference;

```


### 특정 텍스트 찾아내기
 - 대소문자 구분없이 찾기
```SQL
SELECT *
FROM favorite
WHERE title
WHERE title ILIKE '%stranger%things%'
ORDER BY user_id;
```

### 특정 텍스트 교체하기
- previous_text를 new_text로 교체
```SQL
SELECT REPLACE(name, 'previous_text', 'new_text')
AS name
FROM city;
```

### 특정 문자열로 시작하는 값 찾기
- Extract the names of cities that start with ('A', 'E', 'I', 'O', 'U').

```SQL
SELECT DISTINCT name
FROM CITY
WHERE LEFT(name,1) IN ('A', 'E', 'I', 'O', 'U')
ORDER BY name;
```


### 텍스트의 일부만 추출하기
```SQL
SELECT user_id,
       SUBSTRING(code,3,4) AS code_part
FROM accounts
ORDER BY user_id;

```


### 형 변환하기
```SQL
SELECT CAST(match_id AS text)
```

### 테이블에 열 추가하기
```SQL
INSERT INTO  white_wine
    SELECT style, type, country, price
    FROM wine
    WHERE type = 'sparkling'
```

### 날짜 변경하기
```SQL
SELECT reference,
       due_date + interval '90 days' AS new_date
FROM invoices;
```
