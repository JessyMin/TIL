- SQL Server, T-SQL

### SELECT
- SELECT : What we want to retrieve from the table
- FROM : location of the source table
- Query formatting
    - 줄바꿈
- SELECT TOP(5) artist
- SELECT TOP(5) PERCENT artist
- SELECT DISTINCT region
- SELECT *


### Ordering and Filtering
- 순서
    - Sets have no internet order
    - ORDER BY로 순서를 부여할 수 있음
- 필터링
    - 특정 기준으로 추출
    - WHERE points >= 10
    - BETWEEN : Range로 필터링하기
        - WHERE total BETWEEN 20 AND 30 (inclusive)
        - NOT BETWEEN ~ AND ~
        - 줄바꿈 포맷
        ```
        WHERE
          affected_customers BETWEEN 50000
          AND 150000
        ```
    - 날짜
        - SQL Server : YYYY-MM-DD 포맷이 디폴트
        - WHERE  event_date = '2013-12-22';
- NULL
    - 값이 없음을 뜻함.
    - Unknown, missing
    - WHERE ~ IS NULL
    - WHERE ~ IS NOT NULL
