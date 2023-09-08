# 💁🏻‍♂️제2회 통신망 안정성 확보를 위한 인공지능 해커톤

## ✅ 분야 2 : 유선 네트워크 장비의 신속한 조치를 위한 경보 유형 분류

<br>

### 📌 Environments
- 모든 file은 Google colab에서 작성됨

### 📌 Running Process
- 보는 순서 : Autogluon -> RNN
  - autogluon 파일에서 설명된 내용은 rnn 파일에서 생략되어 하나의 전처리 함수로 표현됨
- 진행 순서 : EDA -> modeling -> prediction
- EDA 이후 정형 데이터(tabular data) 형식, sequential 데이터 형식으로 dataset을 생성
- 정형 데이터는 autogluon을 활용, sequential 데이터는 RNN 기반의 딥러닝 모델을 활용하여 예측 모델을 생성
- 저장된 예측 모델을 불러와 prediction 파일에서 예측 후, 이미 알려진 target class 비율(6:3:1)과 가까운 모델 제출

### 📌 Directory
```Q2
├── eda.ipynb
├── modeling_autogluon.ipynb
├── modeling_rnn.ipynb
├── prediction_autogluon.ipynb
└── prediction_rnn.ipynb
```

### 📌 File Description
- eda.ipynb
  - train 데이터에서 각 feature에 대해 target과 연관성이 있는지를 확인
  - root_cause_domain feature의 범주에 따라서 train 데이터와 test 데이터의 특정 feature들의 범주 및 양상이 완전히 달라지는 것을 확인
  - 몇몇 feature들이 train 데이터에서 존재하지 않는 범주형 값들이 test 데이터에서 등장하는 것을 확인
  - prediction에 유용히 쓰일것이라 예상되는 feature들을 선별
  
- modeling_autogluon.ipynb
  - alarmmsg_original이 root_cause_domain에 따라 값이 천차만별이지만, 서로의 몇몇 값들이 축약어의 관계를 이룬 이음동의어임을 확인하여 축약어 풀이 사전을 생성
  - 축약어 풀이 사전을 이용해 모든 root_cause_domain을 아우르는 corpus를 생성
  - corpus를 이용해 단어 임베딩 모델을 생성하여 alarmmsg_original값을 다차원의 벡터값으로 수치 변환 한 뒤, autogluon을 이용해 모델 학습
  
- modeling_rnn.ipynb
  - modeling_autogluon과 동일한 방법으로 단어 임베딩 모델을 생성해 사용
  - 제공된 데이터가 고유의 ticketno feature를 기준으로 시간적으로 순차적으로 발생한 데이터임을 확인. 이후 모든 데이터가 ticketno 별로 한 종류의 target class를 보유하고 있다는 것을 확인하여 가지고 있는 데이터에서 특정 feature만 추출해서 sequential data로 변환
  - RNN 기반 딥러닝 모델로 학습
- prediction_autogluon.ipynb
  - autogluon이 만들어낸 모든 모델에 대하여 예측을 진행하여 각 예측 결과의 범주 분포를 확인
- prediction_rnn.ipynb
  - 학습된 딥러닝 모델을 불러와 예측을 진행하여 예측 결과의 범주 분포를 확인

### 📌 Data 유출 금지
- 데이터세트 파일 및 데이터에 대한 설명 등 제공된 일체의 정보는 주최사 및 주관사의 자산이며 해당 정보는 본 대회의 참가 목적으로만 사용해야 하고, 그 외 용도로 타인에게 양도 및 대여, 재배포, 2차적 저작을 할 수 없음. 만약 이를 어길 시 참가자는 모든 민·형사상의 법적 책임을 질 수 있음.