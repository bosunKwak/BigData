# 1. Perceptron
 수 많은 머신 러닝 방법 중 하나로, 인공 신경망이 있다. Perceptron이란, Frank Rosenblatt가 1957년에 제안한 초기 형태의 인공 신경망이다. 다수의 입력을 받아 하나의 결과를 출력하는 알고리즘이다. Perceptron은 두 개의 노드가 있을 경우, 그 두개의 노드가 들어가야 하는 위치 인 입력값과 그를 가중하는 가중치, 이를 통해 계산하여 나온 결과인 출력 값으로 구성되어 있다. 각각의 입력값에는 각각의 가중치가 존재하는데, 가중치의 값이 크면 클수록 해당 입력 값이 중요하다. 각 입력값이 가중치와 곱해져서 인공 뉴런에 보내지고, 가중치와 입력값을 곱 한 것을 모두 합한 값이계단 함수(step function)에 의해 판단되는데, 그 값이 임계치 (threshold)를 넘으면 뉴런이 활성화되고 결과값으로 1을 출력한다.
 Perceptron은 단층 퍼셉트론과 다층 퍼셉트론으로 나누어지는데, 단층 퍼셉트론은 값을 보내 는 단계인 입력층(input layer)와 값을 받아서 출력하는 단계인 출력층(output layer)로 이루어 진다. 다층 퍼셉트론은 입력층과 출력층 사이에 은닉층(hidden layer)가 존재한다.
 
# 2. Neural Network
 Neural Network는 인간의 뇌에 착안해 구현된, 스스로 모델을 만드는 통계학적 학습 알고리즘이다. Neural Network은 관찰된 데이터로부터 학습하여 원하는 근사 함수를 만들 수 있다. Neural Network은 복잡한 다중 입력과 방향성 피드백 루프와 단방향 또는 양방향, 그리고 다 양한 계층, 등 여러가지 종류가 있다. 전반적으로, 각각 함수의 제어와 연결을 결정한다. 가장 간단한 방법의 인공신경망으로 전방 전달 신경망(Feed-Forward Neural Network)이 있는데, 오 직 입력층에서 출력층 방향으로 연산이 전개되는 신경망이다.
 Neural Network의 일반적인 구조는 입력 계층, 은닉 계층, 출력 계층으로 구성되어 있다. 입 력 계층은 어떤 연산도 일어나지 않고, 신경망의 입력을 받아서 다음 계층으로 넘기는 역할을 한다. 은닉 계층은 입출력 관점에서 드러나지 않고, 복잡한 문제를 해결할 수 있게 하는 핵심 적인 계층이다. 출력 계층은 신경의 외부로 출력 신호를 전달하는 데 사용되고, 신경망의 기 능은 출력 계층의 활성 함수에 의해 결정된다.

# 3. Loss function
 Loss function(손실 함수)는 다른 명칭으로 Cost function(비용 함수)이라고 합니다. 통계학적 모델은 일반적으로 회귀(regression)와 분류(classification) 두 가지 종류로 나눠지는데, 손실 함 수도 그에 따라 두 가지 종류로 나눠진다. 회귀 타입에 쓰이는 손실 함수는 대표적으로 평균 오차 계산법이 있으며, 평균 오차를 계산하는 공식에 따라 평균 절대 오차(MAE), 평균 제곱 오차(MSE), 평균 제곱근 오차(RMSE), 등으로 구분된다. 분류 타입에 쓰이는 손실 함수는 Binary cross-entropy, Categorical cross-entropy, 등이 있다.

# 4. Optimizer
 Neural network의 학습 목적은 손실 함수의 값을 최대한 낮추는 매개변수를 찾는 것이다. 이는 최적의 매개변수를 찾는 방법, Optimization이라고 한다. 기계 학습의 학습 단계에서의 Optimizer란, 학습 데이터 셋(train data set)을 이용하여 모델을 학습 할 때, 데이터의 실제 결 과와 모델이 예측한 결과를 기반으로 최적의 매개변수를 찾아내는 것이다. 최적이란, 손실 함 수가 최솟값이 될 때의 매개변수 값을 의미하고, 기울기를 이용하여 함수의 최솟값을 찾는 것 이 Optimizer이다.

# 5. LeNet5
 LeNet5란, Yann LeCun이 1998년에 발표한 “Gradient-based learning applied to document recognition”논문에서 소개한 Convolutional neural network 구조이다. LeNet5는 input layer, 3개 의 Convolution layer(C1,C3,C5), 2개의 Pooling layer(S2, S4), 1층의 full-connected layer(F6), Output layer로 구성되었다. C1부터 F6까지 활성화 함수로 tanh(hypobolic tangent)을 사용한다.

## A. Convolution
 Convolution layer는 C1, C3, C5가 있다. C1 Layer는 각 convolution kernel에서 (총 26 =.25 + 1)의 자유 파라미터가 있고, 그런 커널이 6개 있기 때문에 총 156개의 자유 파라미 터가 있다. C3 layer는 C1 layer과 동일한 크기의 5X5 convolution을 수행하며, 14X14 입력 영상을 받아 10X10 크기의 출력 영상을 만든다. C5 layer는 16개의 5X5 kernel 크기의 convolution을 수행하기 때문에 출력 1X1 크기의 feature-map이며, 이를 fully connected 의 형태로 연결하여 총 120개의 feature map을 생성한다.

## B. Pooling
 LeNet5에서 pooling layer는 sub-sampling layer라고도 한다. S2 layer는 sub-sampling을 수행하며, 2X2 크기의 receptive field로부터 average pooling을 수행한다. S4 layer는 10X10 feature-map 영상을 받아 5X5 출력 영상을 만들며, 이 단계의 자유 파라미터의 개수는 32(2X16)개다.