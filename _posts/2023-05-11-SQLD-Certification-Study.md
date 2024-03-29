---
layout: post
toc: true
title: "SQLD(SQL개발자) 필기 준비"
categories: study
tags: [SQL Server Management Service,Oracle,SQLD]
author:
  - Kwak Tae Beom
---
<!-- <span style="color:red">  </span> -->
## SQL 개발자 핵심 150제 정리

### 1 ~ 10번

#### 1. 정보시스템을 모델링할 때의 세 가지 관점

1. 데이터에 대한 관점

2. 프로세스에 대한 관점

3. 데이터와 프로세스가 서로 연관성이 표현되는 상관 관점

#### 2. 데이터 모델링의 세 가지 중요개념

1. 업무가 관여하는 <span style="color:red"> 어떤 것(Things) </span>

2. 업무가 관여하는 어떤 것의 <span style="color:red"> 성격(Attributes) </span>

3. 업무가 관여하는 어떤 것의 <span style="color:red"> 관계(Relationships) </span>

#### 3. 발생시점에 따라 구분할 수 있는 `엔터티`의 유형
{: .prompt-warning }

* **`엔터티`**의 개념 : 업무에서 관리해야하는 데이터의 집합을 의미, 저장되고 관리되어야 하는 데이터
{: .prompt-warning }
(개념, 사건, 장소 등의 명사)

1. 기본/핵심 엔터티(Basic Entity)
- 키 엔터티라고 함
- 다른 엔터티로 부터 영향을 안받음. 즉, 독립적으로 생성되는 엔터티   
ex) 고객, 상품, 부서 등

2. 중심 엔터티(Main Entity)

3. 행위 엔터티(Active Entity)

#### 4. `속성 유형` : 보다 세분화된 개념적 모델링을 위해서 속성의 유형을 3가지로 세분화
{: .prompt-warning }

1. 기초 속성(Basic Attribute)
  - 업무로부터 추출된 일반적인 속성
  - 데이터 요구 분석 명세서에 포함되어 있으며, 현업에서 제공해야 속성이 유지가능
  - ex) 상품명, 가격, 주문수량 등

2. 설계 속성(Design Attribute)
  - 원래 존재하지는 않지만 필요에 따라 설계자가 추가한 속성
  - 데이터 요구 분석 명세서에 포함되어 있지는 않지만, 설계를 진행하면서 새로 생성
  - 대부분의 코드 속성이나 일련번호처럼 식별자 역할을 하도록 추가된 속성
  - ex) 주문번호, 예약번호, 상품코드 등

3. 파생 속성(Derived Attribute)
  - 추출/유도 속성이라고도 칭하며, 기본 속성으로부터 계산 등의 가공 처리를 통해서 생성된 속성
  - 저장 속성(Stored Attribute)의 영향을 받으므로, 저장 속성의 값이 변경되면 함께 변경
  - 저장 속성(Stored Attribute)
    : 파생속성을 결정하기위해 사용되는 속성
  - 중복의 의미가 있으므로 대게 개념적 모델링 단계에서 식별하지 않음   
    (반드시 필요한 경우라면 별도로 정리해서 구현 단계에서 참조)
  - ex) 나이(생년월일 속성에서 유도됨), 근무기간(입사일 속성에서 유도됨) 등

#### 5. 

> An example showing the `tip` type prompt.
{: .prompt-tip }