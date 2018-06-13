### bq_helper 라이브러리

#### 1. 개요
* BigQuery 데이터를 쉽게 조회, pandas 데이터프레임으로 변환해서 다룰 수 있도록 Kaggle에서 만든 python 라이브러리

<br>

* Kaggle Kernel 내에서만 사용 가능. back단에서 돌아가는 작업을 Kaggle 시스템이 담당하고 있기 때문.

<br>

#### 2. 사용법
먼저 pandas 라이브러리가 필요하다.
```Python
import pandas
import bq_helper
```

아래와 같이 import해도 된다.
```Python
import pandas
from bq_helper import BigQueryHelper
```

<br>

다음으로, 연결하고자 하는 DB에 접속해서 object를 생성한다.

```python
us_name = bq_helper.BigQueryHelper(active_project="bigquery-public-data",
                                   dataset_name="usa_names")
us_name = BigQueryHelper("bigquery-public-data", "usa_names")
```
이렇게 `us_name`이라는 object를 생성했다.
<br>




#### 3. 주요 함수
