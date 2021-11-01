---
layout: post
toc: true
title: "NCSoft Blade & Soul2 Analysis"
categories: project
tags: [NCSoft, python, jupyter notebook, machine learning]
author:
  - Kwak Tae Beom
---
# Blade & Soul 2 Analysis Project

## 서론

### 게임선택

현재 NCSOFT에서 가장 관심있는 게임으로 올해 8월말에 출시한 Blade & Soul 2로 보인다. 매우 큰 기대를 안고 출시하였으나 갤럭시 게이머 수 기준 8월 28일의 유저 수는 2.36만명을 돌파 후 10월 5일 3289명으로 점점 줄어드는 유저 수가 어떤 이유로 줄어드는지 그리고 해당 문제점을 개선하여 유저를 돌아오게 할 방법을 파악하기로 하였다.

### 분석 프로세스

우선 문제점 파악을 위해 VOC를 토대로 파악하기로 하였다. Blade & Soul 2 공식 홈페이지 커뮤니티 자유게시판을 웹 크롤링하여 제목과 날짜, 조회 수를 모아 데이터를 확인하였다. WordCloud를 통해 직관적으로 어떤 단어들이 많이 언급되었는지 확인하였다. 그 후 단어 언급의 횟수를 카운트하여 일별로 나눈 시계열 그래프를 그려 가장 많은 관심을 가지는 단어들의 추세를 확인하였다. 이와 같은 EDA(Exploratory Data Analysis: 탐색적 데이터 분석) 과정을 거치며 웹 크롤링으로 수집된 데이터를 다양한 각도에서 관찰 및 이해를 하여 유저의 불만을 확인하고 잠재적인 문제를 찾아낼 수 있기에 EDA로 진행하였다. EDA 진행 후 위와 같은 과정으로 도출된 주제가 맞는지 확인하기위해 LDA(Latent Dirichlet Allocation: 잠재 디리클레 할당)를 이용하여 토픽 모델링을 진행하였다.

## 데이터 수집

### 수집 방법 (Crawling)

이번 분석을 진행하기 위해서 고객의 소리 즉 VOC를 수집해야 하는데 마침 Blade & Soul 2 공식 홈페이지 커뮤니티 자유게시판이 활발하게 운영되고 유저들 역시 많이 이용하고 있는 현황을 확인하였다. 그래서 Python의 BeautifulSoup, selenium라이브러리 등을 이용하여 웹 크롤링을 진행하였다.

```python
from bs4 import BeautifulSoup as bs
from selenium import webdriver
import time
import re
import pandas as pd
```

> 크롤링은 출시일인 21년 8월 26일부터 10월 7일까지 진행하였으며, 크롤링으로 게시글 제목, 업로드 일자, 조회수를 pandas를 이용해 DataFrame으로 저장 후 board.csv라는 파일을 생성하였다. Date변수를 크롤링 중 ‘5분전, 1시간전’ 과 같은 형식은 데이터 처리에 불편함을 주어서 다른 날짜의 형식과 같도록 21.10.07 의 형식으로 변환하였다.

### 데이터 확인

데이터의 이해를 돕기 위해 변수간의 관계 및 유형을 파악하여 분석 방향을 설정하였다.

```Tables
변수 명               | 변수 유형             | 변수 설명             
--------------------- | --------------------- | --------------------- 
Title                 | String                | 게시글 제목     
Date                  | Datetime              | 게시 날짜 
View                  | Numeric               | 조회 수 

```

문자열로 이루어진 Title 변수를 konlpy 라이브러리를 이용하여 어간을 추출하여 단어의 빈도 수를 하는 Wordcloud로 시각화가 가능하다. 또한, 추출한 단어들과 날짜를 연결시켜 어떤 시점에 단어들이 많이 언급되었는지 확인할 수 있는 시계열 그래프로 확인이 가능하다.


```python
board.describe()
```

> 평균과 중앙값이 각각 279, 196을 가지고 있어 게시판이 활발하게 활동하고 있는 것을 확인하였다.

```python
board.isna().sum()
```

> 만약 결측치가 생긴다면 제거 혹은 대체 후 분석을 진행해야 하기때문에 반드시 확인이 필요하다.

## 데이터 분석

### WordCloud

Wordcloud로 표현하기 위해서는 어간 추출의 과정이 필요한데 이를 위해서 konlpy, wordcloud 라이브러리를 사용하였다.

```python
from konlpy.tag import Okt
from collections import Counter
from wordcloud import WordCloud, STOPWORDS
```

> Okt와 Counter를 이용하여 전체 title의 어간을 추출하여 빈도수를 확인하였을 때 ('이벤트', 441), ('블소', 407), ('버그', 402), ('친구', 377), ('게임', 296), ('초대', 278)의 순으로 유저들의 관심도는 ‘이벤트’가 가장 높을 것이라 볼 수 있다.

![wordcloud](https://github.com/ktb5891/ktb5891.github.io/blob/main/img/nc_problem/wordcloud.png?raw=true)

> 워드클라우드의 결과로 보았을 때, 이벤트, 친구, 초대가 연관이 있어 ‘친구 초대 이벤트’가 있었을 것으로 예상할 수 있다. 또한, 다른 단어 중 버그가 눈에 띄는데 출시일이 몇일 지나지 않은 시점에서 나타난 버그현상이 있었을 것을 예상할 수 있다.

### 시계열 분석

워드클라우드의 결과가 믿을만한 결과인지 확인하고 어떠한 단어들이 연관되어 있는지 확인하기 위한 방법으로 시계열 분석을 선택하였다.

![10keyword_timeline](https://github.com/ktb5891/ktb5891.github.io/blob/main/img/nc_problem/10keyword_timeline.png?raw=true)

> 위의 그래프에서 급격한 변화가 보이는 이벤트, 친구, 초대, 영기, 버그의 시계열 그래프를 따로 그려 확인해보기로 하였다.

#### `이벤트` 시계열 그래프
![event_timeline.png](https://github.com/ktb5891/ktb5891.github.io/blob/main/img/nc_problem/event_timeline.png?raw=true)

#### `친구` 시계열 그래프
![friend_timeline.png](https://github.com/ktb5891/ktb5891.github.io/blob/main/img/nc_problem/friend_timeline.png?raw=true)

#### `초대` 시계열 그래프
![invite_timeline.png](https://github.com/ktb5891/ktb5891.github.io/blob/main/img/nc_problem/invite_timeline.png?raw=true)

> 위의 세 그래프를 보았을 때, 같은 시점에서 급격한 상승을 보이는 것을 확인할 수 있다. 이를 통해 세개의 단어는 연관되어 있다는 것을 알 수 있었으며, 이벤트로 인해 유저들의 관심도 증가한 것을 볼 수 있다.

#### `영기` 시계열 그래프
![youngki_timeline.png](https://github.com/ktb5891/ktb5891.github.io/blob/main/img/nc_problem/youngki_timeline.png?raw=true)

#### `버그` 시계열 그래프
![bug_timeline.png](https://github.com/ktb5891/ktb5891.github.io/blob/main/img/nc_problem/bug_timeline.png?raw=true)

> 위의 두 그래프는 게임운영에 이슈가 되는 부분이라고 생각한다. 버그는 출시 후 초반에 잠깐 언급되며 점점 줄어드는 추세를 가지고 있지만 영기는 처음 언급 횟수가 다른 단어에 비해 매우 높고 이후에는 놀라울 정도로 언급을 하지 않는다.

##### 이를 통해서 문제가 있었던 영기라는 시스템이 있었지만 현재로써 해결한 것으로 볼 수 있다. 하지만 버그의 언급이 줄어들고 있지만 계속된 언급을 보여 유저들이 문제점으로 삼을 수 있다.


### LDA (Latent Dirichlet Allocation)

LDA는 보통 토픽 모델링에서 주로 사용되는 알고리즘이다. 검색 엔진, 고객 민원 시스템 등과 같이 문서의 주제를 알아내는 일에 사용되기에 현재 Blade & Soul 2 유저들의 주된 생각은 어떠 한지를 다시한번 확인하기 위하여 LDA 알고리즘을 수행시켜 보았다.

```python
from sklearn.feature_extraction.text import TfidfVectorizer
from sklearn.decomposition import LatentDirichletAllocation
```

![LDA_result](https://github.com/ktb5891/ktb5891.github.io/blob/main/img/nc_problem/LDA_result.png?raw=true)

> 위의 LDA결과는 기존의 예상과는 다르게 버그, 영기, 블소, 게임, 쿠폰, 거래소와 같은 순으로 중요도가 매겨졌으며 이벤트, 친구, 초대의 단어는 다른 단어들에 비해 크게 중요하지 않은 것으로 확인되었다. 여기서 중요하게 생각해야 할 점이 버그와 영기가 매우 높은 수치를 나타내어 이 두 단어에 유저들이 민감하게 생각한다고 확인된다.

## 결론 및 제언

현재 Blade & Soul 2라는 게임이 하락세를 보이고 있는 것은 현재 NCSOFT가 직면한 기업적인 문제도 크게 작용할 수 있지만, 이번 분석에서도 볼 수 있듯이 유저들의 관심사는 게임 내의 영기 시스템 개편 요구와 게임 내의 버그 발생에 대한 관심이 가장 높았다. NCSOFT 대표 김택진 대표는 `블레이드앤소울2를 통해 잃어버렸던 게임 본연의 재미, 이야기와 모험이 가득한 세상, 그런 것을 만들어보고 싶었다는 말도 했다. 이를 통해 초창기에 느꼈던 게임 본연의 재미, 그 재미를 다시 찾아내고 싶었다는 게 김 대표의 생각이었다.` 라고 말하였는데 수익구조와 게임의 완성도를 확인하고 잃어버렸던 게임 본연의 재미를 블레이드앤소울2에서 찾기란 힘든 시점이다. 하지만 아직 유저들은 이벤트와 쿠폰과 같은 작은 보상에도 관심을 가지고 게임을 플레이 중에 있다. 그렇기 때문에 BM의 가장 기초적인 고객 확보를 위해서라도 수익구조를 개편해야하며 버그나 편의성 업데이트를 계속해서 시행하는 것이 NC와 블레이드앤소울2를 다시 상승세로 복귀시키는 방법이 될 것이라 생각한다.