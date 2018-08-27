# commit 되돌리기


commit 마다 고유의 번호를 가지고 있음

commit을 되돌리고 싶다면 commit 번호를 알아야 함

commit 번호를 알려면 레파지토리에서 commit을 클릭

![commit1](https://user-images.githubusercontent.com/33515697/44668986-d197d500-aa59-11e8-9ce9-dc58d5488993.PNG)

44...어쩌구가 커밋 번호고 옆에 복사 버튼을 클릭하면 된다

![commit2](https://user-images.githubusercontent.com/33515697/44668985-d197d500-aa59-11e8-9548-72a5dc80892d.PNG)

그 다음에 git bash에서

```
git reset --hard 커밋번호

git push origin +master
```

를 입력하면 커밋 번호 상태로 되돌아감



