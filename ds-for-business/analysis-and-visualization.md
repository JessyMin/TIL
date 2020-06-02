### Dashboards
- 대시보드 : set of metrics
- 업데이트 : real time, daily, weekly
- 그래프의 종류
    - Line chart(시계열, time-series) : tracking a value over time, historical context를 제공,
    - Stacked bar chart : tracking over time, compare different segments
    - Categorical Comparison : 서로 다른 그룹을 비교
- Highlighting a single number
    - 오늘 방문자 수 (어제보다 O% 증가)
- Displaying text
    -  고객 리뷰 등
- 만드는 방법
    - 스프레드시트 : 엑셀, 구글시트
    - BI Tools : Power BI, Tableau, Looker
    - Customized tools : R, Shiny, d3.js
- 대시보드를 요청할 때
    - 조건  
        - 여러 번 사용할 것이 확실할 때
        - 일간/월간 업데이트 필요할 때
        - 항상 요구사항이 동일할 때
    - 요구사항 :
        - Be specific
        - Specify your use case : 데이터분석가가 그래프 종류를 고를 때 참조


### Ad hoc analysis
- Ad hoc request의 특징
  - 일단위/주단위로 반복되지 않는 단일한 요구/질문
  - 다양한 조직에서 Analytics 팀에 요구
    - Product, Finance, Engineering, Marketing 등
- 요구 정의하기
  - Be specific : 요구하는 데이터가 명확해야 함
  - Include contexts : 데이터를 필요로 하는 목적, 용도 (도움되는 추가 데이터를 함께 제공 가능. can add helpful information)
  - Include a priority level and due date : 우선순위와 마감기한
- Managing ad hoc analysis team
  - 예측하기 어려움.  Scheduled work에 비해 (A/B 테스트, 대시보드 등)
  - 전략 : Ticketing system 사용 (Trello, JIRA, Asana)
