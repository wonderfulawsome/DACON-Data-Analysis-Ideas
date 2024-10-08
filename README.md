# 데이콘 데이터 분석 아이디어 프로젝트

## 1. 프로젝트 설명

### 배경
이 프로젝트는 데이콘 경진대회 데이터를 분석하고, 랜덤 포레스트와 LDA(잠재 디리클레 할당)와 같은 머신러닝 기법을 통해 데이터를 분석하는 것을 목표로 한다. 주요 대회에서 사용된 데이터를 바탕으로 참가자 수, 제출 수, 토크 수 등의 통계를 분석하고, 토픽 모델링을 통해 대회의 주요 주제를 파악하는 분석을 수행한다.

### 목표
- 탐색적 데이터 분석(EDA)을 통해 데이터의 전반적인 특성을 파악하고, 머신러닝 기법을 사용해 대회 관련 데이터를 예측 및 분석하는 모델을 구축한다.
- 텍스트 데이터에서 주제를 추출하기 위한 LDA 모델을 적용하고, 랜덤 포레스트 회귀 모델을 통해 예측 성능을 평가한다.

## 2. 코드 설명

### 1. `EDA.ipynb`
- **주요 내용**: 데이터의 탐색적 분석(Exploratory Data Analysis).
  - **데이터 로드**: 참가자 수, 제출 수, 토크 수 등 대회 관련 데이터를 불러와 기본 통계를 확인.
  - **키워드 분석**: 상위 10개 키워드를 추출하여 대회에서 주로 다루는 주제나 키워드를 분석.
  - **결과**: 상위 키워드로 `알고리즘`, `회귀`, `정형` 등이 등장하여, 데이터 분석 대회에서 많이 다뤄지는 주제임을 확인.

### 2. `LDA(Latent Dirichlet Allocation).ipynb`
- **주요 내용**: LDA 모델을 사용해 대회 관련 텍스트 데이터를 분석.
  - **데이터 전처리**: 참가자 수, 제출 수, 토크 수, 코드 공유 수 등 대회 관련 데이터를 전처리.
  - **LDA 모델 적용**: LDA(잠재 디리클레 할당) 모델을 사용하여 텍스트 데이터를 주제별로 분류하고, 토픽을 추출하여 각 대회의 주요 주제를 분석.
  - **결과**: 각 텍스트에서 추출된 주제와 관련된 키워드를 통해 대회의 성격을 이해할 수 있음.

### 3. `RandForest.ipynb`
- **주요 내용**: 랜덤 포레스트 모델을 사용한 예측.
  - **데이터 로드 및 집계**: 대회별 참가자 수, 제출 수, 토크 수, 코드 공유 수를 집계하여 랜덤 포레스트 모델에 사용.
  - **랜덤 포레스트 회귀 모델**: **RandomForestRegressor**를 사용해 데이터를 학습시키고, 대회 관련 변수에 따라 예측을 수행.
  - **모델 평가**: 예측 결과를 평균 제곱 오차(MSE)를 사용해 평가하며, 모델의 성능을 확인.

## 3. 데이터 설명

- **competition_info.csv**: 각 대회에 대한 기본 정보를 제공하는 데이터셋.
  - **ID**: 대회의 고유 식별자.
  - **대회명**: 대회의 이름.
  - **기간**: 대회 진행 기간.

- **participate_log.csv**: 각 대회에서의 참가자 수 관련 데이터를 포함.
  - **ID**: 대회의 고유 식별자.
  - **참가자 수**: 대회에 참가한 사람의 수.

- **submission_log.csv**: 대회에서 제출된 제출 수 관련 데이터.
  - **ID**: 대회의 고유 식별자.
  - **제출 수**: 대회에서 제출된 데이터의 횟수.

- **talk_log.csv**: 대회에서 이루어진 토크(대화) 수와 댓글 수를 포함.
  - **ID**: 대회의 고유 식별자.
  - **토크 수**: 대회 내에서 이루어진 대화 수.
  - **댓글 수**: 대화에 달린 댓글 수.

- **codeshare_log.csv**: 코드 공유와 관련된 데이터를 포함.
  - **ID**: 대회의 고유 식별자.
  - **코드 공유 수**: 대회에서 공유된 코드의 수.

## 4. 기대 효과
- 이 프로젝트는 데이콘 대회와 관련된 다양한 데이터를 분석하고, 참가자의 행동 패턴과 대회의 주제를 이해하는 데 도움을 줄 수 있다.
- LDA 모델을 사용하여 각 대회의 주요 토픽을 분석하고, 랜덤 포레스트 회귀 모델을 통해 대회 데이터의 예측 성능을 평가하여 데이터 분석 및 예측에 기여할 수 있다.
