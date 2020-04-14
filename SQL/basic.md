
### 날짜 변경

```SQL
SELECT reference,
       due_date AS new_date   
       due_date + interval '90 days' AS new_date   
FROM invoices
ORDER BY new_date, reference;

```

### 특정 문자열로 시작하는 값 찾기
- Extract the names of cities that start with ('A', 'E', 'I', 'O', 'U').

```SQL
SELECT DISTINCT name
FROM CITY
WHERE LEFT(name,1) IN ('A', 'E', 'I', 'O', 'U')
ORDER BY name;
```
