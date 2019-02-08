DataCamp 수강 시작.

2개의 array를 x축, y축으로 plot을 그릴 수 있다.

```python
import matplotlib.pyplot as plt

plt.scatter(year, population)
plt.show()

```


### Stacked Barcharts 그리기
- 관련 링크 : https://pstblog.com/2016/10/04/stacked-charts

```python
import pandas as pd

# 데이터프레임 생성
data = [[2000, 2000, 2000, 2001, 2001, 2001, 2002, 2002, 2002],
        ['Jan', 'Feb', 'Mar', 'Jan', 'Feb', 'Mar', 'Jan', 'Feb', 'Mar'],
        [1, 2, 3, 4, 5, 6, 7, 8, 9]]

rows = zip(data[0], data[1], data[2])
headers = ['Year', 'Month', 'Value']
df = pd.DataFrame(list(rows), columns=headers)

# 테이블 피벗하기
pivot_df = df.pivot(index='Year', columns='Month', values='Value')
pivot_df = pivot_df[['Jan','Feb', 'Mar']].copy()

# Stacked Barchart 그리기
colors = ["#006D2C", "#31A354","#74C476"]

pivot_df.plot.bar(stacked=True, color=colors, legend='reverse', figsize=(10,7))
```
- pivot한 뒤에는 월별로 column순서를 재정렬했다.
- legend의 순서를 Bar segment와 일치시키기 위해 'reverse'해주었다.
