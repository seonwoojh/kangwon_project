# 2021 탐색적 자료분석 및 실습 조별과제
[🙋‍♀️ppt 확인하기](https://github.com/seonwoojh/kangwon_project/blob/main/%ED%83%90%EC%83%89%EC%A0%81%20%EC%9E%90%EB%A3%8C%EB%B6%84%EC%84%9D_%ED%8C%80%EA%B3%BC%EC%A0%9C%202_1%EC%A1%B0.pdf)


![캡처](https://user-images.githubusercontent.com/71394778/131491646-015fbbca-db76-4a51-b059-0c356c8b75dd.PNG)






---

### 1. 분석주제
![국내여행 커머셜지수](https://user-images.githubusercontent.com/71394778/131490431-247d29cf-5ba9-468e-bf57-47d04ea692d2.PNG)

춘천하면 떠오르는 이미지는 무엇일까요? 경관 휴양 도시. 청정 환경도시. 문화예술의 도시 등 여러 이미지가 있습니다. 이 중 관광 도시에 초점을 맞춰 알아보고자 했습니다.
표에서 확인할수 있듯, 춘천은 SNS 노출 및 언급 횟수를 의미하는 소셜지수에서 13위, 여행 상품 노출횟수를 의미하는 커머셜 지수에서는 19위를 차지할 정도로 관광에 대한 관심이 높다는 것을 알 수 있습니다. 또한 2012년 처음으로 관광객 1000만명을 돌파했고, 2019년까지 8년 연속 관광객 천만시대를 열었습니다.
관광도시로서 춘천의 매력은 무엇인지, 무엇이 관광객을 춘천으로 오게 하는가에 대한 의문을 가지게 되어 주제로 선정하게 되었습니다.





### 2. 데이터 설명서


##### □ 원데이터 설명

* 일반철도여객수송-차종별 여객수송실적 (월) : 16년 1월 ~ 20년 12월
* 광역철도여객수송-역별 발착통과실적 (월) : 16년 1월 ~ 20년 12월
* 주요관광지점 입장객 : 16년 1월 ~ 20년 12월

---

##### □ 제출데이터 정보

|구분|파일명|
|:---:|:------:|
|1|Train_data.csv|
|2|Travel_data.xlsx|
|3|Total_data.csv|


##### □ 데이터 변수명

* 1. Train_data.csv

|변수명|변수 설명|변수값|
|:---:|:---:|:---:|
|year_month|연월|201601~202012|
|ITX_count|ITX청춘열차_하차승객 수(단위:명)|역별 하차승객 수(연속형)|
|GC_count|경춘선_하차승객 수(단위:명)|역별 하차승객 수(연속형)|


-> 1) ITX 청춘 하차 승객 수 변수 생성 (ITX_count)
  국토교통부 KRiC 철도통계의 공공데이터인 ‘일반철도여객수송-차종별 여객수송실적 (월)’은 각 차종, 연월, 역에 따른 승차 및 하차 승객 수가 기록된 데이터입니다. 저희는 ITX 청춘 차종 중 춘천의 행정구역에 속하는 역의 하차 승객 수를 선택하여 수집하였습니다. 최종적으로 ITX 청춘을 이용해 춘천에 방문한 인원을 알아보기 위해 연월을 기준으로 하차 승객 수를 더한 ITX_count 변수를 생성하였습니다.

-> 2) 경춘선 하차승객 수 변수 생성 (GC_count)
  국토교통부 KRiC 철도통계의 공공데이터인 ‘광역철도여객수송-역별 발착통과실적 (월)’은 각 노선, 연월, 역에 따른
승차 및 하차 승객 수가 기록된 데이터입니다. 저희는 경춘선 노선 중 춘천의 행정구역에 속하는 역의 하차 승객 수를 선택하여 수집하였습니다. 최종적으로 경춘선 노선을 이용해 춘천에 방문한 인원을 알아보기 위해 연월을 기준으로 하차 승객 수를 더한 GC_count 변수를 생성하였습니다.

-> 공통변수인 연월(year_month)를 기준으로 두 데이터를 병합하여 철도 데이터를 완성하였습니다.

---

* 2. Travel_data.xlsx

|변수명|변수 설명|변수값|
|:---:|:---:|:---:|
|year_month|연월|201601~202012|
|강촌레일파크|입장객 수(단위 : 명)|입장객 수(연속형)|
|국립춘천박물관|입장객 수(단위 : 명)|입장객 수(연속형)|
|김유정문학마을|입장객 수(단위 : 명)|입장객 수(연속형)|
|남이섬유원지|입장객 수(단위 : 명)|입장객 수(연속형)|
|막국수체험박물관|입장객 수(단위 : 명)|입장객 수(연속형)|
|물레길|입장객 수(단위 : 명)|입장객 수(연속형)|
|애니메이션박물관|입장객 수(단위 : 명)|입장객 수(연속형)|
|제이드가든|입장객 수(단위 : 명)|입장객 수(연속형)|
|춘천에티오피아전쟁기념관|입장객 수(단위 : 명)|입장객 수(연속형)|
|춘천지구전적기념관|입장객 수(단위 : 명)|입장객 수(연속형)|
|엘리시안 강촌스키장|입장객 수(단위 : 명)|입장객 수(연속형)|


->  문화체육관광부 관광지식정보시스템의 공공데이터인 ‘주요관광지점 입장객’에서 강원도 춘천만을 추출하여 춘천 행정 구역 내 주요 관광지 29곳이 포함된 데이터를 수집하였습니다. 총 29곳의 주요 관광지 중 두 가지 기준으로 데이터를 정제하였습니다. 

	1) 2016년 1월부터 2020년 12월까지의 기간 중 입장객 수가 지속적으로 집계된 관광지
	2) 춘천 행정 구역 내에 위치한 역에서 대중교통을 이용한 접근이 용이한 관광지

  위 두 가지 기준을 만족하는 춘천 주요 관광지 11곳을 선정하여 데이터를 생성하였습니다. 그 후 분석의 용이성을 위해 시계열 데이터의 포맷으로 변환하였습니다.
