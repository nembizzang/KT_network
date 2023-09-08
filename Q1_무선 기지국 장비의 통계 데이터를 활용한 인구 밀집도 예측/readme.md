# 💁🏻‍♂️제2회 통신망 안정성 확보를 위한 인공지능 해커톤

## ✅ 분야 1 : 무선 기지국 장비의 통계 데이터를 활용한 인구 밀집도 예측

<br>

### 📌 Environments
- 모든 file은 Google colab에서 작성됨.

### 📌 Running Process
- 진행 순서 : EDA -> preprocessing -> modeling&prediction
- EDA 후 각각 상이한 방법으로 5개의 preprocessed data set을 생성
- 각 preprocessed data set 별로 autogluon을 활용하여 예측 모델을 생성(submit 5의 경우는 stage가 2개로 예측 모델이 2개)
- 각 preprocessed data set과 매칭되는 예측 모델을 통해 5개의 submission file을 생성하여 제출

### 📌 Directory
```Q1
├── EDA.ipynb
├── preprocessing.ipynb
└── modeling&prediction.ipynb
```

### 📌 File Description
- EDA.ipynb
  - 개별 feature에 대한 단변량 분석, target과 개별 feature에 대한 이변량 분석, 시계열 분석(시간별,일별,요일별), ACF&PACF
- preprocessing.ipynb
  - 예측 모델에 input되는 train & test set을 만들기 위한 5가지 전처리
- modeling&prediction.ipynb
  - 5가지 전처리 파일에 대응되는 5종류의 예측 모델(submit 5의 경우는 stage가 2개로 예측 모델이 2개) 및 제출 파일 생성

### 📌 Data 유출 금지
- 데이터세트 파일 및 데이터에 대한 설명 등 제공된 일체의 정보는 주최사 및 주관사의 자산이며 해당 정보는 본 대회의 참가 목적으로만 사용해야 하고, 그 외 용도로 타인에게 양도 및 대여, 재배포, 2차적 저작을 할 수 없음. 만약 이를 어길 시 참가자는 모든 민·형사상의 법적 책임을 질 수 있음.