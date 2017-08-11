---
layout: post
title:  "Softmax classifier"
date:   2017-08-09 06:57:48 +0900
categories: jekyll update
---
# Softmax Classification
* Multinomial classifier의 한 종류 (여러개의 라벨을 분류)
* N개의 예측할 것들이 있을 때, Score로 나온 값들을 확률로 변화해주는 것
* Softmax란 입력값에 대한 벡터(2.0, 1.0 ,0.1)가 나왔을 때, 해당 벡터를 확률값(0.7, 0.2, 0.1)으로 변경해주는 함수
* ONE-HOT-ENCODING - (1.0, 0.0, 0.0) 이것처럼 위의 값을 변환. MAX값을 표현해줌.

# Hypothesis
Softmax를 사용하여 구현
$$S(Yi) = \frac{\sum_{j}e^Yi}{e^Yi}$$

# Cost(Loss) function 
* Cross-entropy cost function
    * 

* Logistic cost
$$C(H(x),y) = ylog(H(x)) - (1-y)log(1-h(x))$$

* cross entropy
$$D(S,L) = -\sum_{i}^Li * log(Si)$$

# Gradient Descent Algorithm
경사 기울기 알고리즘

# Goal
* 
