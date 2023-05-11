---
title: "Job Opening Web Crawlling "
author: Kwak Tae Beom
date: 2021-12-22 14:31:00 +0900
categories: [project]
tags: [Maven Cloud Service, Python, Visual Studio]
---

# ---정보통신에서의 Web Crawlling 요청.

## Sa---in, Jabpl---- 공고를 크롤링 요청

> 지난 첫 Project 관련 회의를 진행하였는데 회의 진행 중 학부시절, 교육 시절 Python을 몇 번 사용해봤다는 이야기를 들으시고 저에게 크롤링을 요청하셨다.

> 사실 이미 작성된 코드가 존재하였는데 에러도 많아 잘 돌아가지 않아서 수정부분을 맡아 진행하였다.

> 이미 작성된 코드를 아무리 주석이 다 달려있다고는 하지만 한 줄 한 줄 코드를 해석하는데 조금 시간이 걸렸다.

### 필요 라이브러리
```python
from collections import OrderedDict
import requests # pip install requests
from selenium import webdriver  # pip install selenium
import bs4 #pip install bs4
import time
import re
import pandas as pd
import time
```
`필요 라이브러리`

진행방식은 requests를 이용해 각각 공고 링크를 저장하고 링크마다 selenium - webdriver를 이용해 세부 내용을 크롤링해 작업하는 방향으로 작성되었다.

### Chrome 옵션 설정
```python
# 옵션 설정
options = webdriver.ChromeOptions()

# 속도향상목적
options.add_argument("--disable-gpu")
options.add_argument("--window-size=1280x1696")
options.add_argument("--disable-application-cache")
options.add_argument("--disable-infobars")
options.add_argument("--no-sandbox")
options.add_argument('--disable-dev-shm-usage')
options.add_argument("--hide-scrollbars")
options.add_argument("--enable-logging")
options.add_argument("--log-level=0")
options.add_argument("--ignore-certificate-errors")
options.add_argument("--homedir=/tmp")
options.add_experimental_option("excludeSwitches", ["enable-logging"])
```
`Chrome 옵션 설정`

여기서 처음접한 내용이 2가지 정도 있었는데 속도 향상 목적으로 설정한 크롬 옵션이었다.
왜 저렇게 옵션을 설정해야 빠른지 아직도 이해가 가지 않지만 구글링을 통해 천천히 알아봐야겠다.
아직 프로젝트 들어가려면 2주가 넘게 남았다...ㅎ

### 전체 공고 링크 추출

```python
while True:
# for page in range(1,3):    # while문 안될 시, for문으로 쪼개기 필요하다 판단
    response = requests.get('https://www.saramin.co.kr/zf_user/jobs/list/industry?page='+str(page)+'&ind_cd=904%2C903%2C902%2C901%2C216&search_optional_item=n&search_done=y&panel_count=y&isAjaxRequest=0&page_count=50&sort=RD&type=industry&is_param=1&isSearchResultEmpty=1&isSectionHome=0&searchParamCount=1#searchTitle', headers=hrd)
    soup = bs4.BeautifulSoup(response.text, 'html.parser')
    
    # 쪼개기
    url_list = soup.select("div.list_item")
    

    if not url_list: # div의 job_tit이 없으면 break
        break

    
    for tmp in url_list:
        url = 'https://www.saramin.co.kr'+tmp.select_one('a').attrs['href']
        url_all.append(url)
        print(url)  
    page+=1
```
`전체 공고 링크 추출`

### 당일 공고 링크 추출

```python
while True:
# for page in range(1,30):    # while문 안될 시, for문으로 쪼개기 필요하다 판단
    response = requests.get('https://www.saramin.co.kr/zf_user/jobs/list/industry?page='+str(page)+'&ind_cd=904%2C903%2C902%2C901%2C216&search_optional_item=n&search_done=y&panel_count=y&isAjaxRequest=0&page_count=50&sort=RD&type=industry&is_param=1&isSearchResultEmpty=1&isSectionHome=0&searchParamCount=1#searchTitle', headers=hrd)
    soup = bs4.BeautifulSoup(response.text, 'html.parser')
    
    # 쪼개기
    url_list = soup.select("div.list_item")
    

    if not url_list: # div의 job_tit이 없으면 break
        break

    
    for tmp in url_list:
        url = 'https://www.saramin.co.kr'+tmp.select_one('a').attrs['href']
        regdate = tmp.select_one('span.reg_date').text
        print(regdate)
        if regdate == '(1일 전 등록)': # 1일 전 등록 확인 시 중지
            check = 1
            break
        else:
            url_all.append(url)
            print(url)
    if check == 1:
        break  
    page+=1
```
`당일 공고 링크 추출`

프로님이 나에게 요청한 것은 해당하는 모든 공고를 크롤링하는 것과 오늘 날짜로 올라온 공고를 크롤링하는 것이었다.
당일 공고는 1일 전 등록이라고 되어도 현재 오전 10시라고 가정한다면
11시간 전 공고는 어제 등록된 공고가 되므로
가장 늦은 시간인 밤 11시 기준 1일 전 등록까지 추출하여 나중에 필터하는 방향으로 작성하였다.
> 현재 시각이랑 24시 빼고 계산하는게 귀찮.... 속도는 신경쓰지 말래써...

### 세부 정보를 추출해 각 리스트에 저장

```python

for tmp in url_allset:
    url = tmp

#     # 로딩되는 시간 있으므로 3초 기다림.
    driver.implicitly_wait(10)

#     # 페이지 접속
    driver.get(url)

#     # 링크 열었을 때, 공고 종료시 에러 except 추가


#         # 회사명
    try:
        company = driver.find_element_by_xpath('//*[@id="content"]/div[2]/div[1]/div[1]/div[1]/div/a').text
        company_.append(company)
        print(company_)
    except:
        print(url,"채용공고없음")
        continue
      # 링크
    link_.append(url)
    print(url)
    
         # 공고명
    title = driver.find_element_by_xpath('//*[@id="content"]/div[2]/div[1]/div[1]/div[1]/div/h1').text
    title_.append(title)
    print(title_)
    
#         # 경력, 학력, 근무형태
#         # 현 페이지 xml 가져오기
    dom = bs4.BeautifulSoup(driver.page_source, "lxml")
    info1 = [_.find_all("strong") for _ in dom.select("div.cont > div.col")][0]
    test = []
    for i in info1:
        txt1 = re.sub('<strong>', '', str(i))
        txt2 = re.sub('</strong>', '', txt1)
        test.append(txt2)
    career_.append(test[0])
#     print(test[0])
    edu_.append(test[1])
#     print(test[1])
    try:
        type_.append(test[2])
#         print(test[2])
    except:
        type_.append("-") # 계약형태가 없을 시 - 넣기
        
#         # 시작일, 마감일
    info1 = [_.find_all("dd") for _ in dom.select(".status .info_period")][0]
    test = []
    for _ in info1:
        txt1 = re.sub('<dd>', '', str(_))
        txt2 = re.sub('</dd>', '', txt1)
        test.append(txt2.split()[0])

    start_.append(test[0])
    try:
        end_.append(test[1])
    except:
        end_.append("상시 채용 중") # 마감일이 없을 시 "상시 채용 중" 넣기

#         # 근무지역
    info1 = [_.find_all("dd") for _ in dom.select(".wrap_jv_cont .jv_summary .cont .col")][1][-1]
    txt1 = re.sub('<dd>', '', str(info1))
    txt2 = re.sub('</dd>', '', txt1)
    txt3 = txt2.strip()
    txt4 = ''
    loca = txt3.split()
    try:
        for _ in range(loca.index("<button")):
            txt4 += loca[_]
            txt4 += " "
        location_.append(txt4.rstrip())
    except:
        location_.append(loca)
        
 # 기업형태, 사원수, 설립일, 업종
    # 전체가 있을 때 우선 순위 : 기업형태 > 사원수 > 업종 > 설립일
    try: # 일단 시도
        cname = str([_.text for _ in dom.select(".wrap_info .title .company_name")][0])
        print(cname)

        if company == cname :
            print("True")

            info_list = str([_ for _ in dom.select(".wrap_info .info")][0])
            check = ["기업형태", "사원수", "업종", "설립일"]
            answer = []
            pos = 0

            for check_str in check:
                abc = info_list.find(check_str)
                if(abc == -1):
                    answer.append("-")

                else:
                    pos_ = info_list.find("title=") + 7
                    info_list = info_list[pos_:]
                    pos = info_list.index(">") - 1
                    answer.append(info_list[:pos])

                info_list = info_list[pos:]

            comp_type.append(answer[0])
            if answer[1] != "-":
                worker_num.append(answer[1][:answer[1].index("명") + 1])
            else:
                worker_num.append(answer[1])
            sector.append(answer[2])
            if answer[3] != "-":
                founding_date.append(answer[3][:answer[3].index("(")])
            else:
                founding_date.append(answer[3])
        else:
            comp_type.append("-")
            worker_num.append("-")
            founding_date.append("-")
            sector.append("-")

    except: # 안되면
        comp_type.append("-")
        worker_num.append("-")
        founding_date.append("-")
        sector.append("-")
```
`세부 정보를 받아 각 리스트에 저장(제일 아찔했던 곳)`

이 코드를 해석한다고 많이 애를 먹었던 것 같다. 처음엔 이 부분에서 빨간줄이 계속 나오면서 수정할수록 늘어나 새로 코드를 짰었다.(망했지만..)

이 때, xml 데이터를 처음 다뤄봤는데 그리 대단한건 아니었던거같다.

그래도 직접 코드를 짰을 때, Xpath를 이용해서 받아왔는데 속도가 너무 느려 도저히 안되겠다고 판단되어 해당 코드를 수정하는 방향으로 갔다.

### Xpath로 추출하는 방식(실패..)

```python
def etc_text(etc_,path):
    try:
        etc = driver.find_element_by_xpath(path).text
        etc_.append(etc)
    except:
        if etc_ == company_:
            etc_.append('채용공고없음')
        elif etc_ == end_:
            etc_.append('상시 채용 중')
        else:
            etc_.append('-')
    return etc_
```
`직접 짠 코드(다 짜고 이렇게 쉬운걸 왜 저렇게 복잡하게 하지 라고 생각함 ㅎ)`

위의 해당 코드로 받아오긴 했으나 Sa***in의 경우 공란을 두지 않고 그대로 한칸씩 당기는 설계로 하여 원하는 칸에 잘 들어가지 않았고,
속도 측면에서도 굉장히 느렸다.

### 필터 및 엑셀로 저장

```python
raw_data = {'공고링크': link_,
            '공고명': title_,
            '회사명': company_,
            '요구경력': career_,
            '요구학력': edu_,
            '계약형태': type_,
            '근무지역': location_,
            '시작일': start_,
            '마감일': end_,
            '기업형태': comp_type,
            '사원수': worker_num,
            '업종': sector,
            '설립일': founding_date}


# # 엑셀 추출 (엑셀을 저장할 경로 설정해야 함.)
data = pd.DataFrame(raw_data)
data = data[data['시작일'] == str(now.tm_year)+'.'+str(now.tm_mon)+'.'+str(now.tm_mday)]
data.to_excel('sa***in.xlsx', sheet_name='new_name', index=False, header=True)
print(now.tm_year, now.tm_mon, now.tm_mday, now.tm_hour, now.tm_min, now.tm_sec)
print("엑셀저장완료")
driver.close()
```
`필터 후 엑셀 파일로 저장`

공고 시작일을 받아오고 이를 데이터프레임으로 만들어 오늘 날짜와 같은 것만 받아오는 필터를 만들어 엑셀파일로 저장하였다.

> 그리 대단한걸 한건 아니지만 오랜만에 Python을 만지고 회사에서 교육만 듣고 눈치보고 있는 것보다 많이 나았다.
> 그리고 ---정보통신... 이정도는 그쪽에서 하세여...
> 근데 백신 휴가는 왜 안주는거야... 얼른 백신 휴가 주는 곳으로 가는 수 밖에 없을 것 같다... 흑
