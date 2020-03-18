
### 조건문 (20.3.16)

```python
w = 'python'
w_iterator = iter(w)
next(w_iterator)

>> 'p'
```

- iterable 객체 : 반복 가능한 객체

- iterator 객체 : 값을 차례대로 꺼낼 수 있는 객체
- iter( ) : iterator 객체를 생성함
- next( ) : 함수를 사용할 때마다 첫번째, 두번째, 세번째 값이 출력됨.
- for 문을 사용하지 않고도 컬렉션을 순회할 수 있음.

참고 : https://wikidocs.net/16068


### 리스트 생성하기
```python
import pandas as pd

list_keys = ['a', 'b']
list_values = [['x', 'y'], [1, 2]]

list(zip(list_keys, list_values))

>> [('a', ['x', 'y']), ('b', [1, 2])]
```

- list(zip(list_1, list_2))


### 합집합 / 교집합
```python
a = {1, 2, 3}
b = {4, 5, 6}

a.union(b)

>> {1,2,3,4,5,6}
```
교집합
```python
a.intersection(b)
a & b

```
