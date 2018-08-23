# LinearLayout


겹치지 않고 한 방향으로 쌓는 레이아웃이다.

방향은 orientation으로 정한다.

![image](https://user-images.githubusercontent.com/33515697/43816592-825d8e38-9b10-11e8-8307-5869919b24b8.png)



## 필수 요소

- **android:layout_width** : 가로

- **android:layout_height** : 세로

- **android:orientation** : 방향 horizontal(가로) or vertical(세로)


## 부수 요소

- **android:layout_weight** : (부모의) 남은 공간을 어떤 비율로 나눌 것인 지 결정

  - 예시
  
    - weight 지정 안했을 때
    </br>
  
    ```xml
    <?xml version="1.0" encoding="utf-8"?>
    <LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        android:orientation="horizontal">

        <Button
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="1"/>

        <Button
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="2"/>

        <Button
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="3"/>


    </LinearLayout>
    ```

    ![image](https://user-images.githubusercontent.com/33515697/44524106-37f9bc00-a717-11e8-9038-570da6f06f8c.png)
    
    - weight 지정 시( 가로 1:2:1)
    
    weight 쓰려면 남는 공간이 있어야한다. 원하는 비율로 나누고 싶은 부분(width or height) '0dp' 로 맞춰준다.
    
   
    ```xml
    <?xml version="1.0" encoding="utf-8"?>
    <LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="horizontal">

      <Button
          <!-- width를 비율 나누고 싶음 0dp로 설정 -->
          android:layout_width="0dp"
          android:layout_height="wrap_content"
           <!-- weight 설정 -->
          android:layout_weight="1"
          android:text="1"/>

      <Button
          android:layout_width="0dp"
          android:layout_height="wrap_content"
          android:layout_weight="2"
          android:text="2"/>

      <Button
          android:layout_width="0dp"
          android:layout_height="wrap_content"
          android:layout_weight="1"
          android:text="3"/>


    </LinearLayout>
    ```
    
     ![image](https://user-images.githubusercontent.com/33515697/44524419-662bcb80-a718-11e8-8493-b303be19c681.png)









  
