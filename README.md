# Power Demand Forecasting with ANN and RNN

기상 변수와 시계열 정보를 이용해 전력 소비량을 예측하고, ANN과 RNN 접근을 비교한 탐색적 학습 프로젝트입니다.

완성된 제품 코드가 아니라 **모델 선택 과정과 시행착오를 보여주는 실험 기록**으로 공개합니다. 노트북에는 데이터 탐색, 정규화, 교차 검증, 역정규화, ANN 회귀, RNN 시계열 예측 및 결과 비교 과정이 포함되어 있습니다.

## What this notebook covers

- 시간·온도·습도·풍속과 구역별 전력 소비량의 관계 탐색
- Min-Max scaling과 train/test 분리
- Dense ANN 회귀 모델과 K-fold 검증
- 시계열 입력을 위한 sequence 구성과 RNN 학습
- MAE, MSE, R²를 이용한 성능 비교
- 정규화·역정규화된 실제값과 예측값 시각화
- 2017년과 2018년 데이터에 대한 모델 적용 실험

## Run

```bash
python -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
jupyter lab
```

노트북은 다음 상대경로를 사용합니다.

```text
data/power_consumption_2017.csv
data/power_consumption_2018.csv
data/power_consumption_2017_hourly.csv
```

## Data availability

2017년 실험은 UCI Machine Learning Repository의 [Power Consumption of Tetouan City](https://archive.ics.uci.edu/dataset/849/power+consumption+of+tetouan+city) 데이터 구조를 사용했습니다. 원본 데이터는 CC BY 4.0 조건으로 제공되며, 이 저장소에는 재배포하지 않습니다.

2018년 실험에 사용한 지역 전력 CSV는 원출처와 재배포 조건을 현재 확인할 수 없어 포함하지 않았습니다. 따라서 해당 셀은 적법하게 확보한 동일 스키마의 데이터가 있어야 재실행할 수 있습니다.

## Limitations

- 과거 탐색 과정이 담긴 노트북이라 셀 간 상태 의존성이 있습니다.
- 일부 비교 실험은 원본 2018 데이터가 없어 현재 완전 재현되지 않습니다.
- 무작위 분할과 시계열 분할의 차이, 데이터 누수 가능성 및 모델 선택 방식은 후속 개선 대상입니다.
- 이 저장소는 결과를 과장하지 않고 학습 과정과 한계를 함께 보여주기 위한 포트폴리오 기록입니다.

## Tech stack

Python · Pandas · NumPy · TensorFlow/Keras · scikit-learn · Matplotlib · Seaborn

