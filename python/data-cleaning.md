
### 형변환하기

```python
tips.smoking = tips.smoking.astype('category')
print(tips.info())

```

- object 타입의 데이터를 category 타입으로 변환하면 메모리도 감소함
- 결과 확인 : `tips.info()`, `tips.dtypes`
- numpy는 ''를 사용하지 않고, pandas는 ''를 사용
