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



