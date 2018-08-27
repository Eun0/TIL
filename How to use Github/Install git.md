# git 설치하기 (Windows 10)

1. [Git 다운로드](https://git-scm.com/downloads) 에 가서 Windows 클릭

   ![git1](https://user-images.githubusercontent.com/33515697/44652429-d727f780-aa26-11e8-845a-28c14be9a058.PNG)
  
2. 저 같은 경우 바로 다운로드가 되지 않아서 click here to download 부분을 클릭

   ![git2](https://user-images.githubusercontent.com/33515697/44652430-d727f780-aa26-11e8-8bf8-6883e895859b.PNG)

3. 그냥 next next. 

   중간에 window 명령창에서도 git 명령어를 쓸 것이냐 선택하는 것이 기본(default)인데, 

   git bash에서만 git 명령어 쓸 거기 때문에 거기서 git bash에서만 쓴다 선택

4. 사용자 정보 설정
 
   ```vim
    git config -- global user.name "내 이름"
    git config -- global user.email 이메일 주소
   ```
   내 이름과 이메일 주소는 각자 설정하는 것!!
  
   잘 설정되었는 지 git config --list로 확인!
  
   ![git4](https://user-images.githubusercontent.com/33515697/44652903-2ae71080-aa28-11e8-89fc-28a9915deafd.PNG)



