### 조인하기

```python
merge(tv_show, country, on='code', how='outer')
tv_show.join(country, how='outer'))

```

- 같은 컬럼명이 있을 때 지정해주기
```python
salesman.merge(customer, on='city')[['name_x','name_y','city']]
```


### Null값 확인하기
```python
missing_total_by_column = wine.isna().sum()
```
