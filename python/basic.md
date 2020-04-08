
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


### range()
- 역순으로 감소시키려면 단위를 설정해줘야 함

```python
for x in range(10,0,-1):
	print(x)

>> 10
9
8
7
...
```


### 리스트 생성하기
```python
import pandas as pd

list_keys = ['a', 'b']
list_values = [['x', 'y'], [1, 2]]

list(zip(list_keys, list_values))

>> [('a', ['x', 'y']), ('b', [1, 2])]
```

- list(zip(list_1, list_2))


### 합집합 / 교집합 / 교집합 외의 부분
```python
a = {1, 2, 3}
b = {4, 5, 6}

a.union(b)

>> {1,2,3,4,5,6}
```

- 교집합
```python
a.intersection(b)
a & b

```
- 교집합 외의 부분 : `a.difference(b)`



### 여러 개의 인수를 받을 때, 키워드 인수를 받을 때
- args = arguments
- 몇 개가 입력될 지 모르는 경우. 여러 개의 인자를 받고자 할 때.
- 튜플 형태로 들어와서 출력됨

#### args : 여러 개의 인수를 받을 때

```python
def make_dict():
def make_dict(**kwargs):
    return kwargs

make_dict(a = 1, b = 2)

>> {'a': 1, 'b': 2}
```

#### kwargs : 키워드 인수를 받을 때
- kwargs : keyword arguments
- 딕셔너리 형태로 함수 내부로 전달됨

```python
def add_many(args):
def add_many(*args):
    s = 0
    for n in args:
        s += n
    print(s)

add_many(100, 50, 3)

>> 153

```
