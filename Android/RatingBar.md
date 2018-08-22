# RatingBar 사용법


- 예시 

```xml


<RatingBar
  style="?android:attr/ratingBarStyleSmall"
  android:layout_width="wrap_content"
  android:layout_height="wrap_content"
  android:isIndicator="true"
  android:numStars="5"
  android:rating="4.2"
  android:stepSize="0.1" />


```


## 요소

- style : 스타일 적용       ( style="?android:attr/적용할스타일" )
  
  - ratingBarStyle : default , 큰 사이즈
  
  - ratingBarStyleIndicator : 중간 사이즈
  
  - ratingBarStyleSmall : 작은 사이즈 
  
  - 화면
  
    ![ratingbar style](https://user-images.githubusercontent.com/33515697/44454020-656e3900-a635-11e8-9a23-940cb6682d89.JPG)
  
  - 주의할 점
  
    ![image](https://user-images.githubusercontent.com/33515697/44455223-78363d00-a638-11e8-9d22-fb21302b2e25.png)
    
    임의로 width나 height을 바꿔도 맞춰서 사이즈가 바뀌지 않는다 ㅠㅠ
    
    따로 커스터마이징을 하거나 주어진 style을 이용해야한다.
    
  


    
    </br>
    
  
    
- isIndicator : true면 사용자가 ratingbar를 조정할 수 없다. false면 가능.

  - 스타일마다 false로 했을 때

    ![rating2](https://user-images.githubusercontent.com/33515697/44454551-c6e2d780-a636-11e8-85e9-f59b9a549aae.gif)
    
    
   \* 조정했을 때 바탕색이 *분홍색*이 되는 것은 default가 *false*인 것. </br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;아닌 것은 default가 *true*!

- numStars : 화면에 보여줄 별 개수

- rating : 별 기본 값 ex) 3이면 별 3개 채워짐

- stepsize : 단계 크기. 1로 설정시 별 1개 2개 3개 ... 0.5로 설정시 반개씩 가능. 0.1 이하는 의미가 없어보임.  

