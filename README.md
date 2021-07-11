# <Analysis_Of_Credit_Card_Company_Data>
[POSCO_AC_Project] 'S카드사' 카드 사용 특성을 반영한  차별화된 서비스 제공 및 텔레마케팅  성공 예측 모델 개발로 수익 향상

---
## Data
데이터 csv 파일은 공유하지 않음.
#### Card_data
- 옵션에서 결측치 확인 => 'S'카드사 홈페이지 크롤링을 통해 결측치 처리
- 주옵션 4가지(후불교통, 가족카드, 현금기능, IC기능)에 대해 One-Hot-Encoding
#### Card_Spending
- 파생 변수 생성  
  \- 1회 사용금액 (= 사용금액 / 사용횟수)  
  \- 연령대 (<- 연령)  
  \- 요일 (<- 사용일자)  
 - 이상치 처리  
  \- 주소 : 소비처(동네)가 올바른 지역(지역구)에 들어가 있지 않음. => 소비처에 맞추어 지역을 변경 => 주소 (= 지역 + 소비처) 변경  
  \- 사용횟수, 사용금액, 1회 사용금액 : Boxplot과 Histogram을 통해 이상치와 분포를 확인 => 소량의 데이터 제거 및 로그변환  
#### Telemarket
- p_days 결측치 확인 => 보간법으로 결측치 처리 => Boxplot과 Histogram을 통해 이상치와 분포를 확인 => 이상치가 매우 크고 상당히 불균형 => p_days 칼럼 삭제
- 연락시도횟수, 통화시간 : Boxplot과 Histogram을 통해 이상치와 분포를 확인 => 소량의 데이터 제거 및 로그변환 
- 파생 변수 생성  
  \- 연령대 (<- 연령)     
  \- 요일 (<- 사용일자)   
  \- 경제활동인구 (<- 직업군)
#### Merge_Data
- 'Card_ID'를 기준으로 merge_data1(= Card_data + Card_Spending), merge_data2(= Card_data + Telemarketing) 생성 
#### Crawling_final
- 'S' 카드사 홈페이지에서 Card_data의 카드 종류별 카드 옵션, 카드 사진을 긁어옴.
---
## 구성도
![구성도](https://user-images.githubusercontent.com/80561963/125186708-e2876e00-e266-11eb-8af9-e0a69929bda4.png)
---
## 개선안 설명
- 개선안1 : 20대 고객의 다양한 트랜드를 겨냥한 인기 있는 특정 기업과의 제휴 및 서비스 제공이 되는 신용카드 상품 출시
  ![개선안1](https://user-images.githubusercontent.com/80561963/125186965-30e93c80-e268-11eb-8483-1ddd0a44c9a6.PNG)
  
- 개선안2 : 고객 특성 분석을 통한 텔레마케팅 성공 예측 시스템 개발
  ![개선안2-1](https://user-images.githubusercontent.com/80561963/125186971-3777b400-e268-11eb-82fe-07e8249e3f80.PNG)  
  ![개선안2-2](https://user-images.githubusercontent.com/80561963/125186982-4cecde00-e268-11eb-9272-4b4090f39fd4.PNG)
---
Report
[포스코 아카데미 빅데이터 프로젝트.pptx](https://github.com/colin9597/Analysis_Of_Credit_Card_Company_Data/files/6796524/default.pptx)
