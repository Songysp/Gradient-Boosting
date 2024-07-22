# **Gradient Boosting**
### 주요 개념
* 앙상블 학습: 여러 모델(약한 학습기)을 결합하여 전체 성능을 향상시킵니다.
* 부스팅: 각 새로운 모델이 이전 모델의 오류를 수정하는 방식으로 순차적으로 학습합니다.
* 약한 학습기: 성능이 약간 우수한 간단한 모델로, 보통 얕은 의사결정 트리를 사용합니다.

### Gradient Boosting의 특징
* 회귀 및 분류 문제를 해결하는 데 사용되는 강력한 기계 학습 기법

* 기능 공간에서의 부스팅을 기반으로 하는 기계 학습 기술로, 기존 부스팅에 사용되는 일반적인 잔차가 아닌 유사 잔차를 사용한다
    * 일반잔차: 실제 값과 예측 값의 차이.
    * 유사잔차: 손실 함수의 음의 그래디언트로, 현재 모델의 예측값을 개선하기 위해 사용.
    
* 경사 하강법: 손실 함수의 미분을 통해 반복적으로 최솟값으로 이동하는 최적화 알고리즘입니다.


* $L_{MSE} = \frac{1}{n} \sum_{i=1}^{n} \left( y_i - F(x_i) \right)^2$


* $ -\frac{\partial L_{MSE}}{\partial F(x_i)} = \frac{2}{n} \left( y_i - F(x_i) \right) = \frac{2}{n} h_m(x_i)$

    * $F$: m번째 모델
    * $y$: 관측값
    * $h_{m}$: m번째 모델 잔차


### Gradient Boosting 과정
1. 모델 초기화: 초기 예측값으로 시작합니다. 회귀 문제의 경우 보통 평균값을 사용합니다.
2. 잔차 계산: 실제 값과 현재 모델의 예측 값 사이의 차이(잔차)를 계산합니다.
3. 새 모델 학습: 잔차를 예측하기 위해 새로운 약한 학습기를 학습시킵니다.
4. 모델 업데이트: 새로운 모델의 예측을 기존 모델에 일정 학습률로 더해 예측을 업데이트합니다.
5. 반복: 잔차 계산, 새로운 모델 학습, 예측 업데이트 과정을 정지 조건(예: 최대 반복 횟수 또는 수렴)까지 반복합니다.

장점
높은 정확도: Gradient Boosting은 정확하고 강력한 모델을 만드는 데 도움을 줍니다.
유연성: 다양한 유형의 데이터와 손실 함수를 처리할 수 있습니다.
특징 중요도: 각 특징의 중요도를 파악할 수 있습니다.
