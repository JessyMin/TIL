### ROLLUP( )

집계 보고서에서 소계, 합계를 구할 때 쓴다.

```sql




```



ROLLUP에는 ORDER BY를 붙여쓸 수 없다.
서브쿼리로 감싸주거나 WITH문을 사용한 뒤, 최종적으로 ORDER BY를 걸어야 한다.

```sql
# 1번 Dept.에 한하여 각 aisle별
# 제품 수를 카운트
WITH tmp AS (
  SELECT
    aisle_id,
    COUNT(product_id) AS count
  FROM
    products
  WHERE
    department_id = 1
  GROUP BY
    aisle_id WITH ROLLUP
)
SELECT *
FROM
  tmp
ORDER BY
  aisle_id IS NULL, count DESC;

```
이 때, 소계 값이 맨 밑에 위치하게 하려면 IS NULL 조건을 활용한다. NULL인 row가 가장 나중에 위치하게 된다.

```sql
WITH tmp AS (
  SELECT
     department_id
   , aisle_id
   , COUNT(product_id) AS count
  FROM
    products
  GROUP BY
    department_id, aisle_id WITH ROLLUP
)
SELECT
    p.department_id
  , d.department
  , p.aisle_id
  , a.aisle
  , p.count
FROM
  tmp p
LEFT JOIN
  departments d
  ON d.department_id  = p.department_id
LEFT JOIN
  aisles a
  ON a.aisle_id = p.aisle_id
ORDER BY
    p.department_id
  , p.aisle_id IS NULL
  , count DESC
;
```
