# joy.yoon-project-AI

## 데이터셋 설명
- image size 재각각 -> 224x224 로 조정
- 여러 결측데이터 발견 -> 제거
- test data label 없음 -> label 생성

## 실험 결과
### VGG16 vs ResNet50
VGG16은 91.73%, ResNet50은 90.30%로 VGG16이 더 높은 성능을 보임
해당 데이터셋이 더 작기 때문에 더 좋은 성능이 나온 것으로 판단됨

### 색상이 학습에 미치는 영향 
train dataset에 grayscale 적용 결과 88.86의 결과로 색상이 모델 성능에 약간 미치긴 하지만 큰 차이는 보이지 않음

### dropout 위치가 학습에 미치는 영향
은닉층 91.07%, 출력층 93.72%, 새로운 출력층 91.73%
출력층에 dropout을 적용했을 때 가장 높은 정확도, 유일하게 early stopping이 걸리지 않았기 때문에 과적합 방지의 효과가 가장 크다고 볼 수 있음

## 향후 발전 방향
k-fold 교차검증을 적용하여 일반화 능력 향상
swin transformer 모델 적용 후 기존 적용 모델과의 차이점 비교