
``` r

table(signs$sign_type)

```



#### 특정 컬럼의 값에 따라 다른 컬럼값에 차이가 있는지 살펴보기

``` r 
# Check r10's average red level by sign type
aggregate(r10 ~ sign_type, data = signs, mean)

```
