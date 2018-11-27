# Numpy

- 정의 What
  - Numpy = Numeric Python
- 필요한 이유 Why
  - list 자료형은 서로 연산할 수 없다.
  - 따라서 numpy 패키지 등장
- 사용법 How
  - list의 대체재는 array
- 사용 효과 What if
  - Easy & Fast

사례
```python
height = [1.7, 1.5, 1.6]
weight = [56.5, 49.6, 50.2]

weight / height ** 2
# 에러 발생함. list끼리 연산 불가

```

* numpy array로 변환
```python
import numpy as np
np_height = np.array(height)
np_weight = np.array(weight)
bmi = np_weight / np_height ** 2

```
