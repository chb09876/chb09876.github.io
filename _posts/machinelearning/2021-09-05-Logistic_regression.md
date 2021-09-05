---
last_modified_at: "2021-09-05 22:42:36"
title: "[기계학습] Logistic regression"
excerpt: "두 가지로 분류하는 Logistic regression에 대해 알아본다."

categories:
  - 기계학습
tags:
  - 기계학습
  - 딥러닝
---

## 개요

Logistic regression은 binary classification에 사용되는 방법이다.

| 혈압 | 고혈압여부 |
| ---- | ---------- |
| 110  | X(0)       |
| 108  | X(0)       |
| 128  | O(1)       |
| 130  | O(1)       |
| 113  | X(0)       |

위와 같이 결과가 연속적이지 않은 데이터는 linear regression으로는 표현하기 어렵다.  
linear regression은 결과값의 범위가 연속적이고 무한하기 때문이다.

이를 해결하기 위해 결과값의 범위를 제한시키고 불연속적으로 만들어 줄 필요가 있다.

결론부터 말하면 sigmoid함수를 사용해 결과값의 범위를 (0,1)로 제한하고 기준값을 정해 그 값보다 크면 1, 작으면 0으로 출력하도록 해주면 된다.

sigmoid함수는 $\frac{1}{1+e^{z}}$꼴의 함수로 Neural network에서 activation function으로도 쓰이는 매우 중요한 함수다.

최종적으로 logistic regression의 수식은 다음과 같다.

$f(\frac{1}{1+e^{-wx}})=\begin{cases}1&\frac{1}{1+e^{-wx}}>0.5\\0&\frac{1}{1+e^{-wx}}<=0.5\end{cases}$

0.5를 기준으로 값을 구분하도록 했는데 기준값은 sigmoid출력값의 범위 안이면 무엇이든 상관없다.

## Cost function

Cost function을 linear regression처럼 mse를 사용하면 local minima 문제에 빠질 수 있다.

가설함수의 형태가 비선형이기 때문이다.

따라서 mse대신 binary cross entropy함수를 사용한다.

시그모이드의 값을 H(x)라 하고, 훈련 데이터의 정답을 y라 하자. bce는 다음과 같다.

$bce(H(x),y)=\begin{cases}-log(H(x))&y=1\\-log(1-H(x))&y=0\end{cases}$
