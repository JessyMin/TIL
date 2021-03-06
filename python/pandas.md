### 데이터프레임 만들기
df = pd.DataFrame(columns=['category', 'title', 'favorite', 'price'])



### 파일 읽어들이기
- 엑셀 파일 읽어서 파싱하기
```python
import pandas as pd
import xlrd

xls = pd.ExcelFile(file_xlsx)
xls.parse()
```

- 특정 시트 읽어들이기
```python
import pandas as pd

xl = pd.read_excel(url, sheet_name = "Sheet1")
xl.head()
```

- 특정 URL에 접근해서 csv파일 다운받기
```python
import os.path
import urllib.request as ur

ur.urlretrieve(url, 'wine_quality.csv')

# Checking whether file was stored successfully
os.path.exists('wine_quality.csv')
```

- Numpy 오브젝트로 파일 읽어들이기
```python
import numpy as np

np.loadtxt("data.txt", delimiter="\t", dtype="int")
```

### 데이터 크기/내용 확인하기
```python
df.shape
df.head()
df.columns

```

### 데이터 타입 확인/변환하기
```python
# 타입 확인
df.dtypes

# 데이프레임 크기, 컬럼명, 데이터 타입 확인
df.info()

# 숫자형으로 타입 변환
df['column'] = pd.to_numeric(df['column'], errors='coerce')
df['column'] = df['column'].astype(int)


```

### 컬럼 삭제하기
```python
df = df.drop('col1')
df = df.drop(['col1', 'col2'])

```

### 특정 컬럼만 선택하기 (subset)
```python
df = df[['height', 'color']]

```

## 전처리

### Null값의 총 개수 확인하기
```python
missing_total_by_column = wine.isna().sum()
```

df.stars.transform(lambda x: x / 1000)

### 피벗 테이블
```python
df.pivot_table(values = 'stars', index = 'language', aggfunc = np.sum)
```


### 텍스트 다루기

- 값 교체하기
```python
data.str.replace('apple', 'orange')
```

- 특정 텍스트를 가지고 있는지 확인하기
```python
s.str.contains("d")
```


## 테이블 다루기

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

- `concat` 이용하기
  - axis는
```python
print(pd.concat([df1, df2], axis=0))
```





# Numpy

- 텍스트 파일 읽어들이기
```python
np.loadtxt("data.txt", delimiter="\t", dtype="int")
```
