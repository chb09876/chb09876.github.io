---
last_modified_at: "2021-09-04 19:43:06"
title: "[기계학습] Linear regression"
excerpt: "머신러닝의 기초인 Linear regression을 알아본다"

categories:
  - 기계학습
tags:
  - 기계학습
  - 딥러닝
---

_공부한 것들을 제 생각과 함께 정리한 것이기에 오류가 있을 수 있습니다.  
오타나 잘못된 정보는 지적해 주시면 감사하겠습니다._

## 개요

Linear regression은 입력값과 출력값 사이의 선형관계를 찾는 과정이다.

| 공부시간 | 시험점수 |
| -------- | -------- |
| 1        | 35       |
| 2        | 40       |
| 5        | 55       |
| 7        | 65       |
| 10       | 80       |

위와 같은 공부 시간 별 점수 데이터가 있다 해보자.  
공부시간과 시험점수가 비례한다고 가정하면 linear regression으로 예측모델을 만들어볼 수 있다.

---

## simple linear regression

| 공부시간 | 시험점수 |
| -------- | -------- |
| 1        | 35       |
| 2        | 40       |
| 5        | 56       |
| 7        | 63       |
| 10       | 82       |

이 데이터를 그래프에 분포시켜보자.

![sfdsf](https://i.imgur.com/zrwjnGc.png)

정확하진 않아도 얼추 비슷한 선 하나를 그을 수 있다.

![sdf](https://i.imgur.com/oUR9lQa.png)

우리는 직관적으로 근사선을 찾았지만, 머신러닝은 조금 복잡한 과정을 거친다.

x를 공부시간, y를 시험점수라 해보자.  
$y=wx+b$

처음 w, b를 임의의 값으로 둔다.

![](https://i.imgur.com/LGhJIkk.png)

이제 오차를 토대로 w, b를 갱신해야 한다.  
오차를 구하기 위한 비용함수는 평균 제곱 오차 함수를 사용한다.

$Cost(H(x),y)=\frac{1}{m}\sum^{m}_{i=1}(H(x_i)-y_i)^2$

비용함수에 경사하강법을 적용하여 가중치를 갱신해준다.

![](https://i.imgur.com/yIfrQl6.png)

위의 과정을 반복해주면 w가 극값지점에 수렴하게 되고 오차가 작은 선형모델을 얻게된다.

## Multi variable linear regression

simple linear regression에선 독립변수 하나에 대응되는 모델을 살펴보았다.  
Multi variable linear regression에선 여러개의 독립변수에 대응되는 모델을 구하는 과정을 살펴본다.

simple linear regression의 데이터에 아래와 같은 데이터가 추가되었다.

| 공부시간 | 게임시간 | 시험점수 |
| -------- | -------- | -------- |
| 1        | 12       | 35       |
| 2        | 8        | 40       |
| 5        | 7        | 56       |
| 7        | 9        | 63       |
| 10       | 4        | 82       |

게임시간또한 시험점수와 선형관계에 있다고 가정하면 다음처럼 모델을 표현할 수 있다.

$y_{score}=w_0x_{study}+w_1x_{game}+b$

이는 행렬로도 표현 가능하다.

$y=WX+b$

나머지 w, b를 갱신하는 방법은 simple linear regression과 동일하다.
