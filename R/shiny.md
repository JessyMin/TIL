

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
