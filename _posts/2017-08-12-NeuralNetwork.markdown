---
layout: post
title:  "Neural Network"
date:   2017-08-13 06:57:48 +0900
categories: jekyll update
---

* Neural Network 이란
    * 정리 필요
    * Deep Learning 이란
        * 최초에 Neural Network으로 Deep Learning으로 바뀌어서 불림. 결국 둘은 같은 말임.(바뀐 이유는 재미있는 이야기가 있음 - Deep learning의 역사)
![NeuralNetwork]({{ site.url }}/assets/img/20170812/nn.PNG)

* Neural Network 역사
    * 정리 필요

* XOR
두 개의 유닛(LogisticRegression)으로 구성된 Neural Network 네트웍으로 해결할 수 있다.
![xor]({{ site.url }}/assets/img/20170812/xor.PNG)

* 초기 Neural Network 겪었던 문제 (현재도 계속 연구가 진행되고 있는 영역)
    * Back propagation 한계
        * sigmoid를 ReLU(또는 다른 알고리즘)대채하여 극복
    * weight 설정 문제
        * 초기에 weight이 잘 설정되지 않으면 학습이 잘 되지 않는 문제
            * Xaivier/He initialization

* Back propagation(chanin rule)
    * 개요
        * 편미분과 체인룰을 이용하여 각각 영향을 미치는 값을 계산 
        * 많은 게이트가 있더라도 체인룰을 이용하여 값을 구하는 것이 가능
    * 단점
        * sigmoid의 출력이 0~1으로 항상 1보다 작은 값으로 출력되기 때문에 체인룰에 의해 계산되어질 때 뒤로 갈수록 값이 매우 작아지게 된다. -> ReLU 사용
        * Vanishing gradient (NN winter2: 1986~2006)


* Tensorflow에서의 Cost함수 선언 시에 내부적으로 Back propagatino이 자동으로 구성됨.

* sigmoid는 activation function으로 불림. sigmoid가 0~1로 출력하여 다음 뉴런으로 값의 전달여부를 결정하기 때문.

* ReLU : Rectified Linear Unit
    * Back propagation에서 sigmoid는 결과값이 0~1로 나오는데 0에 가까운 값들로 인해 뒤로가 갈수록 weight가 업데이트되지 않는 문제가 발생한다. 그리하여 나온것이 ReLU
![relu]({{ site.url }}/assets/img/20170812/relu.PNG)
![chart]({{ site.url }}/assets/img/20170812/chart.PNG)
![func]({{ site.url }}/assets/img/20170812/func.PNG)

* overfitting
    * More training data!
    * Regularization

* Dropout
    * random하게 몇 개의 neurun을 disable 시켜서 모델들을 학습시키고, test나 predict시에만 모든 neurun을 써서 결과값을 뽑아낸다.
    * 상당히 결과가 좋음
    * 학습할 떄만 Dropout 시킴

* Ensemble
    * 여러개의 학습된 모델의 결과값을 어떠한 기준을 통해 최상의 결과값을 뽑아낸다 (투표등등)