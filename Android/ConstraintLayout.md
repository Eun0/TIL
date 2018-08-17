# ConstraintLayout (제약 레이아웃)


이름대로 제약 조건이 필요하다.

상하 중 한 개 이상

좌우 중 한 개 이상

**상위 뷰와 연결**되어야 한다.

![image](https://user-images.githubusercontent.com/33515697/43816457-de9e5002-9b0f-11e8-986b-336fbb77de48.png)

```xml

    <TextView
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Hello World!"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintLeft_toLeftOf="parent"
        app:layout_constraintRight_toRightOf="parent"
        app:layout_constraintTop_toTopOf="parent" />

```
=>
![image](https://user-images.githubusercontent.com/33515697/43816543-39993738-9b10-11e8-9c17-1d3eeb4add00.png)
