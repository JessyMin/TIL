

#### 1) ggplot 등 package에 포함된 데이터셋

`diamonds`, `mtcars`, `iris` 등이 있다.

<br>

#### 2) Local 데이터 올리기

```r
Server.R

# loading local data file
data <- read.csv("./Data/sample.csv")

```
* 파일을 data 폴더 안에 넣고 경로를 지정해줘야 함.

#### 3) 웹서버에 있는 데이터셋 이용
```r
data <- load(url)
```


### 테이블

* DT package 사용.

* DT::renderDataTable --> renderDT
* DT::dataTableOutput --> DTOutput
* 참고 : https://blog.rstudio.com/2018/03/29/dt-0-4/


* DT::

### 기타
* req(input$n) : 인풋값이 없어도 UI에 에러메시지를 띄우지 않음.


### 텍스트 출력
```r
output$yearText <- renderText({
        sprintf('USA baby names in %s', input$year)
    })
```

하지만 paste0을 많이 쓴다.
```r
# DataCamp 예제
output$correlation <- renderText({
  r <- round(cor(movies[, input$x], movies[, input$y], use="pairwise"), 3)
  paste0("Correlation = ", r, ". Note: If the relationship between the two variables is not linear, the correlation coefficient will not be meaningful.")
})
}
```


### 지정한 컬럼값만 나오게 하기

```r
output$table1 <- renderDT({
    DT::datatable(
        selectedData()[, input$show_vars, drop = FALSE], rownames=FALSE
    )
})
```
