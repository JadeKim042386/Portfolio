# [Computer Vision 개발자] 김주영

## 목차

- [이미지 분류 AI 모델 개발](#-이미지-분류-ai-모델-개발)
- [객체 탐지 AI 모델 개발](#-객체-탐지-ai-모델-개발)
- [객체 영역 분류 AI 모델 개발](#-객체-영역-분류-ai-모델-개발)
- [AI 모델 최적화](#-ai-모델-최적화)
- [음식 사진으로 영양 성분을 분석해주는 웹 서비스](#-음식-사진으로-영양-성분을-분석해주는-웹-서비스)

## Python

### ✨ 이미지 분류 AI 모델 개발

[소개]

사람 얼굴 이미지의 마스크 착용 상태를 분류하는 AI 모델 개발

[기간]

2021.08.23 ~ 2021.09.02 (2주)

[인원]

6명

[결과]

73.5% Private LB Score, 38 팀 중 21 위

[내용]

- 이미지에서 얼굴 부분을 제외한 불필요한 정보를 제거하고 사전 학습된 모델을 사용
- 기존 베이스라인에서 CutMix 기법을 적용 결과 F1 Score 10% 향상

[수행 역할]

- 데이터 불균형 해결을 위한 데이터 수정
- Overfitting 해결을 위한 CutMix 적용

[Github 링크]

- https://github.com/JadeKim042386/image-classification-level1-09

### ✨ 객체 탐지 AI 모델 개발

[소개]

이미지에서 쓰레기를 10 종류로 분류하여 탐지하는 AI 모델 개발

[기간]

2021.09.27 ~ 2021.10.14 (3주)

[인원]

6명

[결과]

61.6% Private LB Score, 19 팀 중 15 위

[내용]

- 사전 학습된 Transformer 모델을 사용
- Multi Scaling, WBF 앙상블을 적용하여 성능 향상

[수행 역할]

- 베이스라인에 제공되지 않은 새로운 모델 탐색 및 적용
- 앙상블 기법 탐색 및 적용

[Github 링크]

- https://github.com/JadeKim042386/object-detection-level2-cv-17

### ✨ 객체 영역 분류 AI 모델 개발

[소개]

이미지에서 쓰레기를 10 종류로 영역을 분리하여 표시하는 AI 모델 개발

[기간]

2021.10.18 ~ 2021.11.04 (3주)

[인원]

6명

[결과]

74.8% Private LB Score, 19 팀 중 5 위

[내용]

- 사전 학습된 Transformer 모델을 사용
- 이미지를 384x384 크기로 Crop 하여 학습
- Hard Voting 앙상블을 적용하여 성능 향상

[수행 역할]

- 기존 베이스라인에 제공되지 않은 새로운 라이브러리와 모델을 탐색 및 적용
- Data Augmentation 기법을 탐색 및 실험
- 다양한 Loss 를 탐색 및 실험
- 앙상블 프로세스 개발

[Github 링크]

- https://github.com/JadeKim042386/semantic-segmentation-level2-cv-17

### ✨ AI 모델 최적화

[소개]

빠른 추론과 동시에 높은 정확도를 가지도록 모델 경량화

[기간]

2021.11.22 ~ 2021.12.02 (2주)

[인원]

6명

[결과]

1.02 Private LB Score, 38 팀 중 7 위

[내용]

- 사전 학습된 모델을 사용하고 input size를 192 로 감소
- Pruning 을 적용하여 높은 정확도와 계산량을 감소

[수행 역할]

- Tensor Composition, Pruning, Quantization 적용 및 실험
- 기존 베이스라인에 있는 Mobilenet 보다 더 적은 Parameter 와 좋은 성능을 가지는 모델을 탐색 및 적용

[Github 링크]

- https://github.com/JadeKim042386/model-optimization-level3-cv-17

### ✨ 음식 사진으로 영양 성분을 분석해주는 웹 서비스

[소개]

업로드한 음식 사진을 종류와 양에 따라 영양 성분을 분석하고 김치로 환산하는 웹 서비스

[기간]

2021.11.19 ~ 2021.12.21 (2개월)

[내용]

- 이미지가 주어지면 음식을 Detection 하고 Detection 한 음식의 종류와 양 추정을 Classification - - 유저의 정보에 따른 해당 음식의 칼로리 분석 결과를 출력

[수행 역할]

- Detection 모델(YOLOv5) 적용 및 실험
- TripletMarginLoss 를 적용한 Clustering 코드 구현 및 적용

[사용 기술]

- Frontend: `Streamlit`
- Backend: `FastAPI`

[Github 링크]

- https://github.com/JadeKim042386/final-project-level3-cv-18
