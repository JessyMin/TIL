

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


### 테이블에 특정 값 선택되어 있게 하기

```r  
#조인 테이블
output$table1 <- renderDT({
    DT::datatable(
        joinedTable(),
        selection = list(mode = 'multiple', selected = 1)
    )
})

```

* 관련 링크 : https://rstudio.github.io/DT/shiny.html


### 세션에 관한 사실들

#### 1)

* 하나의 R 프로세스는 여러 개의 Shiny 세션을 서포트한다.


```r
server <- function(input, output, sesison){

}
```

* 이 함수는 각각의 세션마다 호출된다. 즉, 웹브라우저가 Shiny 애플리케이션을 가리킬 때마다 서버 함수가 호출된다.

* 따라서 이 함수 안의 내용은 매 세션마다 초기화된다.

#### 2) Objects visible across all sessions


#### 3) Global objects

`global.R`에서 정의된 오브젝트는 `app.R`에서 server 함수 바깥쪽에 정의된 것과 비슷하지만, 한가지 중요한 차이점이 있다. ui 오브젝트의 코드에게도 visible하다는 점이다. R 세션의 글로벌 환경에 로드되었기 때문이다. Shiny 앱의 모든 R 코드는 글로벌 환경 또는 그 자식에서 실행된다.

실질적으로는 `server`와 `ui` 사이에 변수를 공유해야 하는 경우는 많지 않다. `ui`의 코드가 일단 실행되면, Shiny 앱이 시작되고 HTML 파일을 생성하며, 이것은 캐쉬되고 연결되어 있는 각각의 웹브라우저로 보내진다. 이것은 공유되는 환경설정 옵션을 셋팅하는 데에 유용할 것이다.


* `global.R`에 관한 유용한 글
https://stevenmortimer.com/tips-for-making-professional-shiny-apps-with-r/
