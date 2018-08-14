

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


* 테이블 크기 줄이기
https://stackoverflow.com/questions/31921238/shrink-dtdatatableoutput-size


### 테이블에서 값 선택하기
reactive / observe click
https://stackoverflow.com/questions/39175099/reading-objects-from-shiny-output-object-not-allowed



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


# 삽질

### Plot 그리기
이 에러로 정말 오래 헤맸다.

  Reading objects from shinyoutput object not allowed.

  ```r  
  output$plot1 < renderPlot({
      d <- selectedData2()
      #d <- subset(data, name == input$name)
      p <- ggplot(data=d, aes(year, count)) + geom_line()
      print(p)
  })

  ```

  화살표에서 - 가 빠진 거였다.....


### Plot 그리기

틀린거

  output$plot1 <- renderPlot({
    ggplot(selectedData(), aes(year, count)) + geom_line()
})


맞는거
output$plot1 <- renderPlot({
    d <- selectedData2()
    ggplot(data=d, aes(year, count)) + geom_line()
})


# 인풋하기

### 테스트용 버튼
, actionButton("name2", "Jessica")


### 입력한 이름으로 그래프 그리기

```r
#Server.R

#입력한 이름으로 상세 테이블 추출
selectedName1 <- reactive({
    req(input$name)
    data <- subset(data, name == input$name & gender == input$gender)
})

#입력된 이름만 Plot 그리기
output$plot1 <- renderPlot({
    d <- selectedName1()
    y <- as.numeric(input$year)
    ggplot(data=d, aes(year, count)) + geom_line(col='steelblue') +
        theme_classic() +
        geom_vline(aes(xintercept = y), col='grey', alpha=0.6)
})

```

```r
#ui.R

#이름 텍스트 인풋받기
textInput(
    "name", h3("Type name :"),
    value = ""   
)

#Plot 출력
plotOutput("plot1")

```