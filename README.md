# 추천 시스템 프로젝트

## 📌 프로젝트 개요
이 프로젝트는 **Factorization Machine(FM)** 기반의 추천 시스템을 구현한 것입니다. 사용자의 선호도를 분석하여 맞춤형 추천을 제공하는 개인화 추천 시스템을 구축합니다.
[연세대학교 통계데이터사이언스학과 & 디지털애널리틱스융합학과 학생들과 함께 프로젝트를 수행했습니다.]

## 📂 데이터셋
사용된 데이터셋은 **BX-Book 데이터셋**으로, 다음과 같은 정보를 포함합니다:
- **사용자 데이터 (`users.csv`)**: User-ID, Location, Age
- **아이템 데이터 (`books.csv`)**: ISBN, Book-Title, Book-Author, Year-Of Publication, Publisher
- **평점 데이터 (`ratings.csv`)**: User-ID, ISBN, Book-Rating

## ⚙️ 전처리 과정
1. 평점이 0인 데이터 제거
2. 나이(`age`) 및 출판 연도(`year`) 정규화
3. 사용자-아이템-평점 데이터를 병합
4. 사용자 및 아이템 ID, 위치, 저자 등을 **숫자로 변환 (인코딩)**
5. 희소 행렬(Sparse Matrix) 형태로 변환

## 🤖 추천 알고리즘: **Factorization Machine (FM)**
Factorization Machine은 협업 필터링에서 사용되는 알고리즘으로, 아이템과 사용자 간 **잠재 요인(Latent Factors)**을 학습하여 예측 성능을 향상시킵니다.

### 🔹 FM 주요 개념
- **잠재 요인(Latent Factors)**을 학습하여 사용자-아이템 간 관계를 모델링
- 기존 **행렬 분해(Matrix Factorization, MF)** 모델을 확장하여 다항 상호작용(Feature Interaction)까지 고려
- **Adam Optimizer**를 적용한 최적화 진행
- **RMSE (Root Mean Square Error)** 지표를 활용한 모델 평가

## 📈 모델 학습 과정
1. **데이터 인코딩**: 사용자, 아이템, 저자 등의 특성을 숫자로 변환
2. **Factorization Machine 구현**: Adam Optimizer 기반의 FM 모델 학습
3. **평점 예측**: 훈련된 모델을 사용하여 사용자별 맞춤 추천 제공
4. **모델 평가**: RMSE 지표를 사용하여 성능 측정

## 🛠 사용 기술
- **Python**
- **pandas, numpy**: 데이터 전처리
- **scikit-learn**: 데이터 분할 및 모델 평가
- **Factorization Machine (FM)** 알고리즘 구현

## 🚀 실행 방법
```bash
# 필수 라이브러리 설치
pip install numpy pandas scikit-learn

# Jupyter Notebook 실행
jupyter notebook
```

## 📌 기대 효과
- **사용자 맞춤형 추천**을 통해 개인화 경험 제공
- **Factorization Machine(FM) 모델**을 활용한 고성능 추천 시스템 구현
- **대형 데이터셋을 활용한 확장 가능성** 연구

## 🔍 결과 및 느낀점
본 프로젝트에서는 4가지 추천 모델(협업 필터링(CF), Factorization Machine(FM), Deep Learning, DeepFM)을 비교하였습니다. 
실험 결과, RMSE가 가장 작게 나오는 모델은 FM이었으며, 이를 통해 FM 모델이 추천 시스템에서 높은 성능을 발휘할 수 있음을 확인할 수 있었습니다. 
이 과정은 추천 시스템의 다양한 모델을 비교하고 최적의 방법을 탐색하는 의미 있는 경험이었습니다.

---

