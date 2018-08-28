* 분류 --> categorical variable 예측
* 회귀 --> continuous variable 예측

## Intro
* 머신러닝은 데이터를 Insight와 Action으로 바꿔준다.

##1. Supervised Learning in R : Classification
* 가장 일반적인 4개의 ML 알고리즘 소개


###1-1. K-Nearest Neighbors(kNN)
* 예시를 통해 배우는 방식, 지도학습을 공부할 때 시작점으로 좋음
* 실습 : 자율주행차의 도로 표지판 인식을 위한 분류기

* Nearest neighbor classifier를 train시키기
  * 비슷한 것끼리 분류한다.
  * 유사도 측정에 유클리디언 거리 이용

```r
#사용법
library(class)
red <- knn(training_data, testing_data, training_labels)

#사례
sign_types <- sign$sign_type
knn(train = signs[-1], test = next_sign, cl = sign_types)

#알아낸 사실
vector <- iris[,1]
df <- iris[1]

```

* 퍼포먼스 측정하기
``` r

# Create a confusion matrix of the actual versus predicted values
signs_actual <- test_signs[,1]
table(signs_pred, signs_actual)


# Compute the accuracy
mean(signs_pred == signs_actual)

```
- 벡터만으로 crosstable 그릴 수 있음

#### 'k'란 무엇인가?
* neighborhood를 결정할 때 참고하는 개수
  * category를 결정할 때 가까운 이웃을 몇 개까지 고려할 것인가?  
* 분류 정확도에 영향을 줌
  * k는 가급적 작으면 좋다.
    * can identify more subtle patterns
    * 하지만 노이즈의 impact가 커짐
  * "Bigger is not always better"
    k가 너무 크면 ignore some noisy points

* k 정하기
  * 제곱근 : observation 100개 --> k=10
  * 여러 번 테스트해서 성능 비교


* R의 class 패키지는 디폴트 k=1
  * 파라미터 변경 : This enlarges the collection of neighbors which will vote on the predicted class.
```r  
# Modify the above to set k = 7
k_7 <- knn(train = signs[-1], test = signs_test[-1], cl = signs[,1], k=7)
mean(k_7 == signs_actual)
```

####어떻게 vote한건지 살펴보기 : probability

* it can sometimes be useful to examine whether the voters were unanimous or widely separated.
*  knowing more about the voters' confidence

``` r

sign_pred <- knn(train = signs[-1], test = signs_test[-1], cl = signs[,1], k = 7, prob=TRUE)

# Get the "prob" attribute from the predicted classes
sign_prob <- attr(sign_pred, "prob")
head(sign_prob)

```

#### 데이터 준비 / 정규화하기
* numeric이어야 함
* kNN으로 분류하기 전에 데이터 rescale 필요
  * 거리 계산 시 극단값(extreme value)로 인한 영향을 최소화
  * 목표 : To ensure all data elements may contribute equal shares to distance.
  * min-max normalization 등 사용 

###1-2. Naive Bayes
* 통계학 분야의 원칙을 이용해 예측
* 베이지언 방법론 소개
* iPhone-like destination 제안 데이터


###1-3. Logistic Regression
* binary event를 예측하기 위해 numeric data에 curve를 피팅시킴
* 가장 많이 사용되는 ML 방법
* 펀드레이징 데이터 이용


###1-4. Classification Trees
* 의사결정에 flowchart처럼 생긴 구조를 이용
* 인간이 이해하기 쉽기 때문에, 투명성이 중요할 때 유 (대출승인  등)
* Lending Club 데이터셋 이용


##2. Supervised Learning in R : Regression

##3. Unsupervised Learning in R

##4. Machine Learning Toolbox
