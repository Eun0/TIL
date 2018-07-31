# 선형 회기(Linear Regression)

**선형 회기란?**

> 두 변수 x와 y와의 관계에 적합한 선을 **회기**라 하고, 
> 
> 이 선이 **직선**일 때 **선형 회기**라 한다.

</br>

**직선 ( Hypothesis )**

: H(x)=Wx+b

</br>
</br>

**Cost Function ( or Loss Function )**
	
: 실제 데이터와 H(x) 얼마나 적합한 지 (거리) 측정하는 함수

- 실제 데이터와 H(x) 차이:  ![equation](https://latex.codecogs.com/gif.latex?%24%28H%28x%5E%7B%28i%29%7D%29-y%5E%7B%28i%29%7D%29%24)

  => not good ( 음수 있을 수 있음)
      
- 결론 :  위의 식 제곱(음수 가능성 x)하고 평균값을 cost라 하자!

   ![eqation](https://latex.codecogs.com/gif.latex?%5Cdpi%7B150%7D%20cost%3D%5Cfrac%7B1%7D%7Bm%7D%5Csum_%7Bi%3D1%7D%5Em%20%28H%28x%5E%7B%28i%29%7D%29-y%5E%7B%28i%29%7D%29%5E2)

- 적합한 선 = cost 작은 H(x)


=> **cost 최소화**하는 **(W,b)** 찾는 것을 **학습**이라고 한다. 

## 예시

- 가정: supervised learning
- 예측(y): 0~100

- training set

  |x (시간)| y (점수) |
  |--|--|             
  | 1 | 10 |
  |2|20|
  |3|30|

  trainig set을 좌표에 그리면 아래와 같다.

  ![image](https://user-images.githubusercontent.com/33515697/43457592-54151c76-9502-11e8-8d7d-58b91d9b29b4.png)
  
  적합한 선 찾기 위해 임의로 선을 긋는다.
  
 ![image](https://user-images.githubusercontent.com/33515697/43457736-b9534aae-9502-11e8-91d7-71ed2c731901.png)
 
   1,2,3 중 어떤 것이 가장 적합한가?
   
   2!!





