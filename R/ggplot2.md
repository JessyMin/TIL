### 여러 데이터프레임으로 차트를 겹쳐 그릴 때

```r
ggplot(NULL, aes(year, count)) +
        geom_line(data = filter(df_summary, gender=='F')) +
        geom_line(data = g, aes(col=name))
```

이 때 `data =` 로 정의해주지 않으면 아래 에러가 발생한다.

ggplot2 doesn't know how to deal with data of class uneval

참고 : <a href="https://stackoverflow.com/questions/9109156/ggplot-combining-two-plots-from-different-data-frames"> ggplot combining two plots from different data frames </a>
