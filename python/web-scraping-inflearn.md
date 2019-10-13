- 강좌명 : 현존 최강 크롤링 기술: Scrapy와 Selenium 정복 (<a href="https://www.inflearn.com/course/Crawling-Scrapy-Selenium/dashboard">인프런</a>)


## 1. 브라우저를 제어해서 크롤링하기

#### Selenium

- 웹 테스팅하는 프레임워크
- 본인 브라우저에 맞는 웹드라이버를 설치해서 사용
- 스크롤다운, 페이지넘김 등 인터랙션을 통한 제어가 필요할 때 유용함

#### Phantom JS
- webdriver 쓰는 부분을 대체
  - 이하 소스 가져오고 파싱하는 작업은 완전히 동일
- 셀레니움보다 빠르기도 느리기도 함. 되기도 안되기도.
- 여러 가지 무기를 아는 차원에서 알아두는 것
- 최근에는 지원을 안해서 사용이 줄어드는 추세
  - 하지만 예전에 많이 썼었고 이전 코드에 존재
  - 크롤링을 하는 개발자라면 모르는 사람은 없음. 알아둬야

#### Headless Chrome  
- 옵션 설정
- 기타 옵션들
  - 윈도 사이즈
  - GPU 사용 안함
  - 클라이언트 쪽의 헤더 정보를 가짜로 입력, 크롤링 아닌 척 하기

#### 다음 뉴스기사 제목 가져오기

element를 선택하는 방법들

- 태그의 속성을 사용

```python
titles = driver.find_elements_by_css_selector("h3[itemprop='headline']")
```

- 선택자를 사용
  - 우클릭 -> Copy -> Copy Selector
```python
css = "div.bv-content-details-offset-off > div > div > div.bv-content-summary-body-text"
review_bodies = driver.find_elements_by_css_selector(css)
```

#### 트위터 사이트 로그인 하기
- 아이디, 패스워드 입력 필드를 속성으로 찾아낸다.
- 아이디 값을 입력한다.
```python
driver.get('http://www.twitter.com')
id_field = driver.find_element_by_name('session[username_or_email]')
id_field.clear()
id_field.send_keys('my_id@gmail.com')
```
- 패스워드 값을 입력한 뒤 엔터를 쳐서 로그인한다.
```python
pw_field = driver.find_element_by_name('session[password]')
pw_field.send_keys('my_password')
pw_field.send_keys(Keys.RETURN)

```


## 2. 동적 웹페이지 크롤링하기

## 3. XPATH : 데이터를 선택하는 또 다른 기법

## 4. Scrapy : 강력한 크롤링 기술

## 5. 현업 스타일 Scrapy 실전 활용(중급)
