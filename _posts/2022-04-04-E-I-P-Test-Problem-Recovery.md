---
title: "정보 처리 기사 실기 기출 복원"
author: Kwak Tae Beom
date: 2022-04-04 13:12:00 +0900
categories: [study]
tags: [정처기]
---

# 20년 3회 정보처리기사 실기 복원 문제

#### 1. 리팩토링의 목적에 대한 설명을 작성하시오.

> A. `소프트웨어를 보다 이해하기 쉽고, 수정하기 쉽도록 만드는 것이다.`   
`결과의 변경없이 코드의 구조를 재조정하는 것으로 가독성을 높이고, 유지보수를 쉽게하기 위한 목적`   
`코드의 외부 행위는 바꾸지 않고 내부 구조를 개선시켜 소프트웨어를 보다 이해하기 쉽고, 수정하기 쉽도록 만드는 것`

***

#### 2. 다음의 출력 결과를 쓰시오.

```C
#include <stdio.h>

void main(){
    int c = 0;
    int i = 0;

    while(i<10){
        i++;
        c *= i;
    }
    printf("%d", c);
}
```

> A. `0`

***

#### 3. 다음 학생 테이블에서 이름이 민수인 튜플을 삭제하도록 결과를 작성하시오.

> A.`DELETE FROM 학생 WHERE 이름 = '민수'`

***

#### 4. TCP/IP에서 신뢰성없는 IP를 대신하여 송신측으로 네트워크의 IP 상태 및 에러 메시지를 전달해주는 프로토콜을 (     )이라 한다.

> A. `ICMP(Internet Control Message Protocol)`

***

#### 5. 다음의 출력 결과를 쓰시오.

```JAVA
public class Test{
    public static void main(String []args){
        int i = 0;
        int sum = 0;
        while (i<10){
            i++;
            if(i%2 == 1)
                continue;
            sum += i;
        }
    System.out.print(sum);
    }
}
```

> A. `30`

***

#### 6. 심리학자 톰 마릴은 컴퓨터가 메시지를 전달하고 메시지가 제대로 도착했는지 확인하며 도착하지 않았을 경우 메시지를 재전송하는 일련의 방법을 '기술적 은어'를 뜻하는 (     )이라는 용어로 정의하였다. (     )안에 들어갈 용어는?

> A. `프로토콜(Protocol)`

***

#### 7. EAI 구축 유형 Message Bus, Hybrid를 제외한 나머지 두 가지 유형은?

> A. `Point To Point`, `Hub & Spoke`

***

#### 8. 다음의 출력 결과를 쓰시오.

```Java
abstract class Vehicle{
    String name;
    abstract public String getName(String val);
    
    public String getName(){
        return "Vehicle name : " + name;
    }
}

class Car extends Vehicle{
    public Car(String val){
        name = super.name = val;
    }
    public String getName(String val){
        return "Car name : " + val;
    }
    public String getName(byte val[]){
        return "Car name : " + val;
    }
}

public class Test{
    public static void main(String[] args){
        Vehicle obj = new Car("Spark");
        System.out.printf(obj.getName());
    }
}
```

> A. `Vehicle name : Spark`

***

#### 9. 다음의 출력 결과를 쓰시오.

```C
int r1(){
    return 4;
}

int r10(){
    return (30+r1());
}

int r100(){
    return (200+r10());
}

int main(){
    printf("%d",r100());
    return 0;
}
```

> A.`234`

***

#### 10. 동치 분할 테스트, 경계값 분석 테스트 등 내부 구조를 보지않고 하는 테스트는 무엇인가?

> A. `블랙박스 테스트`

***

#### 11. 형상 통제에 대한 설명을 작성하시오.

> A. `형상 항목의 버전 관릴르 위해서 변경 여부와 변경 활동을 통제하는 활동-산출물의 변경사항을 버전별로 관리하여 목표 시스템의 품질 향상을 지원하는 활동`

***

#### 12. 분기 커버리지 과정 순서 배열 (* 참고용 - 화이트박스 테스트 그림 표시가 되어있었음)

***

#### 13. 대표적인 내부 라우팅 프로토콜로 대규모 네트워크에 적합하고 링크 상태 라우팅 프로토콜로도 불리는 라우팅 프로토콜은 무엇인가?

> A. `OSPF(Open Shortest Path First)`

***

#### 14. C++에서 생성자의 의미에 대한 설명을 작성하시오.

> A. `객체 생성 시 초기화 작업을 위한 함수로써, 객체를 생성할 때 반드시 호출되고 제일 먼저 실행된다. - new 연산자를 통해서 객체를 생성할 때 반드시 호출이 되고 제일 먼저 실행되는 일종의 메소드`

***

#### 15. 데이터베이스에서 스키마에 대한 설명을 작성하시오.

> A. `데이터베이스의 구조와 제약조건에 대한 명세를 기술한 것. - 데이터베이스의 구조와 제약조건에 관한 전반적인 명세를 기술한 메타데이터의 집합이다.`

***

#### 16. 헝가리안 표기법에 대한 설명을 작성하시오.

> A. `컴퓨터 프로그래밍에서 변수 및 함수의 이름 인자 앞에 데이터 타입을 명시하는 코딩 규칙`

***

#### 17. 다음 성적 테이블에서 평균이 90이상인 과목 이름과 최소점수, 최대점수의 결과를 작성하시오.

|과목코드|과목이름|학점|점수|
|-----|-----|---|---|
|01|데이터과학|3|92|
|02|데이터마이닝|3|88|
|03|실험설계|3|83|
|01|데이터과학|3|90|


|과목이름|최소점수|최대점수|
|-----|-----|-----|
|데이터과학|83|92|

- 대,소문자 구분 X   
- WHERE 구문은 사용 X   
- GROUP BY, HAVING 구문은 필수   
- 별칭 (AS)을 사용   
- 속성명에 작은 따옴표('')를 사용

> A. 
```SQL
SELECT '과목이름', MIN('점수') AS 최소점수, MAX('점수') AS 최대점수
FROM 성적
GROUP BY '과목이름' HAVING AVERAGE('점수') >= 90
```

***

#### 18. UI 설계 원칙 중 직관성에 대한 설명을 작성하시오.

> A. `누구나 쉽게 이해하고 사용할 수 있어야 한다.`

***

#### 19. 릴레이션 A, B가 있을 때 릴레이션 B 조건에 맞는 것들만 릴레이션 A에서 튜플을 분리해 프로젝션하는 관계대수의 기호를 쓰시오.

> A. `÷`

***

#### 20. 다음 속성을 주소라고 하고 크기는 20으로 제한한다. 학생 테이블에 컬럼을 추가하는 결과를 작성하시오.

- (  1  ) TABLE 학생 (  2  ) 주소 VARCHAR(20);

> 1. `ALTER`   
2. `ADD`

***