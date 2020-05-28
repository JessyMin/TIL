# Data Collection

### 데이터 소스
- Web events (ex. user_id, event_name, timestamp)
- Customer data
- Logistics data
- Financial transactions


### 개인정보
- PII : Personally Identifiable Information
- 이름, 위치(location), 이메일주소,
- 개인정보 보호를 위한 조치
  - 테이블을 분리 (Data pseudonymization)
    : Users table / events table
  - 익명화Anonymization해야 함(비식별화)
  - 접근권한 제한
  - 일정기간 경과 후 파기

### GDPR : General Data Protection Regulation
- EU 내의 모든 데이터에 적용됨
- 개인이 데이터를 컨트롤할 수 있게 하는 목적
- 보존기간, 비식별화 방법 등


## Solicited data

1. 목적
 - Create marketing collateral
 - De-risk decision making 의사결정의 리스크 감소
 - Monitor quality 제품/서비스 품질 모니터링

2. 유형
 - 서베이
 - 고객 리뷰
 - In-app questionnaires 인앱 설문조사
 - Focus groups (FGI, 좌담회)

3. 타입
 - Qualitative data 정성 데이터
  : 대화, 개방형 질문
  . 가설을 세울 때 좋음
 - Quantitative data 정량 데이터
  : 복수응답, rating scale
  . 객관화, 그래프 등으로 시각화하기 쉬움

4. NPS(Net Promoter Score)  - “How likely are you to recommend this product or website to a friend or colleague?”
 - 0~10점 척도

5. Revealed vs. stated preference
 - Stated preference : 가설, 주관적
 - Revealed preference : 행동, 구매

6. Best practice (Tips for designing questions)
 - Callibrate : 대상에 대한 관심/선호만 질문하지 말고, 여러 개를 질문해서 값을 비교할 것.
 - Actionable한 결과를 얻을 수 있는 질문을 할 것
   . 궁금한 것을 물어보는 게 아니라, 각 질문에 가설이 있어야 함.


### Collecting additional data
 - Intertnal data / External data

1) Data API
- API : Application Programming Interface
- 인터넷을 통해 3rd Party의 데이터를 요청

2)Public records 공공데이터
- 미국 : data.gov
- 유럽 : data.europa.eu

3)Mechanical Turk (AWS)
- 이미지 인식을 위한 딥러닝 하려면 training set 필요
  - Labeled image구하기 어렵고 시간과 노력이 ㅁ낳이 듬
- 고객 리뷰의 레이블링 (Positive/Negative/Neutral)
- Form으로부터 텍스트 추출
- 문장 내의 키워드에 하이라이팅 등
