
### 형변환하기

```python
tips.smoking = tips.smoking.astype('category')
print(tips.info())

```

- object 타입의 데이터를 category 타입으로 변환하면 메모리도 감소함
- 결과 확인 : `tips.info()`, `tips.dtypes`
- numpy는 ''를 사용하지 않고, pandas는 ''를 사용


- Numeric으로 변환하기

```python
tips['tip'] = pd.to_numeric(tips['tip'], errors='coerce')
```
  - 에러값은 NaN으로 변환함


### 결측값 처리하기
 - 찾아내기 : `df.isnull()`

 - 다른 값으로 채우기 : `df.fillna('alternative_value')`
 - 다음의 비결측값으로 채우기 : `df.fillna(method = 'backfill')`
