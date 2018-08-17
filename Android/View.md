# 뷰(View)

: 안드로이드 기본 화면을 구성하는 모든 기본 화면 구성요소

- 뷰 = 위젯 + 레이아웃
  
  - 위젯 : 눈에 보이는 것들 ex) 버튼,텍스트뷰,...
  - 레이아웃 : 눈에 보이지 않는 것들 ex) constraint layout,linear layout, relative layout

  ![view](https://user-images.githubusercontent.com/33515697/43814886-c62e4f66-9b07-11e8-91be-b45459832ea2.png)


  - 위젯,레이아웃은 View를 상속한다.
  ![image](https://user-images.githubusercontent.com/33515697/43814946-1808f41c-9b08-11e8-8529-bf1c62dddef0.png)

  - 뷰는 '크기' 속성 꼭 필요 => xml 태그에서 설정
  
    ![image](https://user-images.githubusercontent.com/33515697/43815264-e2c0a2bc-9b09-11e8-9056-0c8d77c684e3.png)
    ![image](https://user-images.githubusercontent.com/33515697/43815235-bb76588c-9b09-11e8-8b7e-dd4d53fbd696.png)
  
    ```XML
     <TextView
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Hello world"/>
    ```
    
    - 크기 설정
      - match_parent : 상위 뷰 크기에 맞춘다 
      - wrap_content : 내용만큼 
      - dp : device에 따라 크기 달라짐 
      - px : 픽셀
      

# 레이아웃

- [Constraint Layout(제약 레이아웃)](https://github.com/Eun0/TIL/blob/master/Android/ConstraintLayout.md)

- [Linear Layout](https://github.com/Eun0/TIL/blob/master/Android/LinearLayout.md)

- [Relative Layout](https://github.com/Eun0/TIL/blob/master/Android/RelativeLayout.md)

- [Frame Layout](https://github.com/Eun0/TIL/blob/master/Android/FrameLayout.md)

- [Table Layout](https://github.com/Eun0/TIL/blob/master/Android/TableLayout.md)
