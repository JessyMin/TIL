### Aggregating : Grouping, strings, and counting things
- SUM, COUNT, MIN, MAX, AVG
- 텍스트 필드 다루기
- GROUP BY, HAVING


### Aggregating Data
- Summarize numeric values
- single column을 다룬다.
- Sum과 Count는 툴에 상관없이 데이터를 aggregate하는 기본
- SUM : total amount of a column value
    - Alias 사용해야 함 (T-SQL 특징인 듯)
- MAX : 최대값
- MIN : 최소값
- AVG : 평균


### Strings

- LEN( ) : 텍스트의 길이
- LEFT(column, n) : 해당 텍스트 추출
- RIGHT(column, n)
- 중간에서 추출해야 한다면
- SUBSTRING(url, 12, 5) : 시작점, 추출할 개수
- CHARINDEX (‘a', url) AS char_location : 특정 문자열의 위치를 출력함
- REPLACE(url, ‘a’, ‘b‘) :  문자열 교체
