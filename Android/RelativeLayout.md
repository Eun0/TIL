# Relative 레이아웃

constraint 레이아웃의 간단한 버전이다.

기능이 constraint보다 적지만 그만큼 더 간단하다.

id를 기준으로 상하좌우에 배치할 수 있다.


## Relativelayout으로 화면 중앙에 배치


```xml

android:layout_centerHorizontal="true"
      
android:layout_centerVertical="true"

```

추가하면 됨

## 필수 요소

- android:layout_width

- android:layout_height

- android:id  - 배치 기능을 쓰려면 필요


## 부수 요소

기준이 되는 view 요소의 위치를 (x,y)라 하자

- android:layout_above="아이디" - 아이디보다 상단에 배치 , y의 위쪽

- android:layout_below="아이디" - 아이디보다 하단에 배치 , (y+기준view의 height)의 아래

- android:layout_toRightOf="아이디" - 아이디의 우측에 배치 , (x+기준view의 width)의 오른쪽

- android:layout_toLeftOf="아이디" - 아이디의 좌측에 배치 , x의 왼쪽

* 예제

  ```xml
  <?xml version="1.0" encoding="utf-8"?>
  <RelativeLayout
      xmlns:android="http://schemas.android.com/apk/res/android"
      android:layout_width="match_parent"
      android:layout_height="match_parent">

      <TextView
          android:id="@+id/base"
          android:layout_width="wrap_content"
          android:layout_height="wrap_content"
          android:layout_centerHorizontal="true"
          android:layout_centerVertical="true"
          android:text="기준" />

      <TextView
          android:layout_width="wrap_content"
          android:layout_height="wrap_content"
          android:layout_toRightOf="@+id/base"
          android:text="오른쪽"/>

      <TextView
          android:layout_width="wrap_content"
          android:layout_height="wrap_content"
          android:layout_above="@+id/base"
          android:text="위쪽"/>

      <TextView
          android:layout_width="wrap_content"
          android:layout_height="wrap_content"
          android:layout_below="@+id/base"
          android:text="아래쪽"/>

      <TextView
          android:layout_width="wrap_content"
          android:layout_height="wrap_content"
          android:layout_toLeftOf="@+id/base"
          android:text="왼쪽"/>
    

  </RelativeLayout>

  ```
  
  ![rl1](https://user-images.githubusercontent.com/33515697/44728168-bd65dd80-ab16-11e8-8ce2-6644677eac02.PNG)
  
만약 바로 옆인 오른쪽에 배치하고 싶다면,
  
align을 이용해야함
  
- android:layout_alignTop="아이디" : 아이디의 상단과 맞추기 , x 맞춰준다.

- android:layout_alignBottom="아이디" 

- android:layout_alignLeft="아이디" 

- android:layout_alignRight="아이디"

- 예제

 아까 부분 오른쪽 textview를 아래와 같이 변경
 
 ```xml
 
   <TextView
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_toRightOf="@+id/base"
        android:layout_alignTop="@+id/base"
        android:text="오른쪽"/>
        
 ```
 
 ![image](https://user-images.githubusercontent.com/33515697/44728687-08342500-ab18-11e8-9ce9-1e7102a96152.png)




비슷하게 부모와 맞춰주는 alignParent도 있다.

- android:layout_alingParentTop="true" 

- android:layout_alingParentTop="true" 

- android:layout_alingParentTop="true" 

- android:layout_alingParentTop="true" 

