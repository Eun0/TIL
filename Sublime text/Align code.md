# 코드 정렬 단축키

## 일반 언어 경우

1 . Preference에서 Key Binding 클릭

![1](https://user-images.githubusercontent.com/33515697/44790097-5826f080-abd9-11e8-9a44-0cc2063a7310.png)


2 . 다음 코드 삽입. 만약 처음 설정하는 거라면 []안에 넣어야함.




```
{
    "keys": ["ctrl+shift+r"],
    "command": "reindent",
    "args": {"single_line": false}
}
```

![2](https://user-images.githubusercontent.com/33515697/44790101-5d843b00-abd9-11e8-9e82-d4ac2d63b22f.PNG)

```ctrl+shift+r``` 했지만 다른 거 하고 싶은 사람은 원하는 단축키 설정 가능.

```ctrl+shift+r```자리에 원하는 단축키 넣으면 됨 

```"keys":["원하는단축키"]``` 



## HTML,CSS,JavaScript,Json 경우

어떤 플러그인을 쓰냐에 따라서 다르지만  [Sublime-HTMLPrettify](https://github.com/victorporof/Sublime-HTMLPrettify) 사용함

참고로 **node.js**가 설치되어 있어야함!!



![sub3](https://user-images.githubusercontent.com/33515697/44790104-5fe69500-abd9-11e8-9b36-da4104d95e25.PNG)


이 순서대로 하면된다

번역하자면

node.js가 설치되었다는 가정하에

1. sublime을 키고 ```ctrl+shift+p``` 입력

2. install 입력하고 Package Control:Install Package 선택 

3. 설치가 완료된 후, 또 ```ctrl+shift+p``` 하고 prettify 입력후 HTML-CSS-JS Prettify 선택

하면 설치가 된다.

단축키는 ```ctrl+shift+h``` 이다. ( ```ctrl+a``` 로 전체 선택 후)
