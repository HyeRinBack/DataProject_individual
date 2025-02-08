# DATA ANALYTICS 개인 프로젝트

## 1. 프로젝트 개요

### 1.1 프로젝트명:
국내 활동 중인 상위 SPA 브랜드 현 마케팅 전략 분석 후 2025년 SPAO 브랜드 충성 고객 확대 및 매출 증대 도모

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
- 데이터 분석 및 전처리: Pandas, Numpy, Scipy, Scikit-learn, Matplotlib, Seaborn
- 머신러닝: Scikit-learn
- 머신러닝 알고리즘:
- 한글 처리 형태소 패키지: konopy-Okt
- 딥러닝: Tensorflow, llama3

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
- 찜수, 리뷰갯수를 이용해 매출량열 추가 [(제품당 찜수+리뷰갯수)/(브랜드 전체 찜수+리뷰갯수)*100]
- 가격열 범주화('저가', '중저가', '고가', '럭셔리')
- 3만 원 이하 / 3만 원 초과 - 6만 원 이하 / 6만 원 초과 - 9만 원 이하 / 9만원 초과

##### **Summary**
- 리뷰 수에 가중치를 두고 찜수와 더한 값의 비율로 매출량 열 생성
- 가격 열을 참고하여 가격 범주 열 추가 <br>
|저가|중저가|고가|럭셔리|

#### 3.2.3 **추가 데이터 정제**
- 사용자 리뷰 데이터에서 성별, 키, 몸무게 결측치 대체 및 데이터 타입 정수형 변환
- 사용자가 성별, 키, 몸무게의 정보를 입력하지 않아 제품 사이즈 데이터 혹은 색상 데이터가 들어온 경우 결측치로 간주
     - 이용 데이터 :
     - 무신사리뷰_SPAO_1차정제.csv
     - 무신사리뷰_TOPTEN_1차정제.csv
     - 무신사리뷰_8Seconds_1차정제.csv
     - 무신사리뷰_Mutendard_1차정제.csv
###### 1. 성별 열 정제
- '남성' 혹은 '여성'이 아닌 데이터는 해당 제품명을 가진 데이터 중 성별 데이터의 비율을 확인하여 비중이 높은 성별로 대체
###### 2. 키 열 정제
- 대체된 성별에 대한 평균 키로 대체
###### 3. 몸무게 열 정제
- 구매한 사이즈에 대한 몸무게 범주로 대체



