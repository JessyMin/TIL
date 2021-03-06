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



### A/B test
- 실험 : 웹사이트 변경, 신규 기능 추가, 이메일 제목 등
- 4단계
    1) Picking a metric to track : 지표 선정
    2)Calculating sample size : 샘플 사이즈 도출
        - Baseline metric에 따라 달라짐.
        - Baseline conversion이 높을수록, 유의한 차이에 도달하기 쉽고, 샘플 사이즈는 작아짐.
        - detectable difference : 테스트가 덜 민감할수록 샘플 사이즈가 작아짐 (The less sensitive our tests, the smaller the sample size we need.)
    3)Running the experiment : 실험 수행
        - 너무 짧거나 길게 수행하면 결과에 바이어스가 낄 수 있음.
    4) Checking for significance : 유의한 차이가 있는지 분석
        - “But how do we know that difference is meaningful?”
        - 통계적으로 유의한 차이가 있는지
