# 폴더 이름 변경하기

Git bash 를 통해 가능하다.

GitHub repository를 로컬 저장소(내 컴퓨터)에 clone하고 그 안에서 작업하고 push하면 된다.

## 예시 폴더 이름 Machine Learning을 Deep Learning으로 바꾸기

TIL repository에 있는 Machine Learning 폴더의 이름을 바꿀 것이다.

![image](https://user-images.githubusercontent.com/33515697/43356463-033989d4-92ac-11e8-9d36-d70d14e55969.png)

**1 . clone 하기 (연동하기)**

[Github 연동하기](https://github.com/Eun0/TIL/blob/master/How%20to%20use%20Github/connect%20to%20local.md) 참조


**2 . window에서 작업**

![image](https://user-images.githubusercontent.com/33515697/43356497-811a9460-92ac-11e8-8c70-6343e38ae64d.png)

Machine Learning을 Deep Learning으로 바꿨다!


**3 . git push 하기**

  - __git add__
  
  - **git status로 확인**
  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;![image](https://user-images.githubusercontent.com/33515697/43356639-679b9252-92af-11e8-9d1f-27a6bff3ef54.png)
  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;보시면 **'Changes not staged for commit:'** 가 있는데 변경되었지만 commit할 준비가 되지 않은 것을 뜻한다. 
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;그럴 땐 **git add -u**를 이용하자. 
  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;'-u' 는 update를 의미한다. 
  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;update된 것을 commit 준비시킨다는 명령어 이다.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;![image](https://user-images.githubusercontent.com/33515697/43356692-4a05e50c-92b0-11e8-9d7e-e554ba2c06ca.png)
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;git status로 확인하면,
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;아까 Changes not staged for commit의 내용이 이제 Changes to be committed로 바뀐 것을 알 수 있다.

  
  - __git commit -m "커밋 메시지"__
  
  - __git push__
  
  - __결과__
  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;GitHub 들어가면 잘 바뀐 것을 확인할 수 있다.
  
![image](https://user-images.githubusercontent.com/33515697/43356713-c816df00-92b0-11e8-970b-fa06be98ad27.png)

  

