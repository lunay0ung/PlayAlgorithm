## KNN 알고리즘 / KNN algorithm (K-nearest neighbors algorithm)

 - 정의 및 특징 
    - ![](http://res.cloudinary.com/dyd911kmh/image/upload/f_auto,q_auto:best/v1531424125/KNN_final1_ibdm8a.png) ([How does the KNN algorithm work?](https://www.datacamp.com/community/tutorials/k-nearest-neighbor-classification-scikit-learn))
    - In pattern recognition, **the k-nearest neighbors algorithm (k-NN) is a non-parametric method used for classification and regression**. In both cases, the input consists of the k closest training examples in the feature space. The output depends on whether k-NN is used for classification or regression. ([Wikipedia](https://en.wikipedia.org/wiki/K-nearest_neighbors_algorithm))
        - **In k-NN classification, the output is a class membership**. An object is classified by a plurality vote of its neighbors, with **the object being assigned to the class most common among its k nearest neighbors (k is a positive integer, typically small)**. If k = 1, then the object is simply assigned to the class of that single nearest neighbor.
        - **In k-NN regression, the output is the property value for the object**. This value is the **average of the values of k nearest neighbors**.
        - k-NN is a type of **instance-based learning**, or lazy learning, where the function is only approximated locally and all computation is deferred until classification.
        - A peculiarity of the k-NN algorithm is that it is sensitive to the local structure of the data.
    - KNN은 k개의 가장 가까운 이웃 데이터를 이용하여 분류와 회귀 분석을 할 수 있는 알고리즘이다.
        - 분류 = 그룹으로 나누기
        - 회귀 = (숫자로 된) 반응을 예측하기 
    - KNN을 사용할 때는 **올바른 특징을 고르는 것이 중요**하다. KNN을 통해 넷플릭스의 영화 추천서비스를 구현해야 한다고 가정할 때, 올바른 특징은 다음과 같을 수 있다.
        - 추천하고자 하는 영화와 직접 관련이 있는 특징
        - 편향되지 않은(예를 들어, 코미디 영화에 대한 평점만 있다거나 액션 영화에 대한 평점만 있는 경우) 특징 
        - **단, 좋은 특징을 고르는 데 있어 정답은 없다. 여러 가지 다른 관점에서 모두 살펴 보아야 한다.**
    - 많은 변수가 관련되어 있는 경우에는 사실상 예측이 불가능하다.      



 - 참고 자료
    - [KNN Classification using Scikit-learn](https://www.datacamp.com/community/tutorials/k-nearest-neighbor-classification-scikit-learn)
        - KNN used in the variety of applications such as **finance, healthcare, political science, handwriting detection, image recognition and video recognition**. In Credit ratings, financial institutes will predict the credit rating of customers. In loan disbursement, banking institutes will predict whether the loan is safe or risky. In political science, classifying potential voters in two classes will vote or won’t vote. KNN algorithm used for both classification and regression problems. **KNN algorithm based on feature similarity approach**. 
        - KNN is a **non-parametric and lazy learning algorithm. Non-parametric means** there is no assumption for underlying data distribution. In other words, **the model structure determined from the dataset**. This will be **very helpful in practice** where most of the real world datasets do not follow mathematical theoretical assumptions. 
     
     

 - 머신 러닝
    - OCR / optical character recognition
        - ![](https://miro.medium.com/max/1200/1*qBV12ANk-5epRv7231Zxzw.png) ([4 Simple steps in building OCR](https://medium.com/datadriveninvestor/4-simple-steps-in-building-ocr-1f41c66099c1))
        - 어떤 그림이 무슨 숫자인지 자동으로 알게 하려면 어떻게 해야 할까? KNN을 사용하는 경우에는 다음과 같이 하면 된다.
            - 여러 가지 숫자 그림을 살펴보고 이 그림들의 특징을 뽑아낸다. 이 과정을 트레이닝training이라고 한다. (컴퓨터가 어떤 일을 하려면 반드시 트레이닝 단계를 거쳐야 한다.)
            - 새로운 그림이 주어지면 그 그림의 특징을 뽑아서 가장 가까운 것들을 살펴본다. 
        - 아무리 복잡한 기술이라고 KNN과 같은 간단한 아이디어에 기반하고 있다는 점을 이해하는 것이 중요하다. 

    - 나이브 베이즈 분류기 / Naive bayes classifier
        - 나이브 베이즈는 **분류기를 만들 수 있는 간단한 기술로써 단일 알고리즘을 통한 훈련이 아닌 일반적인 원칙에 근거한 여러 알고리즘들을 이용하여 훈련된다. 모든 나이브 베이즈 분류기는 공통적으로 모든 특성 값은 서로 독립임을 가정**한다. 예를 들어, 특정 과일을 사과로 분류 가능하게 하는 특성들 (둥글다, 빨갛다, 지름 10cm)은 나이브 베이즈 분류기에서 특성들 사이에서 발생할 수 있는 연관성이 없음을 가정하고 각각의 특성들이 특정 과일이 사과일 확률에 독립적으로 기여 하는 것으로 간주한다. ([위키피디아](https://ko.wikipedia.org/wiki/나이브_베이즈_분류))

 
