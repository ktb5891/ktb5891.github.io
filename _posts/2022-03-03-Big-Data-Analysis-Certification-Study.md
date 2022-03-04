---
layout: post
toc: true
title: "빅데이터 분석 기사 실기 준비(단답형)"
categories: study
tags: [Sujebi,Daily Quiz,빅분기]
author:
  - Kwak Tae Beom
---

# 빅데이터 분석 기사 단답형 예시

## 1 ~ 10번


#### 1. `시계열 분석`에서는 주어진 `자료가 정상성을 만족`해야 한다. 비정상시계열을 정상시계열 자료로 바꾸기 위해, 평균이 일정하지 않은 경우 `현시점에서 이전 시점의 자료를 빼는 방법`을 무엇이라고 하는가?

> A.	`차분(difference)`

> > 평균이 일정하지 않은 비정상시계열은 차분으로 정상화하며, 분산이 일정하지 않은 비정상시계열은 변환(transformation)으로 정상화합니다.


#### 2. 기업의 `합리적인 의사결정을 방해하는 요소`로서 문제의 표현 방식에 따라 `동일한 사건이나 상황임에도 불구하고 개인의 판단이나 선택이 달라질 수 있는 현상`을 무엇이라고 하는가?

> A.	`프레이밍 효과(Framing Effect)`

> > 기업의 합리적인 의사결정을 방해하는 요소인 고정 관념, 프레이밍 효과 중에서 프레이밍 효과에 대한 내용입니다.


#### 3. `표본 추출 방법` 중 질적인 원소들로 구성된 모집단에서 `각 계층을 고루 대표할 수 있도록 표본을 추출하는 방법`으로 유사한 원소끼리 `몇 개의 층`으로 나누어 층에서 `랜덤 추출`하는 방법은 무엇인가?

> A.	`층화 추출법(Stratified Random Sampling)`

> > 표본 추출 기법 중 `층화 추출법`과 `군집 추출법`은 잘 알아두기.

> > > `군집 추출법(Cluster Sampling)` : 모집단을 `여러 군집으로 나누고`, 일부 군집의 `전체 또는 일부를 추출`하는 방식, 내부적으로는 이질적, 외부적으로는 동질적인 방법


#### 4. `군집 타당성 지표(Clustering Validity Index)` 중의 하나로 군집 내의 `데이터 응집도(cohesion)`와 `군집간 분리도(separation)`를 계산하며 계산된 결과는 -1에서 1사이의 값을 가지고, 군집 분석이 잘 된 경우 1에 가까운 값을 가지는 `지표`는 무엇인가?

> A.	`실루엣(Silhouette)`

> > 실루엣 지표는 -1과 1사이의 값을 가집니다. 군집 내의 데이터의 거리가 짧을수록, 군집간의 거리가 멀수록 값이 커지며, 1에 가까울수록 군집화가 잘 되어 있고, -1에 가까울수록 군집 결과가 타당하지 않은 것으로 해석합니다. 일반적으로 실루엣 지표가 0.5보다 크면 타당한 것으로 해석합니다.


#### 5. `의사결정나무의 형성 과정` 중 끝마디가 너무 많을 경우, 모형이 과대 적합(Over-fitting)되어 현실 문제에 적용할 수 있는 적절한 규칙이 나오지 않게 되는 문제가 발생한다. 따라서 분류된 `관측치의 비율` 또는 `MSE(Mean Squared Error)`등을 고려하여 적절한 수준의 (    )규칙을 제공해 주어야한다.

> A.	`가지치기`

> > 문제의 지문은 가지치기에 관련된 내용입니다. 가지치기와 정지 규칙의 개념은 혼돈되지 않게 학습해주세요.


#### 6. `인공신경망`에서 가중치 매개변수 기울기를 미분으로 계산하면 시간 소모가 크다. 이를 개선하여 `오차를 출력층에서 입력층으로 전달`하고, `연쇄법칙을 활용하여 역전파를 통해 가중치와 편향을 갱신`하는 것은 무엇인가?

> A.	`오차역전파(Back Propagation)`


#### 7. `코호넨`에 의해 제시된 `비지도 신경망`으로 `고차원의 데이터를 이해하기 쉬운 저차원의 뉴런으로 정렬하여 지도의 형태로 형상화`한 군집분석방법은 무엇인가?

> A.	`SOM(Self-Organizing Maps)`

> > 문제에 제시된 내용은 SOM에 대한 내용입니다. `코호넨 맵`이라고도 불립니다.


#### 8. 버섯을 구매한 고객이 치즈도 구매할 연관성에 대하여 분석할 때 `지지도`, `신뢰도`, `향상도`는 무엇인가?

![8.png](https://github.com/ktb5891/ktb5891.github.io/blob/main/img/BDAC/8.png?raw=true){: width="800"}

> A.  지지도 1/4(0.25), 신뢰도 3/4(0.75), 향상도 9/8(1.125)

> `지지도` = 300/1200 = 1/4 = 0.25

> `신뢰도 = 지지도 / P(A)` = (300/1200) / (400/1200) = 3/4 = 0.75

> `향상도 = 신뢰도 / P(B)` = { (300/1200) / (400/1200) }/ (800/1200) = (3/4) / (2/3) = 9/8 = 1.125


#### 9. 사용자가 다차원으로 이루어진 정보에 직접 접근하여 `대화식`으로 정보를 분석하고 `의사결정에 활용`하는 시스템은 무엇인가?

> A. `OLAP(Online Analytical Processing)`

> > 지문은 OLAP에 대한 내용입니다. SCM과 CRM도 같이 학습해주세요.

> > > `SCM(Supply Chain Management)` : 기업과 `외부 공급업체 또는 제휴업체와 통합된 정보시스템으로 연계`하여 `시간과 비용을 최적화` 시키기 위한 것으로, 자재구매, 생산/재고, 유통/판매, 고객데이터로 구성되는 정보시스템

> > > `CRM(Customer Relationship Management)` : 기업의 `내부 데이터`로써 `소비자들을 자신의 고객`으로 만들고, 이를 `장기간 유지`하고자 내부 정보를 분석하고 저장하는 데 사용하는 정보시스템


#### 10. `회귀모형의 계수`를 추정하는 방법으로 `잔차의 제곱합을 최소화`하는 계수를 찾는 방법을 무엇이라고 하는가?

> A. `최소제곱법 (Least Square Method)`

> > 최소제곱법은 `값을 정확하게 측정할 수 없는 경우`에 근사적으로 값을 구하는 방법으로 `회귀모형의 계수`를 추정할 때 사용합니다.


## 11 ~ 20번


#### 11. 아래와 같이 `오분류표`가 주어질 경우에 대한 `재현율(Recall)`을 구하는 공식을 쓰시오.

#### (답안 작성 예) ① + ② + ③

![11.png](https://github.com/ktb5891/ktb5891.github.io/blob/main/img/BDAC/11.png?raw=true){: width="800"}

> A. `①/(① + ③)`

> > 혼동행렬(오분류표)은 언제 출제가 되어도 이상하지 않은 문제입니다.

> > 재현율의 공식은 `TP /(TP + FN)` 입니다.

> > TP는 ①이고, FN은 ③이므로 ①/(① + ③)이 됩니다.

> > `F1-Score`의 공식도 잊지 말고 기억해 주세요.

> > > `F1-Score` = `2 x (Precision x Recall)/(Precision + Recall)`


#### 12. 다음은 인공신경망에서 무엇에 대한 설명인가?

> 인공신경망 학습에서 최적의 가중치 매개변수 값을 찾기 위한 지표로 이것을 사용한다.

> 인공신경망의 학습은 이것이 최소가 되도록 하기 위해 가중치와 편향을 찾는 것이다.

> 출력한 값과 실제 값과의 오차에 대한 함수이다.

> 이것으로 평균제곱오차 또는 교차엔트로피 오차를 활용한다.

> A. `손실함수(Loss Function)`

> > `손실함수`는 `인공신경망의 성능`을 나타내는 지표로 활용됩니다.

> > 인공신경망 학습에서는 손실함수의 값을 가능한 작게 하는 최적의 매개변수를 찾습니다.

> > (손실함수는 출력한 값과 실제 값과의 오차에 대한 함수이므로 값이 낮을수록 학습이 잘 된 것 입니다.)


#### 13. 텍스트 마이닝의 전처리 과정에서 어형이 변형된 단어로부터 접사등을 제거하고 그 단어의 원형 또는 어간을 분리해 내는 것을 무엇이라고 하는가?

> A. `스테밍(Stemming)`


#### 14. 다음은 앙상블 모형에서 무엇에 대한 설명인가?

> 원 데이터 집합으로부터 크기가 같은 표본을 여러번 단순 임의 복원추출하여 각 표본에 대해 `분류기(Classifier)`를 생성한 후 그 결과를 앙상블하는 기법이다.

> 반복추출 방법을 사용하므로 같은 데이터가 한 표본에 여러번 추출되거나 데이터가 추출되지 않을 수도 있다.

> A. `배깅(Bagging)`

> > 앙상블 모형중에서 데이터를 조정하는 가장 가장 대표적인 방법에는 `배깅(bagging)`과 `부스팅(boosting)`이 있습니다.

> > > `배깅` : 크기가 같은 표본을 여러번 단순 임의 복원추출하여 각 표본에 대해 `분류기(Classifier)`를 생성한 후 그 결과를 앙상블하는 기법

> > > `부스팅` : 배깅의 과정과 유사하나 부트스트랩 표본을 구성하는 `재표본(re-sampling)` 과정에서 각 자료에 동일한 확률을 부여하는 것이 아니라, 분류가 `잘못된 데이터에 더 큰 가중을 주어` 표본을 추출하는 기법입니다.


#### 15. R 언어에서 apriori 함수를 활용해 생성한 연관규칙을 확인할 수 있는 함수는 무엇인가?

> A. `inspect`

> > R언어에서 연관 규칙을 `apriori` 함수를 이용하여 생성 할 수 있습니다.

> > 이 때 생성한 `apriori` 함수의 결과는 `inspect` 함수를 이용하여 확인 가능합니다.

> > 출제기관의 다른 시험에서 출제가 된 유형이므로 참고 부탁드립니다.


#### 16. 실제로 `부정`인 범주 중에서 `부정`으로 올바르게 예측한 비율로 `TN/(TN+FP)`의 계산식을 갖는 혼동행렬 지표는 무엇인가?

> A. `특이도(Specificity)`

![16.png](https://github.com/ktb5891/ktb5891.github.io/blob/main/img/BDAC/16.png?raw=true){: width="800"}


#### 17. 다음은 회귀분석에서 어떤 문제에 대한 설명인가?

> -`독립변수들간에 높은 선형관계`가 존재할 때 발생하는 문제이다.

> -회귀분석에서 결정계수 값이 높아 회귀식의 설명력은 높지만, 각 독립변수의 `P-값(P-Value)이 커서 개별 인자들이 유의하지 않는 경우` 이 문제가 발생할 수 있다.

> -`분산팽창요인(Variance Inflation Factor, VIF)이 10을 넘는 경우` 발생하는 문제이다.

> -`상관관계가 높은 독립변수 중 하나 혹은 일부를 제거하여 이 문제를 해결`한다.

> -`주성분분석(PCA) 방법을 이용하여 설명력이 높은 변수를 선택하여 이 문제를 해결`한다.

> A. `다중공선성(Multicolinearity)`


#### 18. 군집 내의 `오차 제곱합(Error Sum of Square)에 기초`하여 군집을 수행하는 방법으로 군집의 병합으로 인한 `오차 제곱 합의 증가량이 최소가 되는 방향으로 군집을 형성`하는 군집 간 거리측정 방법은 무엇인가?

> A. `와드연결법(Ward Linkage Method)`

> > *최단연결법, 최장연결법, 중심연결법, 평균연결법, 와드연결법 개념 확인 필요


#### 19. `평균으로부터 t Standard Deviation 만큼 떨어져 있는 값들을 이상값(Outlier)으로 판단`하고 `t를 3`으로 하는 `이상값 검색 알고리즘`은 무엇인가?

> A. `ESD(Extreme Studentized Deviation)`

> > 평균으로부터 `3 Standard Deviation(표준 편차)`만큼 떨어져 있는 값들을 이상값으로 판단하는 알고리즘


#### 20. 연관성 분석에서 규칙이 우연에 의해 발생한 것인지를 판단하기 위해 연관 규칙 내 항목의 연관성 정도를 측정하는 척도는 무엇인가?

> A. `향상도(Lift)`

> > ##### 향상도는 우연에 의해 발생한 것인지를 판단하기 위해 연관 규칙 내 항목의 연관성 정도를 측정하는 척도입니다.


> > ##### 지지도 - 전체 거래 중 항목 A와 B를 동시에 포함하는 거래의 비율

> > A -> B 라고 하는 규칙이 전체 거래 중 차지하는 비율을 통해 해당 연관 규칙이 얼마나 의미가 있는 규칙인지를 확인하는 척도


> > ##### 신뢰도 - A 상품을 샀을 때 B 상품을 살 조건부 확률에 대한 척도

> > 상품 A를 구매했을 때 상품 B를 구매할 확률이 어느정도 되는지에 대한 척도


> > ##### 향상도 - A가 주어지지 않았을 때 B의 확률 대비 A가 주어졌을 때 B의 확률 증가 비율

> > 규칙이 우연히 일어날 경우를 대비해 얼마나 나은 효과를 보이는지에 대한 척도