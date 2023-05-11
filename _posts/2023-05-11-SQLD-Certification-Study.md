---
title: "SQL Development Study"
author: Kwak Tae Beom
date: 2023-05-11 17:12:00 +0900
categories: [study]
tags: [SQL Server Management Service,Oracle,SQLD]
---

# SQL 개발자 핵심 150제 정리

## 1 ~ 10번

#### 1. 정보시스템을 모델링할 때의 세 가지 관점

1. 데이터에 대한 관점

2. 프로세스에 대한 관점

3. 데이터와 프로세스가 서로 연관성이 표현되는 상관 관점

#### 2. 데이터 모델링의 세 가지 중요개념

1. 업무가 관여하는 어떤 것(Things)

2. 업무가 관여하는 어떤 것의 성격(Attributes)

3. 업무가 관여하는 어떤 것의 관계(Relationships)

#### 3. 발생시점에 따라 구분할 수 있는 `엔터티`의 유형

* `엔터티`의 개념 : 업무에서 관리해야하는 데이터의 집합을 의미, 저장되고 관리되어야 하는 데이터(개념, 사건, 장소 등의 명사)

1. 기본/핵심 엔터티(Basic Entity)
- 키 엔터티라고 함
- 다른 엔터티로 부터 영향을 안받음. 즉, 독립적으로 생성되는 엔터티

ex) 고객, 상품, 부서 등

2. 중심 엔터티(Main Entity)
- 기본 엔터티와 행위 엔터티 간의 

3. 행위 엔터티(Active Entity)

#### 