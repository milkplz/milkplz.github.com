---
layout: post
title:  "Logistic (regression) classification"
date:   2017-08-09 06:57:48 +0900
categories: jekyll update
---
# Logistic (regression) classification
* bynary Logistic Classfication 라고도 불림
* 어떤 특정 값이 참인지 아닌지 측정

# Hypothesis
* Linear regression에 사용되었던 Hypothesis인 $$H(x) = Wx$$의 식은 $$\hat{y}$$이 실수로 나오며 이 실수는 무한 범위 이기 때문에 Logistic Regression의 0과 1의 분류 문제에는 맞지 않다. 
그래서 $$\hat{y}$$이 0~1의 값을 갖도로 하는 식을 이용한다. 그것이 바로 sigmoid함수. 이 함수는 logistic 함수라고도 불린다. sigmoid를 S(x)라고 H(x)를 G(x)라고 정의하면 아래와 같다.<br>
$$H(x) = S(G(x))$$<br>
$$H(x) = \frac{1}{1+e^{-G(x)}}$$<br>
$$H(x) = \frac{1}{1+e^{-W^tX}}$$

# Cost(Loss) function 
* 결정된 Hypothesis가 sigmoid함수를 사용하기 때문에 Cost함수의 결과값을 바가지 형태의 그래프를 만들기 위해 $$log$$를 사용하여 아래와 같은 식을 사용한다.
$$COST(W) = \sum_{m}^1 C(H(x), y)$$
> $$C(H(x),y) = -ylog(H(x)) - (1-y)log(1-H(x))$$

# Gradient Descent Algorithm
$$W := W - α\frac{δ}{δW}cost(W)$$ <br>
α는 learning_rate 이다.