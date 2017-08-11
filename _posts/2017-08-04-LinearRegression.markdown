---
layout: post
title:  "Linear Regression"
date:   2017-08-04 06:57:48 +0900
categories: jekyll update
---
# Regression
회귀 분석은 주어진 데이터가 어떤 함수로부터 생성됐는가를 알아보는 ‘함수 관계’를 추측하는 것.
어떤 연속적인 데이타(x)들이 주어졌을 때 결과값(y)에 대하여 상관관계를 모델링하여 적합도를 측정해내는 분석 기법
* 선형 회귀 분석(Linear Regression Analysis)
* 다중 선형 회귀 분석(Multiple Linear Regression Analysis)

# Hypothesis
Regression 모델을 학습하기 위해 하나의 가설을 세움.
* Linear Regression 가설 (추론식)

$$H(x) = Wx + b$$

# Cost(Loss) function 
hypothesis function의 결과 $$H(x^i)$$와 실제 결과 y의 차이의 평균을 구하는 것
예측값과 결과값의 차이를 구하는 함수를 먼저 구현하고, 그 함수의 결과값의 합의 평균을 구하는 식을 완성한다.

$$cost(W,b) = \frac{1}{m} \sum_{i=1}^m (H(x^{(i)})-y^{(i)})^2$$
    
> $$cost = \frac{1}{m} \sum_{i=1}^m (H(x^{(i)})-y^{(i)})^2$$ <br>
> $$H(x) = Wx + b$$ <br>
> $$cost(W,b) = \frac{1}{m} \sum_{i=1}^m (H(x^{(i)})-y^{(i)})^2$$ <br>

# Gradient Descent Algorithm
경사 기울기 알고리즘
* 업데이트해야 할 W의 값들이 많을 때 편미분을 이용하여 업데이트 함. <br>
$$W := W - α\frac{δ}{δW}cost(W)$$ <br>
$$W := W - a\frac{δ}{m} \sum_{i=1}^m (Wx^{(i)}-y^{(i)})x^{(i)}$$


> $$H(x) = Wx + b$$ <br>
> $$H(x) = Wx$$ <br>
> $$cost(W) = \frac{1}{m} \sum_{i=1}^m (Wx^{(i)}-y^{(i)})^2$$ <br>
> $$cost(W) = \frac{1}{2m} \sum_{i=1}^m (Wx^{(i)}-y^{(i)})^2$$ <br>
> $$W := W - α\frac{δ}{δW}cost(W)$$ <br>
> $$W := W - α\frac{δ}{δW}\frac{1}{2m} \sum_{i=1}^m (Wx^{(i)}-y^{(i)})^2$$ <br>
> $$W := W - α\frac{1}{2m} \sum_{i=1}^m 2(Wx^{(i)}-y^{(i)})x^{(i)}$$ <br>
> $$W := W - α\frac{δ}{m} \sum_{i=1}^m (Wx^{(i)}-y^{(i)})x^{(i)}$$ <br>


# Goal
* Minimize cost
* Cost function의 값을 가장 작게하는 W, b 를 구하는 것






============================================================

# Logistic (regression) classification
* bynary Logistic Classfication 라고도 불림
* 어떤 특정 값이 참인지 아닌지 측정

# Hypothesis
$$H(x) = \frac{1}{1+e^{-W^tX}}$$

# Cost(Loss) function 
$$COST(W) = \sum_{m}^1 C(H(x), y)$$
> $$C(H(x),y) = -ylog(H(x)) - (1-y)log(1-H(x))$$

# Gradient Descent Algorithm
$$W := W - α\frac{δ}{δW}cost(W)$$ <br>
α는 learning_rate 이다.


-----------------------------

# Softmax Classification (Multinomial classifier)
* Multinomial classifier의 한 종류 (여러개의 라벨을 분류)
* Softmax함수를 이용하여 N개의 예측할 것들이 있을 때, Score로 나온 값들을 확률로 변화해주는 것
* Softmax란 입력값에 대한 벡터(2.0, 1.0 ,0.1)가 나왔을 때, 해당 벡터를 확률값(0.7, 0.2, 0.1)으로 변경해주는 함수
* ONE-HOT-ENCODING - (1.0, 0.0, 0.0) -> 이 값처럼 위의 값을 변환. MAX값을 표현해줌.
    * cross entropy함수를 통과하면 위의 값처럼 결과값이 나온다. 따라서 training의 데이타 y(label)값들이 위의 ONE-HOT-ENCODING 방식으로 표현되어 있지 않은 경우 별도 변환을 해줘야 한다.

# Hypothesis
* Softmax 함수 <br>
$$S(Yi) = \frac{e^{Y^i}}{\sum_{j}e^{Y^i}}$$

# Cost function
$$L = \frac{1}{N} \sum_{i} D(S(WXi+b), Li)$$
> $$D(S,L) = -\sum_{i} Li*log(Si)$$ <br>

# Gradient Decent




