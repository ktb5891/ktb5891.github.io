---
layout: post
toc: true
title: "정보 처리 기사 실기 준비(단답형)"
categories: study
tags: [Sujebi,Daily Quiz,정처기]
author:
  - Kwak Tae Beom
---

# 정보 처리 기사 실기 Daily 문제

## 1. 요구사항 확인

#### 115. 아래는 소프트웨어 아키텍처 4+1 관점(View)에 대한 설명이다. 괄호 (  ) 안에 들어갈 용어를 쓰시오.

![115.png](https://github.com/ktb5891/ktb5891.github.io/blob/main/img/EIP/115.png?raw=true){: width="800"}

> ① `논리 뷰(Logical View)`

> ② `배포 뷰(= 배치 뷰)(Deployment View)`


## 2. 화면 설계

#### 123. 아래는 사용자 인터페이스에 대한 설명이다. 괄호 (  ) 안에 들어갈 용어를 쓰시오.

![123.png](https://github.com/ktb5891/ktb5891.github.io/blob/main/img/EIP/123.png?raw=true){: width="800"}

> ① `NUI(NATURAL USER INTERFACE)`

> ② `유연성 (FLEXIBILITY)`


## 3. 데이터 입출력 구현

#### 110. 아래는 논리적 데이터 모델링 종류에 대한 설명이다. 괄호 (  ) 안에 들어갈 용어를 쓰시오.

![110.png](https://github.com/ktb5891/ktb5891.github.io/blob/main/img/EIP/110.png?raw=true){: width="800"}

> ① `관계 데이터`

> ② `네트워크 데이터`


## 4. 통합 구현

#### 121. 아래는 주요 연계 기술에 대한 설명이다. 괄호 (  ) 안에 들어갈 용어를 쓰시오.

![121.png](https://github.com/ktb5891/ktb5891.github.io/blob/main/img/EIP/121.png?raw=true){: width="800"}

> ① `API(Application Programming Interface)`

> ② `소켓(Socket)`


## 5. 인터페이스 구현

#### 99. 아래는 데이터 통신을 사용하여 인터페이스를 구현하는 방법이다. 괄호 (  ) 안에 들어갈 용어를 쓰시오.

![99.png](https://github.com/ktb5891/ktb5891.github.io/blob/main/img/EIP/99.png?raw=true){: width="800"}

> ① `JSON(Javascript Object Notation)`

> ② `AJAX(Asynchronous Java Script and XML)`


## 6. 프로그래밍 활용

#### 다음은 C언어 코드이다. 출력 결과를 쓰시오.

```C
#include <stdio.h>
void main(){
    char *str = "ABCDE";
    int i;
    for (i=4; i>0; i--)
        print("%d", *(str+i));
}
```

> A. `69686766`

> > str 변수는 ABCDE라는 값을 가리킵니다.

> > i=4부터 i>=0을 만족할 때까지 i를 1씩 감소시키면서 반복하는데, i가 4일 때 *(str+4)는 str 변수에 4번째 값을 가리키므로 E인데 %d(10진수)로 출력해야 하므로 아스키 코드 값인 69가 출력 됩니다.

> > i가 3일 때 *(str+3)은 str 변수에 3번째 값을 가리키므로 D인데 %d(10진수)로 출력해야 하므로 아스키 코드 값인 68이 출력 됩니다.

> > i가 2일 때 *(str+2)는 str 변수에 2번째 값을 가리키므로 C인데 %d(10진수)로 출력해야 하므로 아스키 코드 값인 67이 출력 됩니다.

> > i가 1일 때 *(str+1)은 str 변수에 1번째 값을 가리키므로 B인데 %d(10진수)로 출력해야 하므로 아스키 코드 값인 66이 출력 됩니다.


> > 참고로 A는 65이기 때문에(필기 때도 나왔으므로 암기해주시는게 좋습니다.) B는 1을 더한 66, C는 B에서 1을 더한 67, ... 이렇게 됩니다. 추가로 a는 97입니다.


## 7. SQL 응용

#### 80. 다음은 고객 테이블이다. 나이가 40살 이상이면서 60살 이하이고, 성별이 남자인 사람의 이름을 출력하는 쿼리를 작성하시오.(단, between 구문을 사용해야 한다.)

![80.png](https://github.com/ktb5891/ktb5891.github.io/blob/main/img/EIP/80.png?raw=true){: width="800"}

> A. 
```SQL
SELECT 이름 FROM 고객 
    WHERE 나이 BETWEEN 40 AND 60
    AND 성별 = "남"
```


## 8. 서버 프로그램 구현

#### 120. 아래는 공통 모듈 구현에 대한 설명이다. 괄호 (  ) 안에 들어갈 용어를 쓰시오.

![120.png](https://github.com/ktb5891/ktb5891.github.io/blob/main/img/EIP/120.png?raw=true){: width="800"}

> ① `독립성`

> ​​​​​​② `자료`

> ③ `기능적`


## 9. 소프트웨어 개발 보안 구축

#### 116. A 기업은 ISMS-P 심사에 따른 정보 보안 문제점을 통보받고, 아래와 같이 분야별 정보보안 개선 대책을 수립중이다. 아래 괄호 (  ) 안에 들어갈 용어를 쓰시오.

![116.png](https://github.com/ktb5891/ktb5891.github.io/blob/main/img/EIP/116.png?raw=true){: width="800"}

> ① `강제적 접근 통제(MAC; Mandatory Access Control)`

> ② `AES(Advanced Encryption Standard)`

> ③ `네트워크 접근 제어(NAC; Network Access Control)`


## 10. 애플리케이션 테스트 관리

#### 113. 다음은 조직에서 개발하고 있는 시스템에 대한 테스트 요구사항 중 일부이다. 아래의 요구사항에 따라 수행해야 하는 테스트를 보기에서 기호로 쓰시오.

![113.png](https://github.com/ktb5891/ktb5891.github.io/blob/main/img/EIP/113.png?raw=true){: width="800"}

> Req-01 : 프로젝트 개발 초기에 수행해야 하고, 검토 자료를 회의 전에 배포해서 사전 검토한 후 짧은 시간 동안 회의를 진행하는 형태로 리뷰를 통해 문제 식별, 대안 조사, 개선 활동, 학습 기회를 제공해야 하는 비형식적인 테스트를 수행해야 함 -> ① b

> Req-02 : 단위 시스템 개발 시에 수행해야 하고, (각 분기의) 결정 포인트 내의 각 개별 조건식이 적어도 한 번은 참과 거짓의 결과가 되도록 테스트를 수행해야 함 -> ② e

> Req-03 : 요구사항의 논리와 발생조건을 테이블 형태로 나열하여, 조건과 행위를 모두 조합하여 테스트를 수행해야 함 -> ③ j


## 11. 응용 SW 기초 기술 활용

#### 122. 운영체제가 필요로 하는 파일에 대한 정보를 갖고 있는 제어 블록이며, 보통 보조기억장치 내에 저장되어 있다가 해당 파일이 개방(Open)될 때 주 기억장치로 이동되는 제어 블록은 무엇인가?

> A. `파일 디스크립터(File Descriptor)`


## 12. 제품 소프트웨어 패키징

#### 95. 다음이 설명하는 용어를 쓰시오.

![95.png](https://github.com/ktb5891/ktb5891.github.io/blob/main/img/EIP/95.png?raw=true){: width="800"}

> A. `제품 소프트웨어 사용자 메뉴얼`