
### Local 데이터 올리기

```r
Server.R

# loading local data file
data <- read.csv("./Data/sample.csv")

```
* 파일을 data 폴더 안에 넣고 경로를 지정해줘야 함.


### 기타
* req(input$n) : 인풋값이 없어도 UI에 에러메시지를 띄우지 않음.
