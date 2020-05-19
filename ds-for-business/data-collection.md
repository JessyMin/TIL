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
