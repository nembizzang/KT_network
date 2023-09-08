# 💁🏻‍♂️제2회 통신망 안정성 확보를 위한 인공지능 해커톤

## 📌 주최 및 주관 / 운영

<br>

### ◽ 주최 및 주관 : 한국전자통신연구원(ETRI), KT
### ◽ 운영 : 인공지능팩토리(AIFactory)
### ◽ 대회 홈페이지 : https://aifactory.space/task/2513/overview

<br>

## 📌 대회 소개

<br>

### ✅ 분야 1 : 무선 기지국 장비의 통계 데이터를 활용한 인구 밀집도 예측

<br>

#### ◽ 출제 배경
    많은 사람들이 특정 시간/장소에 모이면 무선 통신 품질의 저하와 함께 각종 사고 위험으로부터 안전할 수 없게 됩니다.
    통신사업자의 무선 통신 기지국에서는 서비스를 제공하는 단말의 통계 정보를 통해 인구의 밀집 정도를 파악 가능합니다.
    무선 네트워크의 성능을 안정적으로 유지하고 인구 밀집도를 완화하기 위해,
    AI를 활용하여 특정 축제 지역 내의 인구 수를 예측하고자 합니다.
#### ◽ 학습 데이터
    무선 기지국 장비인 RU(Radio Unit)에서는 서비스 지역인 셀 내에 존재하는 단말들의 통계 데이터를 관리합니다.
    본 데이터에서는 업링크/다운링크 데이터 크기 및 블록 오류율(BLER),셀 내 평균 수신 신호 강도(RSSI) 및
    사용자 단말 수 등의 각종 통계 정보가 5분 단위로 제공됩니다.
#### ◽ 문제 구성 및 풀이 요령
    축제 지역 근방 10곳의 기지국에서 축제 기간 전후에 해당하는 모든 타임스탬프에 대해 인구 수를 예측하는 회귀 문제입니다.
    다양한 데이터 컬럼 중 인구 수 변화에 유의미한 값을 선별하고 시계열 데이터의 주기성을 고려하는 것이 중요합니다.
    인구 1인당 단말 1대를 가지고 있다고 가정합니다.
#### ◽ 채점 기준
    평균 절대 오차(MAE)

<br>

### ✅ 분야 2 : 유선 네트워크 장비의 신속한 조치를 위한 경보 유형 분류

<br>

#### ◽ 출제 배경
    통신사업자의 네트워크망은 정해진 표준 통신 규격을 준수하는 다양한 이기종 장치들로 구성 및 운용됩니다.
    하지만, 여러 장치 제조사들로부터의 자체 경보 메시지는 그 표현 방식이 서로 다르므로,
    통신사업자에서 신규 장치를 수용하는 경우 정규화 과정이라는 적지 않은 수작업을 필요로 합니다.
    통신 장치의 실시간 상태를 신속히 파악하고 조치하는 것은 네트워크망 안정성 확보를 위한 가장 중요한 일이므로,
    AI를 활용하여 이 문제를 해결하고자 합니다.
#### ◽ 학습 데이터
    인접 시간에 인접 장치에서 발생한 경보들은 상호 연관성을 가지므로 하나의 전표로 군집화 됩니다.
    본 데이터에서는 전표별 경보 메시지의 목록과 발생 시각, 발생 위치 등의 상세 정보가 피처로 제공되며
    해당 전표의 장애 유형이 레이블로 제공됩니다.
#### ◽ 문제 구성 및 풀이 요령
    모든 전표 ID에 대해 링크 장애, 유니트 장애, 전원 장애 중 하나의 유형으로 예측하는 분류 문제입니다.
    경보 메시지를 구성하는 다양한 키워드의 의미와 조합을 이해하고, 다수의 경보 간 발생 순서를 고려하는 것이 중요합니다.
#### ◽ 채점 기준
    정확도(Accuracy)