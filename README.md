# DATA ANALYTICS 개인 프로젝트
---
## 1. 프로젝트 개요
### 1.1 프로젝트명:
**2025년 SPAO 브랜드 충성 고객 확대 및 매출 증대 도모**

### 1.2 프로젝트 배경
최근 한국 경제의 저성장 기조가 지속되면서 **소비자의 소비 트렌드**에도 변화가 나타나고 있습니다.<br>
오픈서베이 설문조사에 따르면 소비자들은 **가성비**와 **품질**을 더욱 중요하게 고려하고 있습니다.<br>
고가 브랜드 제품이나 저렴한 제품보다는 **합리적인 가격**과 **적절한 품질**을 제공하는 제품을 선호하는 경향이 두드러집니다.
**SPA(전문점형 의류 제조 유통) 브랜드**는 기획, 생산, 유통 전과정을 직접 관리하여 **효율적인 운영**과 **빠른 시장 대응**이 가능합니다.<br>
이를 통해 **소비자의 니즈**를 신속하게 반영하고 **트렌드 변화**에도 유연하게 대응할 수 있어 **지속적인 성장세**를 이어가고 있습니다.<br>
또한, 오픈서베이 **MZ세대 패션 앱 트렌드 리포트 2024**에 따르면 만 15-39세 소비자 중 66.9%가 **온라인**을 통해 패션 상품을 구매하며, 특히 **무신사**는 50%의 점유율로 **가장 선호되는 패션 플랫폼**임이 확인되었습니다.
이는 **온라인 쇼핑 비중이 지속적으로 증가**하고 있음을 보여주며, **온라인 플랫폼의 영향력**이 매우 큼을 시사합니다.<br>
기존 SPA브랜드는 주로 오프라인 매장 중심의 판매 전략을 유지해왔으나, **온라인 플랫폼**을 활용한 **마케팅과 판매전략**이 점점 더 중요해지고 있습니다.<br>
이에 국내 상위 SPA 브랜드 중 하나인 **SPAO의 경쟁력을 강화**하기 위해 **온라인 소비자 리뷰 데이터**를 분석하고 **이커머스 플랫폼**을 활용한 **2025년 마케팅 전략을 수립**하고자 합니다. 

### 1.3 프로젝트 목표
**온라인 이커머스 플랫폼**을 통한 **SPAO 브랜드 충성 고객 확대 및 매출 증대**

### 1.4 사용환경, 패키지, 툴, 응용 프로그램
- 프로그래밍 언어: Python3
- 데이터 수집: Selenium, BeautifulSoup4
- 데이터 분석 및 전처리: Pandas, Numpy, Scipy, Matplotlib, Seaborn
- 머신러닝: Scikit-learn
- 머신러닝 알고리즘:
  - 리뷰 감성 분석: konopy-Okt, Tensorflow
  - 추천 시스템: 회귀분석
---
## 2. 데이터 수집

### 2.1 오픈 데이터 다운로드

1) 오픈서베이
   - MZ세대 패션 앱 트렌드 리포트 2024
     [바로가기](https://blog.opensurvey.co.kr/trendreport/mz-fashion-2024/)
   - 2024 소비자 소비 트렌드
     [바로가기](https://blog.opensurvey.co.kr/article/webinar-eatbuyplay-2024-5-buy/)

### 2.2 웹크롤링을 통한 데이터 수집
**이커머스 플랫폼: 무신사**
- 각 브랜드별 **제품 데이터 수집**
  - ['브랜드', '대분류', '소분류', '제품명', '제품ID', '제품 가격', '찜 수', '평점', 리뷰 갯수']
- 사용자 **리뷰 데이터 수집**
  - ['브랜드', '대분류', '소분류', '제품명', '제품ID', '사용자ID', '사용자별점', '사용자리뷰', '성별', '키', '몸무게']

### 2.3 설문조사 데이터 수집
**연령대별, 성별별 옷 구매 고려 요소**
- 연령대/성별/직업군별 구매 고려 요소
![image](https://github.com/user-attachments/assets/1d8e5f68-9b34-4c44-9f74-5d2c1c938119)
![image](https://github.com/user-attachments/assets/f739b938-eff3-4aaf-a2b5-f62afc97f21a)
![image](https://github.com/user-attachments/assets/dc668d85-8d71-4d8b-b462-243abf07be35)

- 모든 연령대, 성별, 직업군에서 **디자인**이 가장 중요한 요소로 나타남
  - **남성**: 디자인 > 품질 > 가격
  - **여성**: 디자인 > 가격 > 품질

- **연령대별 옷 구매수단 선호도**
![image](https://github.com/user-attachments/assets/69581fed-e150-44c7-9753-1327969591c7)

- 20 - 30대: **의류 전용 온라인 쇼핑몰** 이용률 높음
- 40대: 오프라인 및 11번가와 같은 **일반 온라인 쇼핑몰** 선호
- 50대 이상: **오프라인 매장** 이용 비율 압도적

- **구매수단 별 SPA 브랜드 선호도**
![image](https://github.com/user-attachments/assets/799ed0b7-49d4-4860-8868-b7f2a1160cce)

- **의류전용 온라인 쇼핑몰** 이용자의 경우 **무신사 스탠다드** 선호도 압도적
- **SPAO 브랜드**는 **오프라인 매장 이용** 비율 높음

#### SPAO브랜드 마케팅 인사이트
**1. 타깃 연령층에 맞춘 제품 기획**
- **패션 트렌드 리서치** 및 **빠른 디자인 적용** 전략 필요
- SNS 및 인플루언서를 활용한 **스타일링 제안 콘텐츠** 적극 활용

**2. 연령대별 가격, 품질 고려 비율 반영**
- 2030 세대: **가성비 제품 라인** 강화
- 40대: **고품질 기본 아이템 라인** 강화 및 **신뢰 높은 원단** 강조

**3. 쇼핑 채널별 마케팅 전략**
- 2030 세대: **무신사 내 SPAO 브랜드 페이지 최적화** 및 **온라인 전용 제품** 출시
- 40대: 네이버 스마트 스토어 및 11번가 **SEO 개선** 및 **오프라인 연계 프로모션** 진행
- 50대: **오프라인 매장 확대** 및 **체험형 매장** 운영 고려

**4. 브랜드 인지도 향상**
- **오프라인 매장 내 멤버십 혜택 강화**로 **충성고객 유도**
---

**데이터 관계 다이어그램**
![image](https://github.com/user-attachments/assets/ef3c3d54-c1ea-42b0-9d75-68aab0f785c6)

## 3. 데이터 전처리
### 3.1 데이터 병합
- 무신사 제품 리스트 파일에 **카테고리 데이터**를 추가하여 **분석의 일관성**을 유지했습니다.

### 3.2. 데이터 클렌징
**결측치 처리 및 열 추가**를 통해 데이터의 완성도를 높였습니다.

#### 3.2.1 무신사제품리스트.csv
- 수집한 카테고리 파일과 제품명을 매핑하여 **데이터 병합**
- **카테고리 결측치, 디지털/라이프 항목 삭제** 및 **스포츠/레저 카테고리 순서** 변경

#### 3.2.2 리뷰데이터 정제
- SPAO, TOPTEN, 8seconds, Mutendard 브랜드의 리뷰 데이터 병합
- **카테고리 오류 및 불필요한 행** 제거
- **제품ID** 열 및 **브랜드** 열 추가
- 열 이름 및 순서를 변경하고 **데이터 일관성 유지**

### 3.3 데이터 변환 및 표준화
#### 3.3.1 무신사_제품리스트_1차정제완료.csv
- **찜수, 리뷰 갯수**를 **정수형**으로 변환
- **찜수, 리뷰갯수를 이용해 (예측)매출량열 추가
<img width="256" alt="image" src="https://github.com/user-attachments/assets/357f58a8-298e-4b05-98f9-7a7154f5c619" />

- **가격 열 범주화**
- **저가**: 3만 원 이하
- **중저가**: 3만 원 초과 - 6만 원 이하
- **고가**: 6만 원 초과 - 9만 원 이하
- **럭셔리**: 9만 원 초과

#### 3.3.2 추가 데이터 정제
사용자 리뷰 데이터에서 **성별, 키, 몸무게**의 **결측치**를 대체하고 **정수형**으로 변환했습니다.
- 결측치 처리 기준:
  - **성별**: 사용자가 입력하지 않은 경우 **사용자ID**, **리뷰 내용**, **제품명**을 분석하여 성별 추정
  - **키**: 성별의 **평균값**으로 대체
  - **몸무게**: **중앙값** 혹은 **비정상 값**을 평균값으로 대체

#### 3.3.4 신체 범주화(체형 데이터 생성)
성별, 키, 몸무게를 기반으로 **체형 열 생성** 
- **체형 카테고리**:
  - 장신-슬림형
  - 단신-슬림형
  - 장신-볼륨형
  - 단신-볼륨형
- **체형 구분 기준**:
  - **성별 평균 키** 이상일 경우 **장신**, 미만일 경우 **단신**
  - **평균 몸무게** 이상일 경우 **볼륨형**, 미만일 경우 **슬림형**

### 3.4 데이터 전처리 요약 및 인사이트
- **매출량**열 추가를 통해 **제품별 인기 분석**이 가능해졌습니다.
- **가격 열 범주화**로 **가격대별 판매 전략 수립**에 기여했습니다.
- **체형 데이터 생성**으로 **체형별 제품 추천 시스템** 구축의 기반을 마련했습니다.
- **성별 및 체형 데이터 보완**으로 정확한 **고객 분석**이 가능해졌습니다.

---
## 4. 통계학적 분석 및 시각화
### 4.1 탐색적 데이터 분석(EDA) 가설 설정
**탐색적 데이터 분석**을 통해 **데이터의 특성**을 파악하고 **가설을 설정**했습니다.<br>
**시각화 도구**: Pandas, Matplotlib, Seaborn

#### 4.1.1 무신사_제품리스트 데이터 기반 가설

**1. 가설 1. 가격이 낮은 제품일수록 매출량이 높을 것이다.**
- **가격 범주**와 **매출량** 상관관계 분석
- **목적**: 가격대별 소비자 구매 패턴 확인 및 가격 전략 수립

**2. 가설 2. 특정 브랜드의 제품이 타 브랜드보다 매출량이 높을 것이다.**
- **브랜드별 평균 매출량** 비교 및 순위 분석
- **목적**: 경쟁사 분석 및 브랜드별 마케팅 전략 수립

**3. 가설 3. 특정 카테고리에서 높은 매출량을 보일 것이다.**
- **카테고리별 매출량** 비교 및 **인기 카테고리** 식별
- **목적**: 카테고리별 판매 집중 전략 및 제품 기획

#### 4.1.2 무신사 사용자리뷰 데이터 기반 가설 설정

**A. 성별 데이터 구분(대분류)**

|  | 표본수 |
|-|-|
|남성|30,239명|
|여성|15,995명|

![image](https://github.com/user-attachments/assets/060aba82-15bf-4014-a222-e4cdc2b7734a)

**B. 데이터 성별별/체형별 분류(소분류)**
- 체형A: 단신-슬림형
- 체형B: 장신-볼륨형
- 체형C: 장신-슬림형
- 체형D: 단신-볼륨형

|  |체형| 표본수 |
|-|-|-|
|**남성**|체형A|13,753명|
||체형B|10,156명|
||체형C|3,731명|
||체형D|2,599명|
|**여성**|체형A|6,001명|
||체형B|6,834명|
||체형C|1,744명|
||체형D|1,416명|

![image](https://github.com/user-attachments/assets/f46ca7d4-c109-4345-95e8-a740d7fbec6b)
  
**C. 체형별 표본 구분**
|체형| 표본수 |
|-|-|
|체형A|19,754명|
|체형B|16,990명|
|체형C|5,474명|
|체형D|4,015명|

![image](https://github.com/user-attachments/assets/cc9d24c4-dca7-410f-bc7b-3bf078503af1)

**1. 가설 4. 남성 소비자와 여성 소비자는 선호하는 브랜드가 다를 것이다.**
- **성별별 브랜드 선호도** 및 **매출량 차이 분석**
- **목적**: 성별 타깃 마케팅 전략 수립

**2. 가설 5. 특정 성별과 체형의 소비자는 특정 브랜드의 제품을 선호할 것이다.**
- **성별** 및 **체형별 사용자 별점**을 **브랜드별**로 비교
- **목적**: **체형별 맞춤 제품 추천** 및 **브랜드 포지셔닝** 전략

**3. 가설 6. 체형에 따라 선호하는 카테고리와 재구매 의향이 다를 것이다.**
- **체형별 카테고리 선호도 분석** 및 **리뷰 반복 분석**
- **목적**: **체형별 맞춤 제품 기획** 및 **고객 충성도 강화**

### 4.2 시각화 및 분석 결과
**가설별 시각화**를 통해 **분석 결과**를 도출했습니다.

#### 가설 1: 가격이 낮은 제품일수록 매출량이 높을 것이다.
- **목적**: 가격이 낮은 제품이 높은 매출량을 보이는지 확인하여 **가격 전략**수립에 활용
- **분석 방법**: **가격 범주**와 **매출량**의 **스피어만 상관계수 분석**
- **가격 범주**: 저가, 중저가, 고가, 럭셔리

1) 기초 통계 분석
- 제품 가격 평균: 약 29,733원
- 매출량 평균: 약 0.313(추정 매출량)
- 최소 가격: 3,900원 / 최대 가격: 161,390원
- 최소 매출량: 0.0 / 최대 매출량 15.79

**가격과 매출량의 관계**
<img width="386" alt="image" src="https://github.com/user-attachments/assets/877fdc59-cb24-491a-9250-148f1fe0f958" />

2) 시각화 자료 설명
- **그래프 유형**: 산점도(Scatter Plot)
- **가로축**: 가격 범주
- **세로축**: 매출량
- 가격과 매출량 관계 직관적 확인

3) **분석 결과**
- **스피어만 상관계수**: +0.135(약한 양의 상관관계)
- **p-value**: 0.05 미만(유의미한 상관관계)
- **해석**:
  - **가격이 낮을수록 매출량이 높은 경향**을 보임
  - 강한 연관성을 보이지 않음
  - **저가**, **중저가** 제품이 **높은 매출량**을 기록

##### 마케팅 인사이트
- **중저가 가격 전략**이 매출 증가에 유리합니다.
- **가격 인하**가 항상 매출 상승으로 이어지지는 않습니다.
- **가성비**, **고품질**을 강조한 **차별화된 광고 전략**이 필요합니다.

#### 가설 2: 특정 브랜드의 제품이 타 브랜드보다 매출량이 높을 것이다.
- **목적**: **브랜드별 매출 차이**를 분석하여 **경쟁 브랜드 전략** 수립에 활용
- **분석 방법**: **브랜드별 평균 매출량** 비교 및 순위 분석

1) 기초 통계 분석
- 평균 매출량 1위 탑텐(0.415)
- 최대 매출량 1위 스파오(15.79)

**브랜드별 평균 매출량**
<img width="416" alt="image" src="https://github.com/user-attachments/assets/3c4a2639-c1db-4da9-90e1-2e90930580ca" />

2) 시각화 자료 설명
- **그래프 유형**: 막대 그래프(Bar Plot)
- **가로축**: 브랜드(SPAO, TOPTEN, 8Seconds, Mutendard)
- **세로축**: 평균 매출량
- **막대 그래프**: 브랜드별 평균 매출량 비교 및 순위 시각화
  - TOPTEN: 평균 매출량 0.415로 1위
  - SPAO: 최대 매출량 기록, 그러나 평균 매출량은 낮음

3) **분석 결과**
- **스피어만 상관계수**: +0.269(약한 양의 상관관계)
- **p-value**: 0.05 미만(유의미한 상관관계)
- **해석**:
  - 브랜드별 매출량 차이가 존재
  - **TOPTEN**이 **가장 높은 평균 매출량** 기록
  - **SPAO**는 **최대 매출량**을 보유하였으나 평균 매출량이 낮음

##### 마케팅 인사이트
- **SPAO**는 일부 제품에서 **높은 판매량**을 기록하지만 **전체 평균 매출량**에서는 경쟁 브랜드(TOPTEN)에 비해 낮습니다.
- **대량 판매 제품 집중 마케팅**이 필요합니다.
- **이커머스 플랫폼**을 확대하고 **브랜드 차별화 전략**이 필요합니다.
  - TOPTEN과 차별화된 감성 광고를 집행하고 콜라보레이션 제품을 출시합니다.
- SPAO는 일부 제품에서 높은 판매량을 기록하였으나 전체 평균 매출량에서는 **경쟁 브랜드(탑텐)** 에 비해 **낮은 매출량**을 기록하였습니다.

#### 가설 3: 특정 카테고리에서 높은 매출량을 보일 것이다.
- **목적**: **카테고리별 매출 차이**를 분석하여 **효율적인 제품 기획**과 **마케팅 전략** 수립
- **분석 방법**: 카테고리별 평균 매출량 비교

1) 기초 통계 분석
- 특정 카테고리에서 높은 매출량을 보이는 것을 확인
  - 1위 아우터: 평균 0.557 / 최대 15.79
  - 2위 상의: 평균 0.363 / 최대 14.17
  - 3위 패션소품: 평균 0.358 / 최대 2.12
  - 4위 바지: 평균 0.194 / 최대 2.27
  - 5위 원피스/스커트: 평균 0.189 / 최대 0.95

**카테고리별 평균 매출량**
<img width="415" alt="image" src="https://github.com/user-attachments/assets/4fa0ed83-b7b5-4fe6-afeb-63787b7accce" />

2) 시각화 자료 설명:
- **그래프 유형**: 막대 그래프(Bar Plot)
- **가로축**: 카테고리(대분류)
- **세로축**: 평균 매출량
- **막대 그래프**: 카테고리별 평균 매출량 비교
  - **아우터**와 **상의**가 높은 매출량 기록
  - **잡화**는 가장 낮은 매출량

3) **분석 결과**
- **스피어만 상관계수**: +0.106(약한 양의 상관관계)
- **p-value**: 대부분 0.05 미만(유의미한 상관관계)
- **해석**:
  - **아우터, 상의, 바지** 카테고리가 높은 매출량을 기록
  - **패션소품**은 매출 변동성이 크지만 평균 매출량이 높음

##### 마케팅 인사이트
- 아우터 및 상의 카테고리에 **판매 집중 전략**이 필요합니다.
- **겨울 시즌 아우터 집중 프로모션** 및 **상의+아우터 세트 할인 프로모션**등을 진행합니다.
- 패션소품과의 **세트 상품 구성**으로 콜라보를 진행합니다.
- 상대적으로 매출량이 낮은 **원피스/스커트**는 디자인을 리뉴얼하거나 트렌디한 상품을 출시해야 합니다.

#### 가설 4: 남성과 여성 소비자는 선호하는 브랜드가 다를 것이다.
- **목적**: **성별에 따른 브랜드 선호도 차이**를 분석하여 타겟 마케팅 전략 수립
- **분석 방법**: **성별별 브랜드 선호도** 및 **매출량 차이 분석**
- **성별 구분**: 남성, 여성

**브랜드별 평균 매출량**
![image](https://github.com/user-attachments/assets/8dd65b87-a60e-4c8e-8be8-85a83cf78929)

**브랜드별 성별 리뷰 수**
![image](https://github.com/user-attachments/assets/3de1c9c6-af99-497f-852c-81d6a5b0f87c)

**브랜드별 매출량(성별 비율)**
![image](https://github.com/user-attachments/assets/c7722b0c-fe3b-440e-8879-bd2acdf002e7)

1) 시각화 자료 설명
- **그래프 유형**: 누적 막대 그래프(Stacked Bar Plot) 및 파이 차트(Pie Chart)
- **가로축**: 브랜드(SPAO, TOPTEN, 8Seconds, Mutendard)
- **세로축**: 매출 비율(%) / 리뷰 갯수
- **누적 막대 그래프**: 성별별 리뷰 갯수 비교 및 브랜드 선호도 차이 시각화
- **파이 차트**: 남성과 여성의 **브랜드 선호 비율** 시각화

2) **분석 결과**:
- **스피어만 상관계수**: -0.8(강한 음의 상관관계)
- **p-value**: 0.2(유의미한 상관관계가 아님)
- **해석**:
  - **성별 리뷰 갯수**와 **매출량**은 음의 상관관계를 보임
  - **p-value**가 0.2로 유의미한 상관관계는 아님
  - 특정 성별이 특정 브랜드를 선호할 수는 있지만 평균 매출량과 직접적인 연관성이 확인되지 않음

##### 마케팅 인사이트
- **성별별 브랜드 선호 비율**에는 차이가 있으므로 **타겟 소비층**을 구분하여 브랜드 포지셔닝 전략이 필요합니다.
- SPAO: **여성 리뷰 비율**이 높으므로 **여성 타겟 감성 광고**를 강화합니다.
- TOPTEN: **남성 리뷰 비율**이 높으므로 **남성 전용 제품 라인**을 강화하고 **스타일링 콘텐츠를 제작합니다.
- Mutendard: **성별 차이**가 크지 않으므로 **유니섹스 상품**을 강화합니다.

#### 가설 5: 특정 성별과 체형의 소비자는 특정 브랜드의 제품을 선호할 것이다.
- **목적**: 성별 및 체형별 브랜드 선호도를 분석하여 **맞춤형 제품 추천 시스템** 기획
- **분석 방법**: **성별** 및 **체형별 사용자 별점**을 브랜드별로 비교
- **체형 구분**:
  - 장신-슬림형
  - 단신-슬림형
  - 장신-볼륨형
  - 단신-볼륨형

1) 기초 통계 분석
- **무신사 스탠다드** - MAX: 4.83(단신-볼륨, 남성) / MIN: 4.73(단신-볼륨, 여성)
- **스파오** - MAX: 4.85(장신-볼륨, 남성) / MIN: 4.78(장신-볼륨, 여성)
- **에잇세컨즈** - MAX: 4.85(장신-슬림, 남성) / MIN: 4.70(단신-볼륨, 여성)
- **탑텐** - MAX: 4.88(장신-슬림, 남성) / MIN: 4.71(단신-슬림, 여성)

**브랜드별 성별 및 체형 별 평균 사용자별점**
![image](https://github.com/user-attachments/assets/d773f5d1-3037-4f3d-9e7d-a070dabc5c6a)

2) 시각화 자료 설명
- **그래프 유형**: 박스 플롯(Box Plot)
- **가로축**: 브랜드(SPAO, TOPTEN, 8Seconds, Mutendard)
- **세로축**: 사용자 별점(1-5점)
- **BOX PLOT**: **성별 및 체형별 사용자 별점** 분포 시각화
  - **장신-슬림형 남성**: **TOPTEN**에서 가장 높은 별점 기록
  - **단신-볼륨형 여성**: **SPAO**에서 가장 높은 별점 기록

3) **분석 결과**:
- **스피어만 상관계수**: -0.4(약한 음의 상관관계)
- **p-value**: 0.6(유의미한 상관관계 아님)
- **해석**:
  - **특정 성별**과 **체형**이 브랜드 선호도에 영향을 줄 수 있지만 평균 매출량과 직접적인 연관성이 확인되지 않음
  - **장신-슬림형 남성**은 **TOPTEN** 선호
  - **단신-볼륨형 여성**은 **SPAO** 선호

##### 마케팅 인사이트
- TOPTEN: **장신-슬림형 남성 타겟** 맞춤형 마케팅을 강화합니다.
  - 장신-슬림형 핏을 강조한 **스타일링 콘텐츠**를 제작합니다.
- **SPAO**: **단신-볼륨형 여성**을 타겟으로 한 맞춤형 제품을 추천합니다.
  - 볼륨감을 살린 디자인과 슬림핏 아이템을 확대합니다.
- 8Seconds: **슬림형** 체형을 위한 **핏 가이드**를 강화하고 **체형별 제품 추천 시스템**을 구축합니다.

#### 가설 6-1: 체형에 따라 선호하는 카테고리가 다를 것이다.
- **목적**: **체형별 카테고리 선호도 차이**를 분석하여 **맞춤형 제품 기획**에 활용
- **분석 방법**:
  - **체형별 카테고리 리뷰 수** 및 **평균 별점** 비교
  - **소분류 워드클라우드**를 통해 세부 선호도 분석
- **체형 구분**:
  - 장신-슬림형
  - 단신-슬림형
  - 장신-볼륨형
  - 단신-볼륨형

1) 기초 통계 분석
- 체형별로 특정 제품 카테고리에 대한 리뷰 갯수 및 평균 사용자 별점 차이가 존재
- EX. '단신-볼륨형': '바지', '아우터' 등에 대한 리뷰가 많고 별점이 높음
                  : '속옷/홈웨어' 등에 대한 리뷰 수가 적고 평균 별점이 낮음

**카테고리/체형별 리뷰수 비교**
![image](https://github.com/user-attachments/assets/fc388324-4429-409f-916a-88c82c18cdeb)

**체형별 카테고리별 평균 사용자별점**
![image](https://github.com/user-attachments/assets/e13ff67d-c667-4eeb-8b70-2046464d3290)

2) 시각화 분석:
- **그래프 유형**:
  - 누적 막대 그래프
  - 평균 별점 히트맵
  - 소분류 워드 클라우드

**카테고리 리뷰 수 비교**
- **가로축**: 카테고리(대분류)
- **세로축**: 리뷰 수
- **누적 막대 그래프**: 체형별 카테고리 리뷰 수를 막대 그래프로 표현
  - **바지**와 **상의**가 모든 체형에서 가장 많은 리뷰수 기록
  - **패션 소품**은 **단신-볼륨형**과 **장신-슬림형**에서 리뷰 비율이 높음
  - **원피스/스커트**는 모든 체형에서 리뷰수가 낮음

**체형별 카테고리 평균 별점 비교**
- **가로축**: 카테고리(대분류)
- **세로축**: 체형
- 설명: 진한 색상일수록 높은 별점이며 연할 수록 낮은 별점을 보임
- **분석 결과**:
  - **장신-슬림형**
    - **속옷/홈웨어**와 **키즈**에서 압도적으로 높은 별점 기록
    - **핏이 편한 디자인**에 만족도가 높을 것으로 예상
    - 타 카테고리에서도 대체로 높은 별점
  - **장신-볼륨형**
    - **바지**에서 높은 별점 기록
    - **원피스/스커트**와 **신발**에서 낮은 별점 기록
      - 특히 사이즈 문제로 인한 핏 불만이 주 원인
      - **사이즈 다양화** 및 **디자인 보완 필요**
  - **단신-슬림형**
    - 대체로 비슷한 별점 기록
    - 패션소품에서 낮은 별점 기록
      - **패션 잡화**의 스타일 다양화 필요
      - **다양한 디자인**, **색상 추가**
  - **단신-볼륨형**
    - **키즈** 카테고리가 가장 높은 별점 기록
    - 대체로 별점이 높으나 **속옷/홈웨어**에서 낮은 별점 기록
      - **사이즈 다양화**, **편안한 디자인** 필요

**리뷰수가 많은 소분류 키워드**
![image](https://github.com/user-attachments/assets/78fd47c8-35e3-43e4-b950-b707e726877b)

**소분류 워드클라우드 분석**
- 모든 체형에서 **슈트 팬츠/슬랙스**가 가장 많이 언급됨
  - 특히 **장신**라인에서 선호도가 높음
  - **슬랙스와 슈트 팬츠**는 다양한 스타일링과 활용도가 높아 리뷰수가 많음
 
3) **분석 결과 및 결론**
- **스피어만 상관계수**: -0.39 (약한 음의 상관관계)
- **p-value**: 0.0187 (유의미한 상관관계)
- **해석**:
  - 체형에 따라 선호 카테고리 및 소분류가 다르게 나타남
  - 슈트 팬츠/슬랙스는 모든 체형에서 가장 선호
  - 키즈는 평균 별점이 가장 높음, 신발은 평균 별점이 낮음
  - 원피스/스커트는 리뷰 수가 매우 적고 별점도 낮음

##### 마케팅 인사이트
1. 전 체형 공통 인사이트
- **슈트팬츠/슬랙스**가 모든 체형에서 가장 선호되는 카테고리
  - 다양한 핏(슬림핏, 와이드핏)과 색상을 추가합니다.
  - **상하의 세트**를 구성하고 할인 프로모션을 진행합니다.
  - **스타일링 콘텐츠**를 강화하고 리뷰 기반 추천 시스템을 구축합니다.
2. 체형별 맞춤 마케팅 전략
- **장신-슬림형**:
  - **편안한 소재**와 **루즈핏 디자인**을 강화합니다.
  - 키즈 카테고리에서 **부모-아이 패밀리룩**을 제안합니다.
  - **슬림형 체형 전용 핏 가이드**와 스타일 추천 시스템을 구축합니다.
- **장신-볼륨형**:
  - **높은 별점 카테고리**: 바지(허리밴드)
  - **낮은 별점 카테고리**: 원피스/스커트
  - **마케팅 전략**:
    - 바지 카테고리에서 편안한 핏과 허리밴드 디자인을 강화합니다.
    - **원피스/스커트**에서 사이즈를 다양화하고 핏을 보완하는 디자인을 도입합니다.
    - **장신 체형 전용 사이즈 가이드**를 제공합니다.
- **단신 슬림형**:
  - **낮은 별점 카테고리**: 패션소품
  - **마케팅 전략**:
    - 패션 소품 디자인을 다양화하고 컬러를 추가합니다.
    - **트렌디한 스타일**과 **액세서리 세트** 구성을 제안합니다
    - **패션소품 스타일링 콘텐츠**를 강화합니다.
- **단신-볼륨형**:
  - **높은 별점 카테고리**: 키즈
  - **낮은 별점 카테고리**: 속옷/홈웨어
  - **마케팅 전략**:
    - 속옷/홈웨어 카테고리에서 사이즈를 다양화하고 편안한 디자인을 도입합니다.
    - 키즈 카테고리에서 패밀리룩이나 커플룩 스타일링을 제안합니다.

#### 가설 6-2: 체형에 따라 재구매 의향이 다를 것이다.
- **목적**: **체형별 재구매 의향 차이**를 분석하여 **고객 충성도 강화 전략** 수립
- **분석 방법**:
  - **체형별 리뷰 반복 비율** 및 재구매 의향 분석
  - 리뷰 내용 분석을 통한 **재구매 이유** 및 **불만족 요인** 도출
- **검증 방법**:
  - 기초 통계 분석: 체형별 리뷰 수 비교
  - 정규성 검정: Q-Q plot 및 분포도 확인
  - 체형별 리뷰수 최댓값 분포 비교

1) 기초 통계 분석
- **체형별로 리뷰수 차이** 존재
   |체형| 리뷰수 |
   |-|-|
   |단신-슬림형|19,754명|
   |장신-볼륨형|16,990명|
   |장신-슬림형|5,474명|
   |단신-볼륨형|4,015명|
- **해석**:
  - 리뷰 수 차이는 존재하지만 리뷰 수가 많다고 재구매 의향이 높다고 단정할 수 없음
  - **동일한 계정**으로 여러 개의 리뷰를 남긴 경우, 해당 사용자가 **재구매 의향이 높다고 판단**하고 분석 진행

**Q-Q Plot 및 분포도 분석**
![image](https://github.com/user-attachments/assets/efa53096-7ce9-42cb-8cd6-1c09ee34cbfc)

- 정규 분포를 따르지 않음
- 75%까지 1개의 리뷰만 기록 -> 평균 1.2개의 리뷰
- 일부 사용자는 높은 리뷰 수 기록
  - **리뷰 수 상위 25%가 전체 리뷰에서 큰 비중을 차지
  - 리뷰 수 편차가 크게 나타남

**체형별 리뷰수 최댓값 분포 비교**
![image](https://github.com/user-attachments/assets/bbcfc317-ecaf-411c-8164-bfd17e1c7948)

- 체형별 리뷰수 최댓값 분포 비교:
  - **장신-슬림형** 및 **단신-슬림형**의 리뷰 수 최댓값이 **높은 분포** 기록
  - **장신-볼륨형**과 **단신-볼륨형**은 상대적으로 낮은 리뷰 수를 기록

4) 결론
- **체형별 재구매의향**에 **유의미한 차이**를 보이고 있음
  - **장신-슬림형** 및 **단신-슬림형**은 리뷰 수 최댓값이 압도적으로 높음
    - 슬림형 체형의 사용자 재구매 의향이 높음
  - **장신-볼륨형** 및 **단신-볼륨형**은 상대적으로 낮은 리뷰수를 기록
    - 볼륨형 체형 사용자의 재구매 의향이 낮음

##### 마케팅 인사이트
1. **슬림형 체형**
- 높은 재구매 의향을 유지하며 **충성 고객층**으로 확보합니다.
- **마케팅 전략**:
  - **멤버십 혜택 강화**: 포인트 적립, 리뷰 이벤트, 전용 프로모션 기획
  - **재구매율 높은 카테고리**에 세트 할인 프로모션 진행
2. **볼륨형 체형**
- 낮은 재구매 의향을 개선하기 위한 전략이 필요합니다.
- **마케팅 전략**:
  - 사이즈를 다양화하고 핏 보완 디자인을 도입합니다.
    - 허리-엉덩이 비율을 고려한 **볼륨형 전용 핏** 출시
  - **핏 보장 교환, 환불 정책**과 **상담 서비스**를 강화합니다.
  - **체형 커버 스타일링 콘텐츠**와 **리얼핏 리뷰 콘텐츠**를 제작합니다.

### 4.3 통계적 분석의 결론

#### 4.3.1 무신사 제품리스트 파일에 대한 분석 결론

**SPAO 마케팅 전략 도출**
1. **가격 전략:**
- 가성비+고품질/트렌디 제품 출시
 - **리미티드 에디션 출시** 또는 **인기 상품 리뉴얼**
   - 가격대를 강조하면서 **고품질**과 트렌디한 디자인**을 차별화 포인트로 활용
   - **가성비 캠페인**과 **프리미엄 이미지**를 동시에 전달(합리적인 가격, 트렌디한 디자인 브랜딩)

2. **브랜드 인지도 및 차별화 전략:**
- 플랫폼 입점 확장 및 차별화
 오픈서베이 'MZ세대 패션앱 트렌드 리포트 2024'에 따른 이커머스 플랫폼 순위
 ![image](https://github.com/user-attachments/assets/c7b8cb72-030e-45f1-ae31-d454a011980a)
 
 - 현재 입점: '무신사', '에이블리', '지그재그'
   - **SPAO 컬렉션 강화** 및 **전용 이벤트 진행**
 - 미입점: '29CM', 'W-Concept'
   - 새로운 플랫폼으로 **입점 확대** 및 **신규 고객층 확보**
 - SNS / 크리에이터 협업 강화
   - 인플루언서 및 패션 크리에이터와 협업 콘텐츠 제작
   - 바이럴 마케팅 진행

3. **대량 판매 제품 집중 마케팅 전략:**
- **예측 매출량**이 높은 카테고리 집중 마케팅
  - **아우터, 상의** 등의 고매출 카테고리에 집중 투자
    - **시즌별 할인**, **세트 판매** 등으로 구매 유도
    - **특정 시즌** 및 **트렌드**에 맞춘 집중 마케팅 캠페인 
- **패션소품 판매 확대**
  - **트렌드 기반 소품 출시** 및 **세트 구성**으로 소비 유도
  - 충동 구매 유도를 위한 소품 기획 및 연계 프로모션
 
#### 4.3.2 무신사 제품리스트 + 사용자 리뷰 파일에 대한 분석 결론

**SPAO 마케팅 전략 도출**
1. **브랜드별 주요 소비층 맞춤형 광고 집행:**
- 남성 비율이 높은 브랜드
  - **남성 타깃 패션 콘텐츠** 강화
    - 체형별 스타일링 가이드 및 베이직 라인 추천
    - 남성 고객 대상 추가 할인 이벤트 기획
- 여성 비율이 높은 브랜드
  - **여성 고객 맞춤형 감성 광고** 캠페인
    - 여성 전용 라인을 중심으로 **SNS 광고** 및 **인플루언서 마케팅** 확대
    - **고객 맞춤형 쇼핑 경험 제공**을 통한 고객층 유입 강화

2. **체형별 핏 가이드 맞춤형 추천 서비스:**
- **체형별 추천 시스템 도입**
  - 소분류 선호도 분석 데이터를 활용한 맞춤형 제품 추천
    - **체형별 선호도**에 맞는 **카테고리 제품 추천**
    - **만족도 높은 제품군**을 디자인 기획에 반영
  - **체형별 핏 가이드 제공**
    - 체형별 스타일링 팁과 코디 추천 콘텐츠 강화
    - **고객 맞춤형 사이즈 추천 시스템** 구축
  
3. **특정 체형별 브랜드 충성도 강화를 위한 맞춤형 마케팅 전략:**
- 리뷰수가 많은 소비자 타깃군 분석
  - **리뷰 빈도가 높은 고객**은 **재구매 의향이 높음**
  - **회원제 혜택** 또는 **포인트 적립** 제공
  - **충성 고객**에게 VIP 등급 및 맞춤형 할인 혜택 제공
  - 체형별 만족도가 높은 브랜드에 **로열티 프로그램** 적용

4. **리뷰 감성 분석을 통해 제품 개선 및 광고 메시지 반영:** (이후 진행 예정)
- 머신러닝 과정에서 리뷰 감성 분석
  - **긍/부정 피드백** 추출
    - **긍정 피드백: 광고 메시지 키워드**로 활용
      - 고객 만족 포인트를 강조한 광고 콘텐츠 제작
    - **부정 피드백: 제품 보완 및 개선**
      - 부정 리뷰에서 개선점을 반영한 리뉴얼 제품 출시
      - 고객 불만을 적극적으로 해결하여 브랜드 신뢰도 강화

---
## 5. 머신러닝
### 5.1 개요 및 목적
- **목적**:
  - **리뷰 데이터**와 **사용자 특성 데이터**를 활용하여 **제품 추천 시스템** 구축
  - **체형별 선호도 분석**을 통한 **맞춤형 추천 시스템** 개발
  - **리뷰 감성 분석**을 통한 **제품 개선** 및 **마케팅 메시지** 최적화
- **모델 선정 기준**
  - 정확도와 추천 성능이 높고 해석 가능성이 높은 모델 선정
  - **사용자 경험**을 고려한 추천 시스템 구현

### 5.2 리뷰 감성 분석
#### 5.2.1 목적 및 데이터 전처리
- **목적**:
  - **리뷰 데이터**를 **긍정/부정/중립**으로 감성 분류
  - **리뷰 감성 분석**을 통한 **제품 개선점**을 도출하고 **마케팅 메시지**에 반영
  - **긍/부정 키워드** 분석을 통한 제품 기획 및 광고 콘텐츠 최적화
- **Tensorflow**를 사용하여 딥러닝 모델로 감성 분석 진행
- 정확한 감성 분류를 위해 리뷰 데이터를 전처리하고 **모델 학습 및 평가** 수행

#### 5.2.2 데이터 전처리 및 준비
**1. 데이터 수집 및 전처리**
- 데이터 수집:
  - **네이버 쇼핑 리뷰 데이터** 수집
  - 평점, 리뷰 텍스트를 로드한 후 **중복 리뷰 제거**
- Label 생성:
  - 평점을 기준으로 긍/부정 레이블링
    - 5, 4점 --> 긍정(1)
    - 2, 1점 --> 부정(0)
    - 3점 --> 중립(2)
- 텍스트 전처리:
  - **한글 이외의 문자 제거**(특수문자, 숫자 등)
  - **불용어(Stopwords) 제거**
    - '그리고', '한', '있다' 등 의미 없는 단어 삭제
  - 형태소 분석 및 토큰화:
    - **KoNLPy**를 사용하여 형태소 분석
    - 문장 토큰화 및 정수 인코딩
    - 문장 길이를 동일하게 맞추기 위해 패딩 적용

  **2. 데이터 준비 및 인코딩**
  - 학습용 데이터셋 준비:
    - 훈련 데이터(80%) / 테스트 데이터(20%) 분할
    - 정수 인코딩 및 패딩 완료
  - 토크나이저:
    - TensorFlow Tokenizer 사용
    - **shopreviewnaver.pkl**로 저장
  - 모델 학습 데이터 저장:
    - **shopreviewnaver.keras**로 모델 저장
    - 데이터셋과 토크나이저를 TensorFlow 포맷으로 저장

#### 5.2.3 모델 학습
- TenserFlow를 사용하여 모델 학습
- LSTM(Long Short-Term Memory) 모델 사용
  - 문맥 이해 및 순서 정보 반영
- 학습한 모델을 **shopreviewnaver.keras**로 저장

#### 5.2.4 모델 평가
- **무신사 사용자리뷰 데이터**를 로드하여 모델 평가 및 감성 분석 진행
- **분류 기준**:
  - 50% 초과: 긍정
  - 50%: 중립
  - 50% 미만: 부정
- 점수 부여:
- 매우 부정: 1, 조금 부정: 2, 중립: 3, 조금 긍정: 4, 매우 긍정: 5
- **분류 결과**:
  - 5점: 40,150개 (긍정 비율 높음)
  - 1점: 3,840개 (부정 비율 낮음)
  - 4점: 1,237개
  - 2점: 1,007개
  - 3점: 0 (중립 비율 낮음)

#### 5.2.5 추가 EDA 분석

**1. 특정 키워드가 포함된 리뷰에서 감성점수에 차이가 있을 것이다.**
- **목적**:
  - 긍/부정 리뷰에 주로 언급되는 키워드를 분석하여 **제품 개선 포인트** 도출
  - **긍정적 평가**를 받은 요인과 **부정적 평가**를 받은 불만 사항 파악
- **분석 방법**:
  - 리뷰 키워드 추출 후 **워드클라우드 시각화**
  - 긍정(4,5점) 리뷰 키워드와 부정(1,2점) 리뷰 키워드를 비교 분석

**긍정, 부정 리뷰 키워드 시각화**
![image](https://github.com/user-attachments/assets/6103cfa1-b1e0-4366-9577-b06cbb3c6650)

**긍정 리뷰 주요 키워드**
- '입을', '보기', '사이즈', '핏', '여름에', '편하고', '가성비', '이쁘고' 등
- **긍정 키워드 분석**:
  - '입을', '보기': 제품 착용 후 **기대에 부합**하여 만족도가 높음
  - '사이즈', '핏': **예상 핏**과 **착용 핏**이 일치할 때 긍정적인 평가로 이어짐
  - '여름에': **계절성 제품**에서 긍정적인 평가가 많음
  - '가성비': **가격 대비 품질**에 대한 만족도가 높음
  - '이쁘고': **디자인**이 기대에 부합하며 긍정적인 평가로 이어짐

**부정 리뷰 주요 키워드**
- '많이', '보기', '사이즈', '핏', '입으면', '크게', '길이', '기장', '허리', '얇아서' 등
- **부정 키워드 분석**:
  - '사이즈', '핏': **예상 핏**과 **착용 핏**의 불일치로 불만 발생
  - '크게', '길이', '기장', '허리': **사이즈 문제** 및 **핏 불만** 발생 예상
  - '얇아서': **원단 두께**에 대한 **품질 불만** 발생
  - '불편': **착용감 불만**으로 부정적 평가

##### 마케팅 인사이트
- **긍정 요인 강화 전략**
  - **사이즈 가이드**를 상세히 제공하여 긍정 요소를 강화합니다.
  - **모델 피팅 정보** 및 **리뷰 기반 사이즈 추천 시스템**을 구축합니다.
  - **가성비 캠페인** 및 **할인 프로모션**을 강화합니다.
  - **가격 대비 품질**을 강조한 광고 메시지를 캠페인에 적용합니다.
- **부정 요인 개선 전략**
  - **사이즈 다양화** 및 **핏 보완 디자인**을 도입하여 불만을 해소합니다.
  - **핏 보장 교환/환불 정책** 및 **사이즈 상담 서비스**를 강화합니다.
  - **원단 두께**를 상세설명에 명시하고 **원단 정보** 및 **착용감 후기**를 고객 리뷰 콘텐츠에 반영합니다.

**2. 특정 카테고리에 따라 감성 점수가 다를 것이다.**
- **목적**:
  - **카테고리별 감성 점수** 차이를 분석하여 고객 만족도 및 불만 사항 파악
  - **카테고리별 특징**을 반영한 **맞춤형 마케팅 전략** 수립
- **분석 방법**:
  - 대분류, 소분류 별로 **감성 점수 평균** 및 **분포** 비교
  - Kruskal-Wallis Test를 통해 유의미한 차이 검증 완료
  - **대분류 및 소분류 별 감성 점수 시각화**
  
**대분류별 감성 점수 시각화 및 분석**
![image](https://github.com/user-attachments/assets/7a2cc16b-2e70-4634-a8fb-a60374ab9492)

1) 시각화 자료: 대분류별 감성 점수 박스플롯
- **가로축**: 대분류 카테고리
- **세로축**: 감성 점수 평균

2) **분석 결과**:
- **키즈, 하의, 가방**: 높은 감성 점수 기록
  - 키즈: **편안한 핏**과 **기능성** 만족 예상
  - 하의: **편안한 착용감**, **핏 만족도** 높음 예상
  - 가방: **실용성**에 대한 만족도 높음 예상
- **패션 소품, 신발, 잡화**: 낮은 감성 점수 기록
  - 신발: **사이즈 문제**, **착용감 불만** 예상
  - 패션 소품: **디자인 불만**, **기대와 다른 착용감** 예상
   
**소분류별 감성 점수 시각화 및 분석**
![image](https://github.com/user-attachments/assets/1ee06e65-1c9e-49dd-a6d7-9797447a3ea5)

1) 시각화 자료
- 소분류별 감성 점수 상/하위 10개 바 차트
- **가로축**: 소분류 카테고리
- **세로축**: 감성 점수
- **상위 10개**: 높은 감성 점수를 기록한 소분류 카테고리
- **하위 10개**: 낮은 감성 점수를 기록한 소분류 카테고리

**감성점수가 높은 상위 10개의 소분류**
- **소분류별 상위 10개의 바 차트**
- **맨투맨, 재킷, 기획아우터, 가방**등 **착용감이 좋은 제품군** 다수 포진
- **특정 기능성 제품**일 경우 **겨울철 보온성** 및 **내구성 만족**으로 긍정 리뷰 다수
- **시즌성 제품**은 계절별 만족도가 높아 긍정적인 감성 점수 기록

2) **분석 결과**
- **가방**: 실용성과 디자인 만족으로 긍정적인 평가가 이어짐
- **기획아우터, 재킷**: 보온성 및 착용감 만족으로 높은 점수 기록
- **맨투맨**: 편안한 착용감과 다양한 스타일링 가능성으로 긍정적인 평가
- **시즌성 제품**은 **계절 적합성**에 따라 긍정적인 리뷰 발생

3) **마케팅 인사이트**
- 시즌성 제품의 긍정적인 평가에 주목하여 **시즌별 프로모션**을 진행합니다.
  - **겨울철 보온성** 및 **여름철 통기성**을 강조한 시즌성 광고 캠페인
  - **계절별 맞춤 스타일링 콘텐츠** 제작
- 기획아우터 및 맨투맨의 **편안한 착용감**을 **광고 메시지**에 활용합니다.
  - **리얼핏 리뷰**를 광고 콘텐츠에 반영
  - **편안한 스타일링**과 **활용도 높은 디자인**을 강조

**감성점수가 낮은 상위 10개의 소분류**
- **소분류별 하위 10개의 바 차트**
- 슈트/블레이저, 반팔, 슬랙스, 신발류 등 **핏과 사이즈**가 중요한 제품군 다수 포함
- 신발류는 **사이즈 불만** 및 **착용감 불편**으로 낮은 점수 기록
- 정장류는 **핏 불만** 및 **사이즈 문제**로 부정적인 평가 다수 발생

4) **분석 결과**
- **슈트/블레이저, 슬랙스**: 핏 불만 및 사이즈 문제 발생
- **신발류**: 사이즈 미스매치 및 착용감 불편으로 부정적 평가 다수
- **반팔**: 소재 문제 및 디자인 불만으로 감성 점수가 낮음

5) **마케팅 인사이트**
- 정확한 **사이즈 가이드** 및 **핏 보장 교환/환불 정책** 도입합니다.
- 체형별 핏 추천 시스템 구축하여 사이즈 문제를 해결합니다.
- 신발 사이즈 추천 시스템 구축하고 **착용 후기**를 제공합니다.
- **리얼핏 리뷰 콘텐츠를 강화**하여 신뢰도를 개선합니다.
- 소재 정보 및 원단 특성을 상세 설명에 추가합니다.
-**디자인을 다양화**하고 고객 피드백을 반영한 **리뉴얼 제품** 출시

**상/하위 10개의 소분류 리뷰 키워드 분석**
![image](https://github.com/user-attachments/assets/7096955a-f9cd-40b3-afb8-d18191547512)

1) 시각화 자료:
- **소분류별 감성 점수 상/하위 10개의 리뷰 키워드 워드클라우드**
- **긍정 키워드**와 **부정 키워드**를 형태소 분석 후 빈도수를 바탕으로 시각화
- **긍정 리뷰 키워드**: '보기', '많이', '입으려고', '가볍고', '빠르고', '예뻐서', '사이즈도', '배송', '디자인', '무난하게' 등
- **부정 리뷰 키워드**: '사이즈', '많이', '살짝', '입으면', '가격에', '있어서', '크게', '불편', '신고' 등

2) **감성 점수가 높은 상위 10개 소분류의 키워드 분석 결과**
- **'보기', '예뻐서', '디자인'**: 디자인적 만족이 긍정적인 감성 점수로 이어짐
- **'가볍고'**: 편안한 착용감에 대한 긍정적 평가
- **'사이즈도', '입으려고'**: 사이즈가 예상과 일치하여 만족도 상승
- **'배송', '빠르고'**: 빠른 배송에 대한 만족도 높음
-**'무난하게'**: 활용도가 높은 베이직 제품에 대한 만족도

**분석 결론 및 인사이트**:
- 디자인 만족도가 높은 제품군에서 긍정적인 감성 점수 기록
  - **디자인 및 활용도**를 광고 메시지에 반영하여 **고객 경험도 향상**
  - **스타일링 콘텐츠 제작**을 통해 **다양한 연출법** 제시
- **편안한 착용감**과 **사이즈 만족도**가 긍정적 평가로 이어짐
  - 착용감을 강조한 **제품 상세 설명 및 리얼핏 리뷰** 노출
  - 정확한 **사이즈 가이드 제공** 및 **핏 보장 교환/환불 정책** 도입
- 빠른 배송과 활용도 높은 제품에 대한 만족도가 높음
  - **빠른 배송을 강조**한 프로모션 진행
  - 다양한 스타일링이 가능한 **베이직 제품**에 대한 광고 강화
   
3) **감성 점수가 낮은 하위 10개 소분류의 키워드 분석 결과**
- **'사이즈', '많이', '크게'**: 사이즈 불만 및 핏 문제로 부정적 평가
- **'가격에'**: 가격 대비 품질 불만
- **'불편', '신고'**: 착용감 불편으로 부정적 평가

**분석 결론 및 인사이트**:
- 사이즈 불만과 핏 문제가 부정적 평가로 이어짐
  - **체형별 사이즈 추천 시스템 구축** 및 **리얼핏 리뷰** 제공
  - 핏 보장 교환/환불 정책 및 **사이즈 상담 서비스** 도입
- 가격 대비 품질 불만 해소
  - 가격대에 맞는 품질을 제공하거나 **가성비 캠페인** 강화
- 착용감 불만 개선
  - **착용감 상세 설명** 및 고객 피드백 반영한 **리뉴얼 제품** 출시

**3. 특정 체형에 따라 감성점수 차이가 존재할 것이다.**
- 성별에 따른 감성점수 평균 / 체형에 따른 감성점수 관계를 각각 비교하여 시각화
1) 기초 통계 분석
- 성별, 체형별로 감성 점수 평균을 구해본 결과 대부분 4.5의 비슷한 점수 평균을 보임

2) 비모수 검정 진행
- 성별, 체형 모두 정규성을 따르지 않아 비모수 검정을 진행하였으며, 그 결과 **성별의 경우 유의미한 차이**를 보이나 **체형의 경우 유의미한 결과를 갖지 않음**

3) 성별에 따른 감성점수 분포
![image](https://github.com/user-attachments/assets/67e1efaf-431b-46f8-97a5-91aff9c66f30)

- 감성점수 차이
  - 남성과 여성 감성점수 분포는 대체적으로 유사
  - 하단의 작은 분포로 보아 일부 낮은 점수도 존재하나 전체적으로 긍정적인 리뷰 우세

**분석결과 및 인사이트**
- 성별에 따른 감성점수 차이가 크지 않으므로 성별 맞춤 마케팅보단 제품 특성 및 착용감을 강조하는 전략이 더 효과적일 가능성이 큽니다.
- 따라서 성별보단 제품 카테고리 중심으로 세분화시킨 마케팅 전략이 필요합니다.

**4. 특정 브랜드는 타 브랜드에 비해 감성 점수가 높을 것이다.**
- 브랜드별 감성점수 평균을 비교하고, 긍/부정 리뷰 비율을 비교

1) 기초 통계 분석
- 브랜드별 평균 감성점수
   - 스파오: 4.54
   - 탑텐: 4.54
   - 에잇세컨즈: 4.58
   - 무신사 스탠다드: 4.54
- 브랜드별 긍/부정 비율
  - 스파오: 긍정 - 91.2% / 부정 - 8.8%
  - 탑텐: 긍정 - 91.1% / 부정 - 8.9%
  - 에잇세컨즈: 긍정 - 89.7% / 부정 - 10.3%
  - 무신사 스탠다드: 긍정 - 88.7% / 부정 - 11.3%
* 브랜드별 평균 감성 점수의 차이는 크게 없는 편이며, 긍/부정 비율을 살펴보았을 때 스파오의 긍정비율이 가장 높고 무신사 스탠다드의 비율이 가장 낮음

2) Kruskal-Wallis Test
- 네 브랜드 모두 정규성을 띄지 않으므로 비모수 검정을 진행하였고 그 결과 브랜드별 유의미한 감성점수 차이가 있음이 판명

3) 브랜드별 긍/부정 리뷰 갯수
![image](https://github.com/user-attachments/assets/1324fa7e-2f28-4f8c-a07d-f04d5bbc2326)

**분석결과**
- 네 브랜드 제품들을 최대한 동일한 갯수로 수집하여 해당 제품들에 대한 리뷰수를 분석해보았을 때 무신사 스탠다드의 리뷰가 압도적으로 많음을 알 수 있었습니다.
- 탑텐의 경우 리뷰 갯수가 가장 적고 스파오는 비교적 높은 긍정 비율 및 리뷰 갯수를 보이는 것을 확인하였습니다.
- 스파오의 이커머스 내 리뷰수를 좀 더 늘리기 위한 방안을 찾아 전략을 도출해야 할 필요성이 있습니다.

**SPAO 마케팅 인사이트**
A. 긍정 리뷰 활용
- 고객 만족도 1위 브랜드 포지셔닝
  - 긍정 리뷰 비율이 가장 높은 점을 이용하여 고객 만족도가 가장 높은 SPA 브랜드라는 포지션을 강조합니다.
  - 공식 홈페이지, 무신사, 네이버 스토어 등에 '베스트 리뷰 선정' 섹션을 추가해 실구매자의 긍정 평가를 강조하는 전략을 이용합니다.
- 소비자 리뷰 이용 퍼포먼스 마케팅
  - 스토어 혹은 SNS 등에서 리뷰를 강조한 컨텐츠를 기획하여 고객 만족도가 높은 인기템의 카피를 이용해 홍보를 진행합니다.
  - 주요 플랫폼 내 '리뷰 기반 인기 제품' 등의 섹션을 운영합니다.
- 고객 리뷰를 활용한 리타겟팅 광고
  - 긍정 리뷰가 많은 제품을 기반으로 DA 광고를 진행합니다.

B. 부정 리뷰 개선
- 부정 리뷰 맞춤 개선 전략
  - 주요 불만사항을 파악하여 해결책을 제시합니다.
  - 상세페이지에 해당 각 체형별 베스트 사이즈 정보를 제공합니다.
- 반품, 교환 정책을 개선 혹은 고객 만족 프로그램 운영
  - 특정 기간 무료 반품 프로모션을 운영합니다.

C. 신규 고객 유입
- 리뷰 인증 이벤트 진행
  - 리뷰 고객 대상 할인 쿠폰 증정 이벤트
- 타깃 세분화
  - Z세대: 트렌디 패션 아이템 및 콜라보 제품 중심 마케팅
  - 밀레니얼: 기본 아이템 및 가성비 강조
  - 시즌별 리마케팅: 시즌별로 긍정리뷰가 많은 재고 확보 후 할인 프로모션 진행

### 5.3 고객 맞춤 제품 추천 시스템

#### 5.3.1 모델 선택
- 목표: 사용자 정보를 입력받아 원하는 대분류의 제품으로 사용자에게 적합한 제품 추천
- 추천에 이용할 정보(독립변수): 성별(범주형), 키(연속형), 몸무게(연속형), 대분류(범주형)
- 예측을 진행할 정보(종속변수): 매출량(제품별 리뷰 갯수와 평점을 가지고 추론한 **예측 매출량**)
- 평가를 진행할 모델 선택: 선형회귀, 랜덤포레스트, XGBoost, MLP 회귀로 테스트를 진행

#### 5.3.2 데이터 준비 및 인코딩
**1) 데이터 준비 및 정제**
   - 현재 제품리스트 파일에만 존재하는 매출량 데이터를 감성분석을 마친 사용자 리뷰 데이터에 링크
   - 독립변수, 종속변수를 제외한 필요없는 데이터는 삭제
   - 해당 데이터에 남은 열: '대분류', '성별', '키', '몸무게', '매출량'
**2) 인코딩 및 스케일링**
- 머신러닝 진행을 위해 데이터 인코딩 진행
   - 성별: 레이블 인코딩을 진행하여 남성의 경우 0, 여성의 경우 1로 인코딩
   - 대분류: 레이블, 타깃 인코딩을 진행할 시 가중치가 발생하여 학습에 방해가 될 수 있음 따라서 11개의 대분류를 원-핫 인코딩으로 진행
   - 키, 몸무게: 키와 몸무게의 경우 연속형 데이터이므로 원활한 머신러닝을 위해 스케일링을 진행

#### 5.3.3 데이터 분리
- 레이블 예측을 위해 훈련용 데이터셋과 현재 가진 매출량(정답)데이터셋을 분리하여 모델 학습 진행

#### 5.3.4 모델 학습, 예측, 평가
먼저 선형데이터와 비선형데이터에 특화되어있는 4개의 모델로 회귀를 진행해본 결과는 다음과 같습니다.
- Linear Regression - RMSE: 1.29, R²: 0.0487
- Random Forest - RMSE: 1.38, R²: -0.0784
- XGBoost - RMSE: 1.34, R²: -0.0162
- MLP Regressor - RMSE: 1.27, R²: 0.0750
  - 매출량에 이상치로 인해 모델 성능이 굉장히 낮게 나오게 되어 종속 변수 스케일링을 새로 진행하였으며, 값에 0을 포함하는 경우가 있어 **제곱근 변환**을 진행하였습니다.
- Linear Regression - RMSE: 0.41, R²: 0.0682
- Random Forest - RMSE: 0.43, R²: -0.0271
- XGBoost - RMSE: 0.41, R²: 0.0664
- MLP Regressor - RMSE: 0.41, R²: 0.0862
   - 제곱근 변환 이후 다시 진행하여 RMSE 개선이 확인되었으나 더 높은 성능의 모델을 찾기 위해 하이퍼 파라미터 튜닝 후 성능을 측정하고자 합니다.
   - 
#### 5.3.5 하이퍼 파라미터 튜닝
- 하이퍼 파라미터 튜닝을 진행할 때 추가로 비선형 데이터에 적합한 **그라디언트 부스팅 회귀(Gradient Boosting Regressor)**를 진행하였고, 교차 검증 결과 해당 모델이 가장 성능이 좋은 것으로 판단되었습니다.
   - 해당 모델로 진행해본 결과 **R²: 0.0990, MAE: 0.2415, RMSE: 0.4069**라는 성능을 달성하였습니다.

#### 5.3.6 예측 결과
- 이번 결과는 기본적인 변수만으로 매출량 예측이 가능함을 확인하였으며, 이후 추가적인 변수 탐색, 데이터 정제, 모델 최적화를 통해 정교한 예측이 가능할 것이라 기대됩니다.
**결과물 출력**
![image](https://github.com/user-attachments/assets/8811f80a-a9c6-41fb-bdff-76c828556f7a)
- 고객이 선택한 대분류, 성별, 키, 몸무게, 브랜드를 입력하면 나오는 결과값입니다.

## 6. 응용 및 배포: 고객 맞춤형 제품 추천 시스템
- 해당 알고리즘을 이용해 고객 맞춤형 제품 시스템을 실제로 응용하여 배포하고자 합니다.

### 6.1 개요 및 알고리즘
#### 고객 맞춤형 제품 추천시스템 개발 배경 및 목적
온라인 이커머스 플랫폼에서 발생하는 부정적인 리뷰는 주로 제품의 핏과 착용 사이즈가 맞지 않았기 때문에 발생하였습니다.<br>
따라서 고객의 불만 해소 및 이커머스 플랫폼 내 브랜드 경쟁력을 강화하기 위해 **머신러닝을 이용한 고객 맞춤형 제품 추천 시스템**을 개발하고 배포하게 되었습니다.<br>
해당 시스템은 **고객 성별, 체형, 카테고리, 선호 브랜드**를 바탕으로 개인 맞춤형 제품을 추천하며
**자동화된 답변 시스템**을 통해 고객 개개인에게 최적화된 제품 추천을 **실시간으로 제공**합니다.

### 6.2 선택 플랫폼
고객 맞춤형 경험 제공을 목표로 해당 시스템을 **Wix**와 **Zapier**를 활용한 자동화 시스템으로 구현하여 배포하였습니다.

#### 플랫폼 구성 요소:
1. **Wix site**
  - 고객 정보 입력 Form을 통해 **성별, 카테고리, 체형, 브랜드 등의 정보를 입력
  - Form 양식 제출 시 고객 정보 실시간 수집
2.**Zapier**
  - Wix Form에 입력된 고객 정보를 Zapier를 통해 자동화 시스템으로 연결
  - Zapier 트리거 설정
    - Wix: 각 Form 필드에 대응하는 열 이름 저장 및 자동 연결
    - Google Spread Sheet: Wix에서 수집된 정보 구글 스프레드 시트에 자동 저장
3. **Google Spread Sheet -> 로컬 컴퓨터**
  - 스프레드 시트에 저장된 정보를 로컬 컴퓨터 파일로 저장
  - 새 데이터가 들어올 때마다 저장 및 업데이트 진행
4. **Machine Learning Model**
  - best_pipeline_model:
    - 사전 학습된 머신러닝 모델을 통해 입력값에 따른 고객 맞춤형 제품 추천
    - 예측된 제품 프레임 내 제품명 추출
    - 추천 제품명 기반 제품 페이지 링크 생성
5. **Selenium(웹크롤링)**
  - 웹크롤링을 통해 추천 시스템 페이지 접속 및 관리자 로그인
  - 고객 성함, 제품 링크가 포함된 댓글 자동 생성
  - 자동 게시 후 피드백 제공

### 6.3 UI
- Wix site Form UI 사용, 쉽게 정보 입력
- 추천 제품 링크 댓글 형태로 제공

### 6.4 테스트 진행 결과 (추후 사진 첨부)
#### 6.4.1 정보 입력
- Wix 추천 시스템 페이지를 통해 고객 정보를 직접 입력하고 제출합니다.
<img width="261" alt="image" src="https://github.com/user-attachments/assets/04091ffd-7ff7-43e2-b517-9bf02a3ee429" />
<img width="408" alt="image" src="https://github.com/user-attachments/assets/088af7e6-0d0c-45cf-a1f0-54607a9faede" />

- 제출이 진행되면 Zapier를 통해 자동화 시스템에 의하여 구글 스프레드로 정보가 자동 저장됩니다.
<img width="317" alt="image" src="https://github.com/user-attachments/assets/1729c454-7480-4192-ad25-194fbf623212" />

- 저장된 파일 정보를 컴퓨터 로컬 파일로 저장하여 웹크롤링을 통해 추천 시스템 페이지 댓글로 자동 답변이 진행됩니다.
<img width="470" alt="image" src="https://github.com/user-attachments/assets/bec621bc-6a00-4dc3-8724-ff71de8fb90e" />

- 답변에 달린 링크를 클릭하면 원하는 카테고리의 상품이 추천됩니다.
<img width="952" alt="image" src="https://github.com/user-attachments/assets/be0d155d-99c4-4352-a620-6feace5207d6" />

---

## 7. 프로젝트 마무리
