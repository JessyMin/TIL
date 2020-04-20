### 텍스트 다루기

- 값 교체하기
```python
data.str.replace('apple', 'orange')
```


### 조인하기

```python
pd.merge(df_1, df_2, on = 'repo')


merge(tv_show, country, on='code', how='outer')
tv_show.join(country, how='outer'))


```



- 같은 컬럼명이 있을 때 지정해주기
```python
salesman.merge(customer, on='city')[['name_x','name_y','city']]
```


### Null값의 총 개수 확인하기
```python
missing_total_by_column = wine.isna().sum()
```

df.stars.transform(lambda x: x / 1000)

### 피벗 테이블
```python
df.pivot_table(values = 'stars', index = 'language', aggfunc = np.sum)
```
