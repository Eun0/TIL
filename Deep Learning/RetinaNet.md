# Focal Loss for Dense Object Detection - RetinaNet


loss 함수로 cross-entropy를 변형한 함수를 쓴 것이 특징임.


## Abstract & Introduction

요즘 가장 정확도가 높은 object detecotr들은 two-stage approach를 기본으로 한다. 

- Two-stage approach :   Bounding box 찾고 Classification ex. R-CNN

1. Bounding box 찾기 : candidate object location의 sparse set을 만든다.

2. Classification : 각 candidatae object location을 배경인지 object class의 하나인지 cnn을 이용하여 분류

- One-stage approach : Bounding box 찾고 Classification 하는 것을 한번에!  ex. YOLO

  전체 이미지

  더 빠르고 간단하나 성능(정확도)는 two-stage보다 뒤쳐짐
  
- Why?

  dense detector 학습 시, 극단적인 Class 간 imbalance 때문에!
  
  \# of Hard positives(object) << # of Easy negatives(background)
  
- class 분류에 사용되는 loss 함수인 cross entropy 변형 => **Focal Loss**

  well-classified examples 가중치를 낮게 해서 easy sample이 hard sample 학습을 압도하는 것을 막았다!

  즉, Easy sample 가중치 작게
  
  Hard sample 가중치 크게
  
  이 변형한 loss 함수 적용한 dense detector => **RetinaNet**
  
- RetinaNet

  속도는 one-stage detector 만큼 빠르면서 , 성능은 two-stage detector를 뛰어넘는다
  
  네트워크 설계 : feature pyramid 사용, anchor box 사용 (이전 dense detector와 비슷) 
  
  => 성능이 좋은 것은 네트워크 설계가 아니라 참신한 loss 함수 때문 ! 
  

## Related Work

- Classic Object Detectors : sliding-window  방식

- Two-stage Detectors

- One-stage Detectors
 
- Class Imbalance 

- Robust Estimation 

## Focal Loss

잘 분류한 것에는 신경을 덜 쓰고, 잘 분류하지 못한 것에 집중하자!

- Definition 

![Focal Loss](https://user-images.githubusercontent.com/33515697/48937441-6fb01400-ef51-11e8-978f-4050807e965a.png)

  - r 은 하이퍼 파라미터, Focusing parameter라 부른다.  

  - -log(Pt)의 상수는 Scaliing factor 또는 Modulating factor라 부른다. 
  
  - Pt는 잘 분류할 확률 ,Pt가 높을 수록 Easy 낮을 수록 Hard example

- Scaling factor 이용한 Focal Loss 특징 

1. 잘 분류하기 어려운 경우 집중  (Pt -> 0 => Scaling factor -> 1)

2. 잘 분류할 확률 높으면 가중치 감소 (Pt -> 1 => Scaling factor -> 0)

=> 대부분이 구분하기 쉬운 배경 예제들이 많은 경우 good for dense object detector


## RetinaNet Detector


**backbone network**와 **two task-specific subnetworks**로 이뤄진 **하나의** 네트워크

![image](https://user-images.githubusercontent.com/33515697/48943245-ff5fbd80-ef65-11e8-9e91-7b701caad46a.png)

  - backbone network(ResNet + Feature Pyramid Network) : 이미지의 특징 추출

  - two task-specific subnetworks

  1. First subnet : backbone's 결과를 classification

  2. Second subnet : bounding box regression

- Feature Pyramid Network Backbone

  ![image](https://user-images.githubusercontent.com/33515697/48943148-9c6e2680-ef65-11e8-92c0-389511f087e5.png)

  \* 구조 :일반적인 Conv Net(Bottom-Up pathway) + Top-down pathway and Lateral connection (측면 연결)
  
    피라미드 위로 갈수록 semantically 강인하지만 spatially 약하다.
  
    피라미드 Top-down할 때 그 단계의 Bottom-Up으로 만들어진 feature map을 측면 연결한다
  
    => semantically 약하지만 spatially 강인해진다.
  
  \* 장점 : single resolution에서 rich, multi-scale feature pyramid를 만들 수 있다. 
  
    => scale이 다른 각 피라미드 단계를 object detection에 사용 가능
  


 
    
    
    
    






  

  

  
