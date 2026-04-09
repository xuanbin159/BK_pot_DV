
# Whitespace Detection

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/xuanbin159/BK_pot_DV/blob/main/3_whitespace_detection.ipynb)

## 개요

본 저장소는 논문 *"Transforming Market Whitespaces into New Product Concepts: A Text Embedding and Inversion Approach"* (Journal of Engineering Design, https://doi.org/10.1080/09544828.2025.2568820) 에서 사용된 시장 공백 탐색 코드를 포함하고 있습니다. Autoencoder로 축소된 2차원 임베딩 공간에서 KDE(Kernel Density Estimation)를 적용하여 제품이 존재하지 않는 저밀도 영역(vacuum point)을 식별하고, 밀도 등고선 및 히트맵으로 시각화합니다.

## 주요 구성

| 단계 | 내용 |
|---|---|
| KDE 밀도 추정 | Silverman's rule 기반 대역폭 설정, 그리드 단위 밀도 계산 |
| Vacuum Point 탐색 | 밀도 구간별(percentile 기준) 데이터 부재 영역 식별 및 중복 제거 |
| 다중 구간 탐색 | 복수의 밀도 구간에 걸쳐 반복 탐색 수행 |
| 시각화 | 밀도 히트맵, 등고선 맵, 데이터 포인트 및 vacuum point 오버레이 |

## 실행 환경

Google Colab 환경에서 실행되며, Google Drive 마운트가 필요합니다. 이전 단계(`2_embedding_autoencoder.ipynb`)에서 저장된 인코딩 임베딩 파일을 사용합니다.

## 의존성

```
numpy, pandas, scipy, matplotlib, torch
```
