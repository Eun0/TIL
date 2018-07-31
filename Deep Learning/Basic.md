# 딥 러닝
 
 참고: [모두를 위한 머신러닝/딥러닝](http://hunkim.github.io/ml/)

## 왜 머신 러닝/딥 러닝??

 명확한 프로그래밍을 하기에 **한계**가 있다. ex) 이메일 스팸 처리 rule 너무 많음.
 
 => 주어진 자료로 컴퓨터가 스스로 판단해 처리하는 **머신 러닝/딥러닝** 
 
 ## Supervised/Unsupervised learning
   구분은 사람이 관여 여부 즉 **label의 유무**이다.
   
   사람이 training set에 label을 붙여준 경우 -> **supervised learning** 
   
  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;그렇지 않으면 -> **unsupervised learning**
   
   아래 사진은 label이 붙여진 training set의 예이다.
   
   ![image](https://user-images.githubusercontent.com/33515697/43265744-9f2cc006-9124-11e8-9d19-dd292f304d78.png)
   
   unsupervised는 dog,cat 등 label이 없는 경우다.
   
 ## Supervised learning의 종류
  - **회기(regression)**
  
    : 두 변수 x와 y와의 관계에 적합한 선을 **회기**라 한다.
      
    주어진 training set으로 그래프(회기)를 만들어 예측
    
    
    ex) training set: 5시간 공부->100점, 3시간 공부->60점  
    
      4시간 공부하면 몇 점나올까? 80점 예측
        
  
  
  - **이진 분류(binary classification)**
  
    : 결과 두 가지(Pass/NonPass)로 분류
    
    ex) training set: 5시간 공부 - > P, 3시간 공부 - >  NP  
    
     2시간 공부하면 P or NP? NP 예측
    
  - **multi-label 분류**
  
    : 결과 multi-label(A,B,C,E,F)로 분류
    
    ex) training set: 4시간 공부 - > A, 3시간 공부 - > B, 2시간 공부 - > C 
    
     5시간 공부하면 학점 몇? A 예측

 
 
