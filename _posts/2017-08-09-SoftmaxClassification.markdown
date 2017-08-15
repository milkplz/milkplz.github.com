---
layout: post
title:  "Softmax classifier"
date:   2017-08-09 06:57:48 +0900
categories: jekyll update
---
# Softmax Regression

# 요약
* Multinomial classification
    * 여러 개의 class가 있을 때 그것을 예측하는 분류기
* Softmax Regression
    * Multinomial classification 중에서 가장 많이 쓰이는 분류기
* Logistic regression의 hopothesis
    * 출력된 실수를 0~1로 normalize하기 위해 $$sigmoid$$함수를 사용한다.
* Multinomial classification의 hopothesis
    * 출력된 여러 개의 실수를 확률 값으로 바꿔주는 함수를 사용한다.(그 출력된 확률값들의 합은 1이다.) 그것이 바로 $$Softmax classifier$$이다. 
* Logistic regression과 Multinomial Classification
어떤 분류 문제가 binary classifier 즉. 하나의 분류가 필요한 경우(Logistic regression). sigmoid함수에 어떤 가설 함수를 통과시켜 예측값($$\hat{y}$$)이 0,1로 출력되게 하고. 여러가지 분류(Multinomial Classification)가 필요한 경우. softmax함수에 어떤 가설 함수를 통과시켜 예측값들($$\hat{y}$$)들의 합이 1이 되는 확률값으로 변환시켜준다

* Softmax란
    * Softmax란 입력값에 대한 벡터(2.0, 1.0 ,0.1)가 나왔을 때, 해당 벡터를 확률값(0.7, 0.2, 0.1)으로 변경해주는 함수
* ONE-HOT-ENCODING
    * (1.0, 0.0, 0.0) -> 이 값처럼 위의 값을 변환. MAX값을 표현해줌.
    * cross entropy함수를 통과하면 위의 값처럼 결과값이 나온다. 따라서 training의 데이타 y(label)값들이 위의 ONE-HOT-ENCODING 방식으로 표현되어 있지 않은 경우 별도 변환을 해줘야 한다.

# Hypothesis
Softmax를 사용하여 구현<br>
$$S(Yi) = \frac{e^Yi}{\sum_{j}e^Yi}$$
> Yi = H(x) = XW + b

![Softmax]({{ site.url }}/assets/img/20170809/softmax.PNG)

# Cost(Loss) function 
* Cross-entropy cost function를 사용한다. (각 w들은 편미분늘 통해 업데이트 됨??)
$$L = \frac{1}{N} \sum_{i} D(S(WXi+b), Li)$$
> $$D(S,L) = -\sum_{i} Li*log(Si)$$ <br>

* Logistic cost 과 같다.
$$C(H(x),y) = ylog(H(x)) - (1-y)log(1-h(x))$$

![crossendtropy exp]({{ site.url }}/assets/img/20170809/cross_exp.PNG)
![crossendtropy]({{ site.url }}/assets/img/20170809/crossendtropy.PNG)


# Gradient Descent Algorithm
* Tensorflow에서의 Cost함수 선언 시에 내부적으로 Back propagatino이 자동으로 구성됨.
