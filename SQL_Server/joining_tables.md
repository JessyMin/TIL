### Joining tables
- Relational DB : multiple tables
- Primary Key
    - Uniquely identify each row in a table
    - 컬럼명 : Table name_id
- Foreign key
    - to B table :
    - Join 사용
- Join
    - Inner JOIN
        - Syntax : FROM table_A JOIN table_B ON table_B.foreign_key = table=A.primary_key
    - Outer JOIN


### LEFT JOIN & RIGHT JOIN
- 필요성
  - 예)고객이 A행동은 했지만 B행동은 안했다면?
  - NULL값이 있는 경우까지 포함
  - 모든 row를 매치하여 반환함
  - 매칭되지 않으면 NULL
- Left Join
  - return ALL rows in the first table, and any matching rows in the right table.


### UNION & UNION ALL
   - 조건
  	- Select the same number of columns in the same order
   	- Columns should have the same data types
  	- 컬럼명이 다르다면 Alias하기
  - UNION
      - 두 테이블은 결합해 한 테이블로 만들 때
      - Duplicate rows are excluded (합집합)
  - UNION ALL
      - Includes duplicate rows



### etc.
- WHERE album_id IN (213,214)
