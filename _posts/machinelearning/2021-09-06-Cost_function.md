---
last_modified_at: "2021-09-06 19:06:44"
title: "[기계학습] Cost function"
excerpt: "여러 Cost function들의 종류와 용도를 알아본다."

categories:
  - 기계학습
tags:
  - 기계학습
  - 딥러닝
---

## 개요

Cost function은 모델의 학습과정에서 오차를 확인하고 가중치를 업데이트 하는 과정에 사용된다.  
모델의 목표와 가설함수의 형태에 따라 적절한 Cost function을 설정해야 한다.

## MAE(Mean Absolute Error)

$MAE=\frac{1}{m}\sum^{m}_{i=1}|\hat y_i-y_i|$

모델의 예측값과 훈련 데이터의 결과값의 차이를 구해 절대값을 씌워 평균을 구한다.  
regression에서 사용된다.

## MSE(Mean Sqaured Error)

$MSE=\frac{1}{m}\sum^{m}_{i=1}(\hat y_i-y_i)^2$

모델의 예측값과 훈련 데이터의 결과값의 차이를 구해 제곱하여 평균을 구한다.  
제곱을 하기 때문에 MAE에 비해 특이값에 더 민감하다.  
regression에 사용된다.

## Cross Entropy

$CE=\sum^{m}_{i=1}-y_ilog(\hat y_i)$

multi label classification에서 주로 쓰인다.

## Binary Cross Entropy

$BCE=-y_ilog(\hat y_i)-(1-y_i)log(1-\hat y_i)$

binary classification에서 쓰이는 함수다.  
$\hat y_i$는 모델의 예측값으로 0과 1사이의 값이다.  
$y_i$는 훈련 데이터의 결과값으로 0또는 1이다.
