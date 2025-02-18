# DATA ANALYTICS 개인 프로젝트
---
## 1. 프로젝트 개요

### 1.1 프로젝트명:
2025년 SPAO 브랜드 충성 고객 확대 및 매출 증대 도모

### 1.2 프로젝트 배경
최근 한국 경제는 저성장 기조가 지속되면서 **소비자의 소비 행태에도 변화**가 나타나고 있습니다. 오픈서베이 설문조사에 따르면 소비자들은 ‘가성비’와 ‘품질’을 더욱 중요하게 고려하며, 고가 브랜드 제품과 극단적으로 저렴한 제품보다는 **합리적인 가격과 적절한 품질**을 제공하는 제품을 선호하는 경향을 보이고 있습니다.

SPA 브랜드는 이러한 소비 트렌드에 부합하는 대표적인 유통 모델입니다. **SPA(전문점형 의류 제조 유통) 브랜드는 기획, 생산, 유통의 전 과정을 직접 관리하여 효율적인 운영이 가능하며, 신속한 시장 대응력을 갖추고 있습니다.** 이에 따라 소비자의 니즈를 빠르게 반영하고, 트렌드 변화에 유연하게 대응할 수 있어 지속적인 성장세를 이어가고 있습니다.

또한, 오픈서베이 ‘MZ세대 패션 앱 트렌드 리포트 2024’에 따르면 만 15~39세 소비자 중 66.9%가 온라인을 통해 패션 상품을 구매하고 있으며, 패션 플랫폼 선호도 조사에서도 무신사가 50%로 압도적인 점유율을 차지하고 있었는데 이는 패션 상품 구매에 있어 **온라인 플랫폼의 영향력이 매우 크고**, **온라인 쇼핑의 비중이 지속적으로 증가하고 있음**을 시사합니다.

기존 SPA 브랜드는 전통적으로 오프라인 매장 중심의 판매 전략을 유지해왔으나, 점차 온라인 플랫폼을 활용한 마케팅과 판매 전략이 필수적인 요소로 자리 잡고 있으며 이커머스 패션 플랫폼에도 계속해서 입점하고 있는 상황입니다.
이에 국내 상위 SPA 브랜드 중 하나인 **SPAO의 경쟁력을 강화**하기 위해 온라인 플랫폼에서의 **소비자 리뷰 데이터를 분석**하고, 무신사 등의 주요 이커머스 플랫폼을 활용한 **2025년 마케팅 전략을 수립**하고자 합니다. 

### 1.3 프로젝트 목표
온라인 이커머스 플랫폼을 통한 SPAO 브랜드 충성 고객 범위 확대 및 매출 증진 도모

### 1.4 사용환경, 패키지, 툴, 응용 프로그램
- 프로그래밍 언어: Python3
- 데이터 수집: Selenium, BeautifulSoup4
- 데이터 분석 및 전처리: Pandas, Numpy, Scipy, Matplotlib, Seaborn
- 머신러닝: Scikit-learn
- 머신러닝 알고리즘:
- 한글 처리 형태소 패키지: konopy-Okt
- 딥러닝: Tensorflow, llama3
---
## 2. 데이터 수집

### 2.1 오픈 데이터 다운로드

1) 오픈서베이
   - MZ세대 패션 앱 트렌드 리포트 2024
     [바로가기](https://blog.opensurvey.co.kr/trendreport/mz-fashion-2024/)
   - 2024 소비자 소비 트렌드
     [바로가기](https://blog.opensurvey.co.kr/article/webinar-eatbuyplay-2024-5-buy/)
2) Korea Fashion Big Data
   - 2024 한국 패션산업 빅데이터 트렌드(한국 패션 시장규모 전망)

### 2.2 웹크롤링을 통한 데이터 수집

1) 무신사[이커머스 플랫폼]
   - 각 브랜드별 [|'브랜드'|'대분류'|'소분류'|'제품명'|'제품ID|'제품가격'|'찜 수'|'평점'|'리뷰 갯수'|] 파일
   - 각 브랜드별  [|'브랜드'|'대분류'|'소분류'|'제품명'|'제품ID'|'사용자ID'|'사용자별점'|'사용자리뷰'|'성별'|'키'|'몸무게'] 파일

### 2.3 설문조사

1) 연령대별, 성별별 옷 구매 고려 요소 설문조사 데이터
* 연령대/성별/직업군별 구매 고려 요소
![image](https://github.com/user-attachments/assets/1d8e5f68-9b34-4c44-9f74-5d2c1c938119)
![image](https://github.com/user-attachments/assets/f739b938-eff3-4aaf-a2b5-f62afc97f21a)
![image](https://github.com/user-attachments/assets/dc668d85-8d71-4d8b-b462-243abf07be35)
- 모든 연령대, 성별, 직업군에서 가장 많이 고려하는 요소는 '디자인' 입니다.
  - 남성은 디자인, 품질, 가격 순으로 고려하고 여성의 경우 디자인, 가격, 품질 순으로 고려합니다.
* 연령대별 옷 구매수단 선호도
![image](https://github.com/user-attachments/assets/69581fed-e150-44c7-9753-1327969591c7)
- 2/30대의 경우 의류 전용 온라인 쇼핑몰 이용률이 높습니다.
- 40대의 경우 오프라인 혹은 11번가와 같은 온라인 쇼핑몰 이용 비율이 높고, 50대 이상의 경우 압도적으로 오프라인 매장을 이용합니다.
*구매수단 별 SPA 브랜드 선호도
![image](https://github.com/user-attachments/assets/799ed0b7-49d4-4860-8868-b7f2a1160cce)
- 의류전용 온라인 쇼핑몰을 이용하는 사용자의 경우 무신사 스탠다드의 선호도가 압도적으로 높고, SPAO 브랜드의 경우 오프라인 매장 이용자가 많습니다.

**SPAO브랜드 마케팅 인사이트**
**1. SPAO의 타깃 연령층에 맞춘 제품 기획**
- 모든 연령대 및 직업군에서 디자인을 가장 중요하게 고려하는 것으로 나타났습니다.
  따라서, **패션 트렌드 리서치 및 빠른 디자인 적용 전략**을 통해 트렌디한 디자인을 지속적으로 반영해야합니다.
  SNS 및 인플루언서를 활용한 스타일링 제안 콘텐츠를 적극 활용하여 해당 요소를 강조해야합니다.
**2. 연령대별 가격, 품질 고려 비율을 고려**
- 2030의 경우 **가성비를 강조한 제품라인을 진행**하는 것이 좋을 것이라 판단됩니다.
- 40대의 경우 디자인 뿐 아니라 가격/품질도 무시할 수 없으므로 **고품질의 기본 아이템 라인을 강화하고 신뢰 높은 원단을 강조**해야합니다.
**3. 쇼핑 채널 분석에 따른 전략**
- 2030의 경우 의류전용 온라인 쇼핑몰을 선호하기 때문에 **무신사 내 SPAO 브랜드 페이지를 최적화**하고, **쿠폰을 제공**하거나 **온라인 전용 제품**을 출시하여 해당 채널에서의 경쟁력을 강화합니다.
- 40대의 경우 일반 온라인 쇼핑몰을 선호하므로 '네이버 스마트스토어' 및 11번가 등의 쇼핑몰에서 **SEO 개선을 통해 검색을 최적화**하고 **오프라인 할인 행사와 연계된 프로모션**을 진행합니다.
- 50대의 경우 오프라인 구매 비율이 압도적이므로 백화점, 대형마트 내 **오프라인 매장을 확대하고 체험형 매장 운영을 고려**하여 구매율을 향상 시킵니다.
**4. 브랜드 인지도 향상**
- 오프라인 매장 이용자 비율이 높은 것을 이용하여 **오프라인 매장 내 멤버십 혜택 강화**로 충성고객을 유도합니다.
---

**데이터 관계 다이어그램**
![image](https://github.com/user-attachments/assets/ef3c3d54-c1ea-42b0-9d75-68aab0f785c6)

## 3. 데이터 전처리

### 3.1 데이터 병합
- 무신사제품리스트 파일에 카테고리 추가

### 3.2. 데이터 클렌징
- 결측치 처리 및 순서 변경, 열 추가

#### 3.2.1 무신사제품리스트.csv
- 수집한 카테고리 파일과 제품명에 맞게 병합
- 카테고리 오류, 카테고리 없음, 디지털/라이프 행 삭제 및 스포츠/레저 카테고리 순서 변경

#### 3.2.2 리뷰데이터 정제
- 무신사)SPAO_reviews 정제전.csv
- 무신사)TOPTEN_reviews 정제전.csv
- 무신사)8seconds_reviews 정제전.csv
- 무신사)Mutendard_reviews 정제전.csv
<br>
- 4개 정제전 리뷰 데이터 병합
- 카테고리 오류, 카테고리 없음, 디지털/라이프 행 제거 및 스포츠/레저 순서 변경
- 제품ID열, 브랜드열 추가
- 열 이름 및 순서 변경

### 3.3 데이터 변환 및 정규화

#### 3.3.1 무신사_제품리스트_1차정제완료.csv
- 찜수, 리뷰갯수 열 만, 천 숫자로 변경 후 정수형으로 변환
- **찜수, 리뷰갯수를 이용해 매출량열 추가 [(제품당 찜수+리뷰갯수)/(브랜드 전체 찜수+리뷰갯수)*100]**
- **가격열 범주화('저가', '중저가', '고가', '럭셔리')**
- 3만 원 이하 / 3만 원 초과 - 6만 원 이하 / 6만 원 초과 - 9만 원 이하 / 9만원 초과

##### **Summary**
- 리뷰 수에 가중치를 두고 찜수와 더한 값의 비율로 매출량 열 생성
- 가격 열을 참고하여 가격 범주 열 추가 <br>
|저가|중저가|고가|럭셔리|

#### 3.2.3 **추가 데이터 정제**
- 사용자 리뷰 데이터에서 **성별, 키, 몸무게 결측치 대체** 및 **데이터 타입 정수형 변환**
- 사용자가 성별, 키, 몸무게의 정보를 입력하지 않아 제품 사이즈 데이터 혹은 색상 데이터가 들어온 경우 결측치로 간주
     - 이용 데이터 :
     - 무신사리뷰_SPAO_1차정제.csv
     - 무신사리뷰_TOPTEN_1차정제.csv
     - 무신사리뷰_8Seconds_1차정제.csv
     - 무신사리뷰_Mutendard_1차정제.csv
###### 1. 성별 열 정제
- '남성' 혹은 '여성'이 아닌 데이터 성별 정제
- 사용자 ID, 제품명, 사용자리뷰, 키를 조합하여 성별을 추측
- 사용자 ID가 '남성향'ID인지 '여성향'ID인지 판단하여 점수 부여
- 제품명 분석을 통해 남성제품, 여성 제품을 판단하고 중성적인 제품의 경우 0.5점 부여
- 사용자 리뷰를 분석하여 성별 판별 후 동일한 형태로 점수 부여
- 한국 남성 키, 여성 평균 키를 활용하여 키에 따라 0과 1 사이의 점수를 부여
- 최종 합을 4로 나누고 평균 점수가 0에 가까우면 여성, 1에 가까우면 남성으로 추측하여 성별 열을 대체
###### 2. 키 열 정제
- 대체된 성별에 대해 정상인 데이터 평균 값으로 대체
###### 3. 몸무게 열 정제
- 전체 중앙값을 사용하여 결측치, 30 이하의 몸무게 행 대체
###### 4. 키와 몸무게 열을 이용해 신체범주화(체형) 열 생성
- 키와 몸무게 열을 정수형 데이터로 변경
- **키와 몸무게, 성별을 참고하여 '장신-슬림형', '단신-슬림형', '장신-볼륨형', '단신-볼륨형' 총 4가지의 범주로 체형 열 생성**
- 성별 데이터가 남성일 경우와 여성일 경우를 각각 나누어서 평균 키 이상일 때 평균 몸무게 이상일 경우 '장신-볼륨형' / 평균 키 이상, 평균 몸무게 미만일 경우 '장신-슬림형', 평균 키 미만 평균 몸무게 이상일 경우 '단신-볼륨형', 모두 미만일 경우 '단신-슬림형'으로 나누어 체형 데이터를 생성

---
## 4. 통계학적 분석 및 시각화

### 4.1 탐색적 데이터 분석(EDA) 가설 설정
#### 4.1.1 무신사_제품리스트 데이터 기반 가설
- 해당 데이터의 열 구성 <br>
**|브랜드|대분류|소분류|제품명|제품ID|제품가격|찜수|평점|리뷰갯수|매출량|가격 범주|** <br>

**1. 가설 1. 가격이 낮은 제품일수록 매출량이 높을 것이다.**
- 가격 범주열을 이용하여 각 가격대 별 매출량을 비교하여 상관관계 분석 진행

**2. 가설 2. 4개의 브랜드 중 특정 브랜드 제품이 타 브랜드보다 매출량이 높을 것이다.**
- 브랜드별 매출량 평균을 계산하여 순위를 비교

**3. 가설 3. 특정 카테고리에서 높은 매출량을 보일 것이다.**
- 각 카테고리별 매출량 평균을 비교하여 인기있는 카테고리를 식별

#### 4.1.2 무신사 사용자리뷰 데이터 기반 가설 설정
- 사용자 리뷰 데이터 열 구성<br>
**|브랜드|대분류|소분류|제품명|제품ID|사용자ID|사용자별점|사용자리뷰|성별|키|몸무게|체형| <br>**

**A. 성별 데이터 구분(대분류)**

|  | 표본수 |
|-|-|
|남성|30,239명|
|여성|15,995명|

![image](https://github.com/user-attachments/assets/060aba82-15bf-4014-a222-e4cdc2b7734a)

**1. 가설 4. 남성 소비자와 여성 소비자는 선호하는 브랜드가 다르다.**
- 각 성별군이 브랜드별 예상 매출량에 통계적 차이를 보이는지 분석 및 검증

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

**2. 가설 5. 특정 성별과 신체조건을 가진 사람은 특정 브랜드의 제품을 선호할 것이다.**
- 성별과 체형 열을 이용해 브랜드에 대한 사용자 별점 평균을 비교

**C. 체형별 표본 구분**
|체형| 표본수 |
|-|-|
|체형A|19,754명|
|체형B|16,990명|
|체형C|5,474명|
|체형D|4,015명|

![image](https://github.com/user-attachments/assets/cc9d24c4-dca7-410f-bc7b-3bf078503af1)

**3. 가설 6. 체형에 따라 선호하는 특정 카테고리와 재구매 의향이 다를 것이다.**
- 체형별 각 카테고리(대분류)에 대한 리뷰수, 평균 사용자 별점 비교
- 소분류에 대한 선호도 분석
- 체형별 반복 리뷰 갯수 분석 및 재구매의향 파악

---
## 머신러닝 진행 후 분석 요망

**긍정적인 리뷰가 많은 브랜드가 높은 매출량을 보일 것이다.**
- 리뷰 감성 분석 진행을 통해 긍/부정 열을 생성한 후 브랜드별 긍/부정 비율과 매출량 비교

**가격대가 낮을수록 긍정 비율이 더 높을 것이다.**
- 가격대와 긍/부정 열과의 상관관계 분석을 진행한 후 긍/부정 비율 평균과 가격대 비교
---

### 4.2 분석 시각화
- 시각화 도구: Pandas, Numpy, Matplotlib, Seaborn

#### 4.2.1 가설1 검증 진행
- 귀무가설: 가격과 매출량은 유의미한 상관관계를 가지지 않을 것이다.
1) 기초 통계 분석
- 제품 가격 평균: 약 29,733원
- 매출량 평균: 약 0.313(추정 매출량)
- 최소 가격: 3,900원 / 최대 가격: 161,390원
- 최소 매출량: 0.0 / 최대 매출량 15.79

2) 정규성 검증 진행
- 제품 가격과 매출량 정규성 검증결과 p-value값 0.05 미만으로 비모수 검증인 Spearman 상관관계 분석 진행

3) 상관관계 분석 결과
- p-value값이 0.05 미만으로 귀무가설 기각
- 스피어만 상관계수: 0.135, 약한 양의 상관관계

4) 가격과 매출량의 관계
<img width="386" alt="image" src="https://github.com/user-attachments/assets/877fdc59-cb24-491a-9250-148f1fe0f958" />

5) 가설 1 결론
- 제품 가격과 매출량은 약한 상관관계를 보입니다.
- 가설과 동일하게 가격이 낮을수록 매출량이 높은 경향을 보이지만 강한 연관성을 띄지는 않습니다.

##### **마케팅 인사이트**
- SPAO의 중저가 가격 전략은 매출 증가에 유리할 수 있지만 가격을 낮추는 것이 매출 상승을 보장하진 않습니다.
- **합리적인 가격**과 **제품 경쟁력 강화** 전략이 필요합니다.
  - 핵심 전략: '가성비' 전략과 더불어 '고품질'을 강조한 광고 캠페인 진행

#### 4.2.2 가설2 검증 진행
- 귀무가설: 브랜드별 매출량의 차이가 크게 다르지 않을 것이다.
1) 기초통계분석
- 평균 매출량 1위 탑텐(0.415)
- 최대 매출량 1위 스파오(15.79)

2) 정규성 검증
- 네 브랜드 모두 p-value값이 0.05 미만으로 정규성을 띄지 않아 비모수 검증인 스피어만 상관관계 분석을 진행

3) 상관관계 분석 결과
- p값이 0.05 미만이므로 귀무가설 기각
- 브랜드와 매출량간의 유의미한 상관관계가 있음
- 스피어만 상관계수: 0.269, 약한 양의 상관관계

4) 브랜드별 평균 매출량
<img width="416" alt="image" src="https://github.com/user-attachments/assets/3c4a2639-c1db-4da9-90e1-2e90930580ca" />

5) 가설2 결론
- 브랜드별로 약하게 매출량 차이가 존재합니다.
- 탑텐이 가장 높은 평균 매출량을 기록하였고, 스파오가 최대 매출량을 보유하고 있습니다.

##### **마케팅 인사이트**
- SPAO는 일부 제품에서 높은 판매량을 기록하였으나 전체 평균 매출량에서는 **경쟁 브랜드(탑텐)** 에 비해 **낮은 매출량**을 기록하였습니다.
- 핵심 전략:
  - **대량 판매 제품을 확인**하여 집중적으로 마케팅 진행
  - 현재 입점한 무신사, ABLY 뿐 아니라 더욱 다양한 이커머스 플랫폼 입점 필요
  - 탑텐과 차별화된 감성 강조 --> 디자인, 지속적인 콜라보 진행 등

#### 4.2.3 가설3 검증 진행
- 귀무가설: 카테고리별로 매출량의 차이가 다르지 않을 것이다.
1) 기초통계분석
- 특정 카테고리에서 높은 매출량을 보이는 것을 확인
  - 1위 아우터: 평균 0.557 / 최대 15.79
  - 2위 상의: 평균 0.363 / 최대 14.17
  - 3위 패션소품: 평균 0.358 / 최대 2.12
  - 4위 바지: 평균 0.194 / 최대 2.27
  - 5위 원피스/스커트: 평균 0.189 / 최대 0.95

2) 정규성 검증
- 제품 수 3개 이상인 카테고리를 필터링한 후 정규성을 진행한 결과 일부 제외 대부분의 카테고리가 정규성을 따르지 않아 스피어만 상관관계 분석 진행

3) 상관관계 분석 결과
- p값이 0.05 미만이므로 귀무가설 기각
- 카테고리 별 매출량의 차이가 유의미하게 존재
- 스피어만 상관계수: 0.106, 약한 상관관계

4) 카테고리별 평균 매출량
<img width="415" alt="image" src="https://github.com/user-attachments/assets/4fa0ed83-b7b5-4fe6-afeb-63787b7accce" />

5) 가설3 결론
- **아우터, 상의, 바지**의 카테고리에서 평균 매출량이 타 카테고리에 비해 상대적으로 높은 것을 알 수 있습니다.

##### **마케팅 인사이트**
- SPAO의 아우터, 상의 카테고리 매출 비중을 확대해야 합니다.
- 핵심 전략:
  - 겨울 시즌 아우터 집중 프로모션(패딩, 플리스 등)을 통해 **아우터 매출 증대** 도모
  - 무신사 내 **F/W 시즌 아우터 컬렉션 기획전** 참여
  - **상의+아우터 세트 할인 프로모션** 진행 혹은 **패션소품 콜라보 진행**을 통해 아우터 혹은 상의에 세트 상품 구성
  - 세트 상품 기획 프로모션 진행 시 **크리에이터와의 협업**을 통해 차별화된 마케팅 전략으로 활용

#### 4.2.4 가설4 검증 진행
- 귀무가설: 성별별 리뷰 갯수와 매출량은 직접적인 연관이 없을 것이다.
1) 기초통계분석
- 특정 카테고리에서 높은 매출량을 보이는 것을 확인
   - 리뷰 갯수: 극단적인 값이 존재할 가능성이 있음
   - 매출량: 0인 데이터도 존재

2) 정규성 검증
- 리뷰데이터와 제품리스트 데이터의 연속성 데이터 열을 이용해 정규성 검증을 진행해본 결과 모든 열의 p-value값이 0.05미만으로 정규성을 따르지 않고 따라서 스피어만 상관관계 분석 진행

3) 상관관계 분석 결과
- 스피어만 상관계수: -0.8
- p-value: 0.2
- 성별 리뷰 갯수와 평균 매출량은 **음의 상관관계**를 보이고 있지만 p값이 0.05 이상으로 유의미한 상관관계를 보이지 않음
- 따라서 특정 성별이 특정 브랜드를 선호할 수는 있으나 평균 매출량과 직접적인 연관을 보이지는 않음.

4) 브랜드별 성별 리뷰 수
![image](https://github.com/user-attachments/assets/3de1c9c6-af99-497f-852c-81d6a5b0f87c)

5) 브랜드별 매출량(성별 비율)
![image](https://github.com/user-attachments/assets/c7722b0c-fe3b-440e-8879-bd2acdf002e7)

6) 브랜드별 평균 매출량
![image](https://github.com/user-attachments/assets/8dd65b87-a60e-4c8e-8be8-85a83cf78929)

7) 가설4 결론
- 특정 성별이 직접적인 매출에 영향을 주진 않으나 **각 브랜드별로 성별 간 리뷰 갯수나 매출 비율에는 차이를 보이는 것**이 확인되었습니다.
- 브랜드별 성별 리뷰가 다른 것은 **타깃 소비층이 다를 가능성을 의미**하며 남성, 여성 소비자 기여도가 크게 차이나는 브랜드가 존재하므로 **성별별 매출 비율을 고려한 전략 수립**이 필요합니다.

#### 4.2.5 가설5 검증 진행
- 귀무가설: 성별과 체형별 사용자별점 평균과 브랜드별 매출량은 유의미한 상관관계가 없을 것이다.
1) 기초통계분석
- 각 성별과 체형별 사용자 별점 평균 비교
  - 대부분 4.8대의 별점으로 높은 별점을 기록하지만 체형별로 별점이 낮은 브랜드가 존재
- 무신사 스탠다드 - 최대: 4.83(단신-볼륨, 남성) / 최소: 4.73(단신-볼륨, 여성)
- 스파오 - 최대: 4.85(장신-볼륨, 남성) / 최소: 4.78(장신-볼륨, 여성)
- 에잇세컨즈 - 최대: 4.85(장신-슬림, 남성) / 최소: 4.70(단신-볼륨, 여성)
- 탑텐 - 최대: 4.88(장신-슬림, 남성) / 최소: 4.71(단신-슬림, 여성)

2) 정규성 검증
- 이전에 진행한 '사용자별점'의 정규성 검증 결과 정규성을 따르지 않았으므로 스피어만 상관관계 분석 진행

3) 상관관계 분석 결과
- 스피어만 상관계수: -0.4
- p-value: 0.6
- 따라서 특정 성별과 체형을 가진 고객이 특정 브랜드를 선호할 수는 있으나 평균 매출량과 직접적인 연관을 보이지는 않음.

4) 브랜드별 성별 및 체형 별 평균 사용자별점
![image](https://github.com/user-attachments/assets/d773f5d1-3037-4f3d-9e7d-a070dabc5c6a)

5) 가설5 결론
- 성별/체형별 평균평범과 매출량 간에 음의 상관관계가 존재하지만 통계적으로 유의미하지 않고 별점의 차이 또한 크지 않습니다.
- 소비자들이 특정 체형에 맞춘 제품을 선호하지만 구매행동과는 이어지지 않는다는 점을 고려하여 기존 제품의 피드백을 반영하여 **다양한 스타일**을 제공하는 것이 중요할 것이라 판단됩니다.

#### 4.2.6 가설6.1 검증 진행
- 귀무가설: 체형별 카테고리 리뷰수와 평균 별점을 통한 선호도와 유의미한 상관관계가 없을 것이다.
1) 기초통계분석
- 체형별로 특정 제품 카테고리에 대한 리뷰 갯수 및 평균 사용자 별점 차이가 존재
- '단신-볼륨형': '바지', '아우터' 등에 대한 리뷰가 많고 별점이 높음
              : '속옷/홈웨어' 등에 대한 리뷰 수가 적고 평균 별점이 낮음
  - 각 체형별로 카테고리에 대한 만족도가 다를 것으로 예상

2) 정규성 검증
- 리뷰 갯수: p-value<0.05 / 평균 사용자별점: p-value<0.05
  - 모두 정규성을 따르지 않으므로 스피어만 상관관계 분석 진행

3) 상관관계 분석 결과
- 스피어만 상관계수: -0.39
- p-value: 0.0187
   - 리뷰수와 평균 사용자별점간 약한 음의 상관관계를 보이며, 통계적으로 유의미함
   - 귀무가설 기각에 따라 체형별 카테고리 리뷰수와 평균 별점을 통한 선호도는 유의미한 상관관계가 있음.

4) 카테고리/체형별 리뷰수 비교
![image](https://github.com/user-attachments/assets/fc388324-4429-409f-916a-88c82c18cdeb)
- 특정 체형에서 특정 카테고리에 대한 리뷰수가 압도적으로 많음
  - ex. 장신-볼륨형: 바지 / 단신-슬림형: 상의

5) 체형별 카테고리별 평균 사용자별점
![image](https://github.com/user-attachments/assets/e13ff67d-c667-4eeb-8b70-2046464d3290)

- 장신-슬림형: 속옷/홈웨어, 키즈의 경우 압도적으로 별점이 높음
- 장신-볼륨형: 하의에서 별점이 높지만 원피스 혹은 신발의 경우 별점이 낮은편
  - 사이즈의 부재일 가능성이 큼
- 단신-슬림형: 대체로 비슷한 수치를 보이며, 잡화의 경우만 조금 낮은 것을 알 수 있음
  - 패션 잡화의 다양화가 필요해보임
- 단신-볼륨형: 키즈가 다수 분포해있는 해당 범주의 특성에 따라 키즈가 가장 높고 대체적으로 높은 수치를 보이나 속옷/홈웨어의 경우 낮은 별점을 보임
  - 사이즈의 부재일 가능성이 큼

6) 체형별 제품 소분류 선호도
- 리뷰수가 많은 소분류 파악을 통해 제품 추천시 해당 데이터 사용
![image](https://github.com/user-attachments/assets/78fd47c8-35e3-43e4-b950-b707e726877b)
- 눈에 띄는 키워드를 추출하여 각 체형에 선호 제품을 추천
- 맞춤형 제품 추천 시스템 이용

7) 가설6.1 결론
- **체형별로 선호 카테고리를 선별**하여 맞춤형 마케팅 전략을 진행할 수 있습니다.
  - 선호도가 높은 카테고리를 강조하는 방식
- 체형별 제품 만족도를 사용하여 광고 메시지로 강조합니다.
  - 별점이 높은 카테고리 및 제품 구성
- **체형을 기반으로 제품을 추천**하는 추천 시스템 도입이 가능합니다.

#### 4.3.7 가설6.2 검증진행
- 귀무가설: 체형과 리뷰갯수는 유의미한 상관관계가 없을 것이다.
1) 기초통계분석
- 체형별로 리뷰수 차이가 존재
   |체형| 리뷰수 |
   |-|-|
   |단신-슬림형|19,754명|
   |장신-볼륨형|16,990명|
   |장신-슬림형|5,474명|
   |단신-볼륨형|4,015명|
- 하지만 리뷰수 차이가 존재하여도 각 체형별로 재구매 의향에 차이가 있을 수 있다고 판단 불가
- 동일한 계정으로 여러개의 리뷰를 남긴 사용자는 재구매 의향이 높다고 판단하여 분석 진행
- 리뷰수가 정규성을 보이지 않는 것으로 확인되어 Q-Q plot을 이용해 분포도를 확인
![image](https://github.com/user-attachments/assets/efa53096-7ce9-42cb-8cd6-1c09ee34cbfc)
- 확인 결과 사분위 75%까진 1로 기록되어있어 평균 1.2개의 리뷰를 남기나 특정 사용자들은 높은 리뷰수를 기록

2) 상관관계 분석 결과
   - Kruskal-Wallis 검정 진행
- p-value < 0.05로 통계적으로 유의미한 차이가 존재

3) 체형별 리뷰수 최댓값 분포 비교
![image](https://github.com/user-attachments/assets/bbcfc317-ecaf-411c-8164-bfd17e1c7948)
- 특정 체형에서 특정 카테고리에 대한 리뷰수가 압도적으로 많음
  - ex. 장신-볼륨형: 바지 / 단신-슬림형: 상의

4) 가설6.2 결론
- **체형별 재구매의향**에 유의미한 차이를 보이고 있습니다.
- '장신-슬림형', '단신-슬림형'의 최대값이 압도적으로 높은 분포를 보이며, 해당 분석에 따라 '슬림형' 사용자들의 재구매 의향이 높다고 판단됩니다.

### 4.3 통계적 분석의 결론

#### 4.3.1 무신사 제품리스트 파일에 대한 분석 결론

**SPAO 마케팅 전략 도출**
   1. **가격 전략:**
   - 가성비+고품질/트렌디 제품 출시
     - 가격과 품질 모두를 잡은 리미티드 에디션을 출시하거나 현재 인기 상품을 리뉴얼하여 출시
     - 가성비를 원하는 소비자들에게 '가격대'를 강조하면서 동시에 '고품질', '트렌디'를 강조한 캠페인을 진행하여 '차별화'
   2. **브랜드 인지도 및 차별화 전략:**
   - 플랫폼 입점 확장
     오픈서베이 'MZ세대 패션앱 트렌드 리포트 2024'에 따른 이커머스 플랫폼 순위
     ![image](https://github.com/user-attachments/assets/c7b8cb72-030e-45f1-ae31-d454a011980a)
     - 현재 입점해있는 '무신사', '에이블리', '지그재그' 등에서 SPAO 컬렉션을 더 강화하고 아직 입점하지 않은 '29CM', 'W-Concept' 등에 입점 확대
   - SNS / 크리에이터 협업 강화
   3. **대량 판매 제품 집중 마케팅 전략:**
   - 특정 카테고리에서 높은 예측매출량을 보이는 분석결과에 따라 해당 카테고리 집중 마케팅
     - ex. 아우터, 상의 등의 카테고리 집중적으로 마케팅 진행(시즌별 할인 or 세트 판매)
   - 패션소품 판매 확대
     - ex. 트렌드를 기반으로 소품을 출시하여 세트 구성을 통해 소비 도모
 
#### 4.3.2 무신사 제품리스트 + 사용자 리뷰 파일에 대한 분석 결론

**SPAO 마케팅 전략 도출**
   1. **브랜드별 주요 소비층 고려 후 맞춤형 광고 집행:**
   - 남성 비율이 높은 브랜드 --> 남성 소비자 타깃 패션 콘텐츠 강화
     ex. 남성 체형별 SPAO 스타일링 가이드
     ex. 남성 전용 베이직 라인 고객 대상 추가 할인 등
   - 여성 비율이 높은 브랜드 --> 여성 고객 맞춤형 감성 광고 캠페인 기획
     ex. 고객 맞춤형 쇼핑 경험 제공 --> 고객층 유입을 위해 여성 전용라인 위주 홍보, 인플루언서 마케팅 확대
   2. **체형별 핏 가이드 맞춤형 추천 서비스:**
   - 고객 체형에 맞는 제품을 찾을 수 있도록 '체형별 추천 시스템' 기능 도입
     - 각 체형별로 소분류 선호도를 분석한 데이터를 이용하여 해당 카테고리에 맞는 제품들을 추천
     - 체형별 만족도가 높은 제품군 분석을 통해 제품 기획 및 디자인에 반영
   3. **특정 체형별 브랜드 충성도를 위한 맞춤형 마케팅 전략:**
   - 리뷰수가 많은 소비자 타깃군 분석 데이터를 통해 해당 타깃을 대상으로 회원제 혜택 or 포인트 적립 등의 혜택 제공
   4. **리뷰 감성 분석을 통해 제품 개선 및 광고 메시지 반영:** (이후 진행 예정)
   - 머신러닝 과정에서 리뷰 감성 분석을 진행
   - 긍/부정 피드백 추출
   - 긍정 피드백: 광고 메시지 키워드
   - 부정 피드백: 제품 보완 및 개선

---
## 5. 머신러닝

### 5.1 사용자 리뷰 감성분석

#### 5.1.1 모델 선택
- GLU (tenserflow)

#### 5.1.2 데이터 준비 및 인코딩 진행
- 네이버 쇼핑에서 리뷰 파일을 다운 받아 해당 파일의 평점과 리뷰를 로드 후 중복을 제거합니다.
- 감성 Label을 생성하여 평점을 기준으로 긍정과 부정을 출력합니다.
- 한글 이외의 문자(특수기호, 숫자 등)를 제거합니다.
- 불용어('그리고', '한', '있다' 등)를 설정하여 제거합니다.
- 라벨을 만들 모델을 학습시키기 위한 데이터 셋을 준비합니다.

#### 5.1.3 모델 학습
- 훈련용 데이터셋을 이용해 정확도를 검증하고 감성 분석에 대한 모델을 shopreviewnaver.keras로, 토크나이저를 shopreviewnaver.pkl로 저장합니다.

#### 5.1.4 모델 평가
- 무신사 사용자리뷰 데이터를 로드하여 해당 모델을 통해 감성 분석을 진행합니다.
- 점수가 50% 초과이면 긍정, 50%는 중립, 미만은 부정으로 긍/부정을 출력하고, 각 긍정과 부정에 대한 퍼센트를 토대로 1부터 5까지의 점수를 부여합니다.
- 매우 부정: 1, 조금 부정: 2, 중립: 3, 조금 긍정: 4, 매우 긍정: 5

#### 5.1.5 예측 결과 및 추가 분석
**감성분석 결과**
- 5점: 40,150
- 1점: 3,840
- 4점: 1,237
- 2점: 1,007
- 3점: 0

**추가 EDA 분석**

**1. 특정 키워드가 포함된 리뷰에서 감성점수에 차이가 있을 것이다.(긍/부정 리뷰 요인 비교)**
- 리뷰 키워드를 추출하여 점수가 높은 제품군과 낮은 제품군에서 비교
  - 1, 2점 리뷰 단어 / 4, 5점 리뷰 단어를 워드 클라우드로 비교
- 긍/부정 주요 키워드를 추출하여 상품 개선 포인트를 발견할 것이라 예상됩니다.
![image](https://github.com/user-attachments/assets/6103cfa1-b1e0-4366-9577-b06cbb3c6650)

* **긍정적인 리뷰에서 많이 등장하는 키워드**
  - '입을', '보기', '사이즈', '핏', '여름에', '편하고', '가성비', '이쁘고' 등등

  **'입기', '보기'**: 제품 실제 착용 시 기대에 부합한다.<br>
   **'사이즈', '핏'**: 사이즈와 핏이 긍정적인 평가를 받고 있다.<br>
   **'여름에'**: 계절성 상품에 대한 긍정적인 평가가 보인다.<br>
   **'가성비'**: 가격대비 품질이 좋다는 것을 보여준다.<br>

* **인사이트**
  - 제품 핏과 실제 착용 사이즈가 예상과 맞을 때 긍정적인 평가로 이어집니다.
  - 시즌성(여름)에 맞춘 제품이 좋은 평가를 얻는 것을 보아 **시즌별 맞춤 마케팅 전략**이 효과적일 가능성이 높습니다.

* **부정적인 리뷰에서 많이 등장하는 키워드**
  - '많이', '보기', '사이즈', '핏', '입으면', '크게', '길이', '기장', '허리', '얇아서' 등등

  **'사이즈', '핏'**: 긍정 리뷰와 동일한 키워드이나 예상과 다른 핏일 경우 부정평가로 이어지는 것으로 예측된다.<br>
  **'크게', '길이', '기장이', '허리가'**: 사이즈가 크거나 길이가 예상과 다르면 불만이 많다.<br>
  **'얇아서'**: 원단이 얇으면 품질 문제로 지적당할 수 있다.<br>
  **'입으면'**: 입었을 때 불편할 경우 기대와 다르다는 리뷰로 이어질 수 있다.<br>

* 인사이트
    - 사이즈 표기와 실제 착용 핏이 다를 경우 부정적인 리뷰로 이어질 수 있습니다.
    - 허리, 기장, 사이즈 등의 불만이 많으므로 제품 상세 설명에서 **사이즈 관련 가이드**를 강화해야 합니다.
    - **얇은 원단에 대한 불만**을 확인하고 제품 상세 설명에 **원단 두께 설명**도 명확하게 제공해야 합니다.

**2. 특정 카테고리에 따라 감성 점수가 높을 것이다.**
- 대분류, 소분류 따로 감성 점수 평균을 구해 해당 분포를 시각화
* 의류 카테고리에 따라 긍정, 부정 비율이 다를 것으로 예상됩니다.(평균이 낮음 - 불만이 많음 / 평균이 높음 - 만족도가 높음)
1) 기초 통계 분석
- 평균은 4.33부터 4.87을 웃돌며, 키즈, 하의, 가방 등에서 점수가 높고 패션 소품, 신발, 잡화 등에서 낮은 경향을 띔
2) Kruskal-Wallis Test
- 정규성 검증 결과 모든 대분류의 감성 점수가 정규성을 따르지 않아 비모수 검정을 진행
- 검정 결과 p값이 0.05 미만임에 따라 감성 점수 차이가 유의미하다고 판단
3) 대분류별 감성점수 평균
![image](https://github.com/user-attachments/assets/7a2cc16b-2e70-4634-a8fb-a60374ab9492)
- 대분류별로 감성점수 차이가 존재하며, 이를 통해 소비자들이 특정 카테고리 제품에 더 만족하거나 불만족하는 경향이 있음을 파악
- 키즈의 경우 높은 감성 점수를 보이는데, 성인 제품에 비해 기대수준이 낮고 기능성 및 편안함이 만족될 때 긍정적인 평가가 많을 것이라 예상
- 점수가 높은 제품군: **하의, 가방, 아우터** 등
  - 하의: 핏/편안함이 충족될 때 높은 만족도를 받을 가능성이 있음
  - 가방: 실용성이 좋을 경우 만족도가 높을 가능성이 있음
  - 아우터: 보온성 및 스타일이 괜찮을 경우 만족도가 높을 가능성이 있음
- 점수가 낮은 제품군: **신발, 잡화, 패션소품** 등
  - 착용감, 내구성 등에서의 문제가 발생했을 가능성이 높음
  - 모자 및 액세서리의 제품은 디자인이 다를 때 실망하는 경우가 존재
  - 연령대/직업군별 브랜드 조사 데이터에 따르면 전연령대에서 가장 중시하는 요소이 디자인이었던 점을 참고하여 부정 키워드를 추출하고자 함
4) 소분류 감성점수 비교
- 소분류의 경우 종류가 너무 많아 감성점수 평균 순으로 정렬하여 상/하위 10개만 표시
![image](https://github.com/user-attachments/assets/1ee06e65-1c9e-49dd-a6d7-9797447a3ea5)

**감성점수가 높은 상위 10개의 소분류**
- 가방, 기획아우터, 맨투맨, 재킷 등 착용감을 주는 제품 다수 포진
- 특정 기능성 제품의 경우 **겨울철 보온성과 내구성이 좋을 경우** 긍정 리뷰가 많을 가능성이 높음
- 특정 시즌과 관련된 제품 등이 높은 만족도를 보이는 경향을 파악해 **시즌성 프로모션을 진행하는 것**도 좋을 것이라 판단

**감성점수가 낮은 상위 10개의 소분류**
- 슈트/블레이저, 반팔, 슬랙스 등 정장류가 많고 **핏과 사이즈가 중요한 제품군**이 많음
- 신발류의 경우 사이즈가 애매할 때 불만족도가 높으므로 **착용감, 내구성이 부족할 가능성**이 보임
- 리뷰 키워드 분석을 통해 원인을 파악하는 것이 좋을 것이라 판단

각 상위 10개의 소분류 리뷰 키워드 분석
![image](https://github.com/user-attachments/assets/7096955a-f9cd-40b3-afb8-d18191547512)

**1) 감성 점수가 높은 상위 10개 소분류의 키워드 분석 결과**
- 주 키워드:
  - '보기', '많이', '입으려고', '가볍고', '빠르고', '예뻐서', '사이즈도', '배송', '디자인', '무난하게' 등
- 키워드 분석:
  - '보기', '예뻐서', '디자인': 해당 제품이 **디자인적으로 만족**스러웠을 가능성이 높음
  - '가볍고': **착용감**이 가벼웠을 가능성이 있음
  - '사이즈도', '입으려고': 핏과 실제 착용 사이즈가 예상과 잘 맞아 만족스러웠을 가능성이 높음
  - '배송', '빠르고': 배송이 빨라 높은 만족도 추출
  - '무난하게': 활용도가 높은 베이직 제품으로 만족도를 이끌어냄

- **분석결론 및 인사이트**:
  - 디자인이 만족스럽고 착용감이 좋은 제품군에서 높은 감성 점수를 보임
    - 제품 상세페이지에서 디자인 및 활용도를 강조하는 이미지 혹은 영상을 추가하여 고객 경험도를 높입니다.
  - 가볍고 편리한 착용감, 적절한 사이즈 제공이 중요한 요인
    - 소재의 가벼움 및 착용감을 강조한 캠페인을 구상합니다.
  - 배송이 빠르고, 무난하게 착용 가능한 제품에 대한 높은 만족도
    - 빠른 배송을 강조하는 프로모션을 통해 구매 전환을 도모합니다.
   
**2) 감성 점수가 낮은 하위 10개 소분류의 키워드 분석 결과**
- 주 키워드:
  - '사이즈', '많이', '살짝', '입으면', '가격에', '있어서', '크게', '불편', '신고' 등
- 키워드 분석:
  - '사이즈', '많이', '크게': **사이즈가 예상보다 크거나 작아** 불만족 발생
  - '가격에': 가격 대비 **품질이 낮은 점**에서 불만족 발생
  - '불편', '신고': 착용감이 불편함

- **분석결론 및 인사이트**:
  - 하위 10개의 소분류의 대부분은 신발, 사이즈 관련 불만이 많을 것이라 판단
    - 모델 피팅 정보, 사용자 추천 사이즈 등을 강화하여 실제 착용 사이즈와 다른 문제점에 대한 해결점을 도출합니다.
  - 착용감과 핏이 예상과 달른 문제
    - 상세페이지에 **착용감에 대한 상세 설명**을 추가하고 **반품 및 교환 정책을 강화**하여 사후 대처를 진행합니다.

**3. 특정 체형에 따라 감성점수 차이가 존재할 것이다.**
- 성별에 따른 감성점수 평균 / 체형에 따른 감성점수 관계를 각각 비교하여 시각화

**4. 특정 브랜드는 타 브랜드에 비해 감성 점수가 높을 것이다.**
- 브랜드별 감성점수 평균을 비교하고, 긍/부정 리뷰 비율을 비교
예상 인사이트 - 브랜드별 고객 충성도 차이 분석 가능

1) 기초 통계 분석
- 성별, 체형별로 감성 점수 평균을 구해본 결과 대부분 4.5의 비슷한 점수 평균을 보임

2) 비모수 검정 진행
- 성별, 체형 모두 정규성을 따르지 않아 비모수 검정을 진행하였으며, 그 결과 성별의 경우 유의미한 차이를 보이나 체형의 경우 유의미한 결과를 갖지 않음

#### 5.1.6 하이퍼파라미터 튜닝
#### 5.1.7 모델 개선
#### 5.1.8 예측 결과 및 결론
---
## 6. 최종 결과물

### 6.1 개요 및 알고리즘
### 6.2 선택 플랫폼
### 6.3 UI
### 6.4 테스트 진행 결과 
### 6.5 소스코드
---
## 7. 프로젝트 마무리


