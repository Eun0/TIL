# Github 연동하기

먼저 개념은 아래와 같다

### **로컬(내컴퓨터) <---> Git(서버) <---> Github(원격 저장소)**

작업을 하기 위해서는 연동을 해야한다.

## 연동하기

1 . Github에 repository를 만든다.
2 . 우측 상단의 clone or download를 누르고 나오는 주소를 복사한다.
  
	
![default](https://user-images.githubusercontent.com/33515697/43196067-c785367a-9041-11e8-8383-c65bb29b0d23.JPG)
3 . git bash를 키고 repository를 관리하고 싶은 위치로 가서
```
git clone (복사한 주소)
```
를 하면 이런식으로 된다.

![clone](https://user-images.githubusercontent.com/33515697/43196637-9b638e6e-9043-11e8-92da-bf59bf208429.JPG)

4 . 작업 순서

###  pull - > 작업 - > add - > commit  - > push
- git pull : 원격 저장소(Github) 내용을 로컬로 가져오기
- git add *(파일,폴더이름) : 버전 관리할 파일 지정하기
-  git commit -m "커밋 메시지" : commit 하기
- git push : 로컬 저장소 내용을 원격 저장소로 보내기 (로그인 필요)

	< push 완료시 >
	
  ![push](https://user-images.githubusercontent.com/33515697/43197074-fdf457e2-9044-11e8-971e-bb3c82855390.JPG)

 
 
