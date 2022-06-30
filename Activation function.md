# Activation function

생성일: 2022년 6월 30일 오후 2:45

---

# Activation function이란?

- 신경망에서 노드에 들어오는 값을 활성화 함수를 통과 시킨 후 전달함
- 입력 신호의 총합을 출력 신호로 변환하는 함수로, 입력 받은 신호를 얼마나 출력할지 결정하고 네트워크에 층을 쌓아 비선형성을 표현할 수 있도록 해줌

# 1. 시그모이드 함수(Sigmoid)
![Untitled](https://user-images.githubusercontent.com/80506107/176608309-235aac09-e049-43cb-be8d-15bf64231f2f.png)

- 독립 변수가 어느 값이든 상관없이 종속 변수(결과값)이 항상 범위 [0, 1] 사이에 있도록 하는 함수
- 출력값은 0보다 크고 1보다 작은 임의의 값이며 미분이 가능함
- 임계값을 설정하고 0과 1을 분류하는 이진 분류 문제에 많이 쓰이지만 0과 1로 강제 출력하는 부분에서 학습이 잘 이루어지지 않음 → 기울기 소실 문제가 발생

# 2. Tanh(Hyperbolic Tangent function)
![Untitled 1](https://user-images.githubusercontent.com/80506107/176608332-5a1e69c1-8819-4976-9cc1-de59482d80e2.png)


- Sigmoid 함수를 대체제로 사용 될 수 있으며 Sigmoid 함수와는 다르게  출력값이 -1에서 1 사이임
- tanh함수는 sigmoid 함수와 다르게 출력 범위가 더 넓고 경사면이 크기 때문에 더 빠르게 수렴하여 학습함
- 하지만 sigmoid 함수의 문제인 기울기 소실(gradient vanishing) 문제를 가지고 있음

# 3. 소프트맥스 함수(Softmax function)

- input 값을 [0, 1] 사이의 값으로 모두 정규화하여 출력하며, 출력값들의 총합은 항상 1이 됨
- 다중 분류 문제에서 사용하며 분류될 클래스 개수에 따른 n차원의 벡터를 입력받아 각 클래스에 속할 확률을 추정함
![Untitled 2](https://user-images.githubusercontent.com/80506107/176608356-8abe887d-a55a-4604-a55c-e356b7adddbd.png)



- n = 출력층의 뉴런 수(총 클래스 수)
- x = x번째 클래스

# 4. ReLU 함수(Rectified Linear Unit function)
![Untitled 3](https://user-images.githubusercontent.com/80506107/176608386-cc334877-49f8-4d3b-b572-e708b94e91d7.png)

![Untitled 4](https://user-images.githubusercontent.com/80506107/176608399-d222366b-c5ed-4238-98ae-9673c28e7f67.png)


- 딥러닝에 사용되는 활성화 함수

- 뉴런의 활성화 값이 0이거나 음수이면 0으로 만들어서 연산량을 줄여주고 기울기 소실 문제를 해결 할 수 있음
- 값이 0이된 뉴런은 죽게 되는 단점이 존재

# 5. Leakly ReLU

![Untitled 5](https://user-images.githubusercontent.com/80506107/176608168-011bfd2e-3b7a-4b52-b69f-03e971cc1382.png)
- ReLU 함수에서 뉴런이 죽는 것을 방지하기 위해 만든 것으로 0대신 활성화 값에 0.01을 곱함

# 6. PReLU

![Untitled 6](https://user-images.githubusercontent.com/80506107/176608224-fc4f04e7-e28b-4660-bb3f-7b0b7725f3de.png)

- 새로운 파라미터 $\alpha$을 추가하여 x < 0에서 기울기를 학습할 수 있게함


# 7. ELU(Exponential Linear Unit)

![Untitled 7](https://user-images.githubusercontent.com/80506107/176608255-f5adef8c-1645-48c3-bfce-3b6c30ad050d.png)

- 비용을 0으로 더 빨리 수렴하고 보다 정확한 결과를 도출함




# 참고자료

[[ML] 활성화 함수(Activation Function) 종류 정리](https://heeya-stupidbutstudying.tistory.com/38)
