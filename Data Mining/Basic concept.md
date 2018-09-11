# 데이터 마이닝 기초


## Unsupervised Learning

- data 간의 의미있는(meaningful) 관계 알고 싶을 때

  ex) 비슷하게 행동하는 그룹들 찾기

- sample(or input)에 결과 x

- 잘 동작하는 지 알기 어렵다


## Supervised Learning

- input 주어지고 output 알고 싶을 때

  ex) 나이가 29살일 때, 암에 걸릴 확률은?
  
  input : 나이(29)
  
  output : 암에 걸릴 확률(예측)
  
  
- sample(training data set)에 input과 결과 o 

  형태 - (x,y) x:input, y: output

  
  

## model in Supervised Learing

![codecogseqn](https://user-images.githubusercontent.com/33515697/45081591-7e491500-b132-11e8-967e-ba4a315d2240.png)


  - Y : 결과

  - X : p 개의 predictor로 이루어진 vector
  
  - f : X에 대한 unknown ftn (fixed)
  
  - 입실론 : 평균이 0인 random error (X에 대해 독립적), '노이즈'라고도 부름

 
## Parametric method vs Non-Parametric method in Supervised Learning

- Parametric method
  
  : f를 함수의 형태로 명확하게 가정
  
  ex) Linear Regression, Logistic Regression , linear SVM, LDA, QDA
  

- Non-Parametric mehthod

  : f를 함수의 형태로 명확하게 가정하지 않는다..
  
  - 더 많은 observation(sample data) 필요
  
  ex) thin-plate spline,KNN,kernel SVM, decision tree
  

## Training,test,vallidation set

- Training  dataset

  : learning에 사용되는 dataset (fit model)
  
  - overfitting : fit model에 너무 맞추면 새로운 observation이 잘 안 맞을 수 있다.
  
  => test dataset 필요
  
- Test dataset

  : 최종적으로 확인하는 dataset
  
  sample dataset 전체를 바로 학습시키지 않고,
  
  어느 정도는 Test dataset으로 만든다.
    
  - sample dataset = Training dataset + Test dataset 

- Validation dataset

  : 하이퍼파라미터를 조정하기 위해 사용하는 dataset
  
  - 하이퍼파라미터 : 사람이 지정하는 파라미터

  - sample dataset = Training dataset + Validation dataset + Test dataset
  
  ex) training data로 학습 validation으로 조정 training data로 다시 학습 validation으로 조정 ...
  
  => 최종적으로 test data 이용

## MSE (Mean Square Error)


![trainingmse](https://user-images.githubusercontent.com/33515697/45367976-63d4d700-b61d-11e8-9298-36e89cd6598e.png)


![testmse](https://user-images.githubusercontent.com/33515697/45367980-69322180-b61d-11e8-9562-7ebe4be4f164.png)


![expectedtestmse](https://user-images.githubusercontent.com/33515697/45367986-6b947b80-b61d-11e8-8050-3a49546f0968.png)

어떤 모델이 좋은 모델인가? MSE 작은 것!!

