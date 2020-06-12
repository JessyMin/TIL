### Supervised Machine Learning
- 머신러닝 : 데이터에 기반한 예측 Predictions
- Supervised Machine Learning : label과 feature가 있는 데이터
  - Label : 예측하려는 값
  - Feature : label을 예측하는 데이터
- 예시
  - 추천 시스템
  - 이메일 주제 optimization
  - churn prediction : 구독 중지 또는 지속
- 과정 : Data >> Trained Model >> Prediction (subscribe or churn)
- Model evaluation
    - Training set >> Test set


### Unsupervised Machine Learning : Clustering
- 정의
    - 머신러닝 알고리즘의 set
        - Unsupervised 머신러닝에 해당
    - Unlabeled dataset을 카테고리로 나눈다
        - 데이터에 Feature만 있음
        - 레이블 없음
    - 데이터셋에 대해 잘 몰라도 할 수 있음
- Use case
    - 고객 세그먼테이션
    - 이미지 분류
    - Anomaly detection
- Steps
    - Select features : 여행객 특성들
    - Select number of clusters
    - Use clusters to solve business problems


### Special topics in Machine Learning
- Time series forecasting
    - Time이 중요한 feature
        - 주간/월간/연간
    - Seasonality 이슈
        - 주간 : 금요일의 시청률 저하
        - 월간 : 결제일에 소비액 증가
        - 연간 : 겨울에 아이스크림 매출 하락
- NLP : Natural Language Processing
    - 텍스트 데이터셋을 사용
        - 고객 리뷰, 트윗, 의료기록, 이메일 제목 등
    - 활용
        - 센티먼트 분류
        - 클러스터링
    - Word counts로 변환
        - 부정어 문제
        - 동의어 문제 : single feature로 묶어야 함
    - Word embeddings
        - 유사어끼리 묶어 feature로 만듬
        - 수학적 의미를 가진 feature
