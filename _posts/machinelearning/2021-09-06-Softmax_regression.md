---
last_modified_at: "2021-09-06 19:06:44"
title: "[기계학습] Softmax regression"
excerpt: "multi classification에 사용되는 Softmax regression을 알아본다."

categories:
  - 기계학습
tags:
  - 기계학습
  - 딥러닝
---

## 개요

2개의 그룹으로 나뉘는 데이터는 logistic regression을 적용하면 되지만 3개 이상의 그룹들은 다른 방법을 적용해야 한다.

아이디어는 매우 간단하다.

3개의 그룹 A, B, C를 분류해야 된다면 각각의 그룹에 대해 logistic classification을 적용하는 것이다.  
즉 A인지 아닌지(1), B인지 아닌지(2), C인지 아닌지(3)에 대한 3개의 결과값이 나올텐데 그것을 이용하면 된다.

## Softmax function

![classification](https://i.imgur.com/0cEtbeo.png)

위와 같은 3개의 그룹에 logistic regression을 적용하면 출력값은 총 3개가 된다.  
이 3개의 값을 확률분포로 표현하면 어떨까 하는게 softmax의 아이디어다.

다음은 m개의 출력값중에 i번째 출력값의 확률을 구하는 softmax수식이다.

$S(y_i)=\cfrac{e^{y_i}}{\sum^m_{n=1} e^{y_n}}$

모든 출력값에 softmax를 적용시키면 총 합이 1인 확률 분포가 나오게 된다.  
이 중 가장 높은 확률에 one-hot인코딩을 적용하여 그룹분류를 하는것이 일반적이다.

## Cost function: Cross Entropy Function

logistic regression에서 사용했던 Binary Cross Entropy를 일반화한 버전이다.

$E(S(Y),Y_{data})=-\sum_{i=1}^Ky_{data}^{(i)}log(S(Y)^{(i)})$

S(Y)는 softmax를 거쳐서 나온 결과값이고 $Y_{data}$는 훈련 데이터의 결과값(정답)이다.
