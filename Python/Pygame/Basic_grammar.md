
## pygame

 기초 문법에 대해 알아보자

 [Pygame documents](https://www.pygame.org/docs/)
 
 기본 형태는 아래와 같다.
 
 ```python
 import pygame

# 스크린 초기화
pygame.init()
screen=pygame.display.set_mode((350,350)) # 스크린 크기 350*350
pygame.display.set_caption("연습") # 캡션 "연습"으로 

finish=False

# Rect 객체 생성 
my_rect=pygame.Rect(0,0,10,20)

# 이벤트 루프
while not finish:
  # 스크린 검은 화면으로. color를 인자로 넘겨준다. 0=(0,0,0)=검은색
	screen.fill(0)

	for event in pygame.event.get():
		if event.type==pygame.QUIT:
			finish=True

	# 여기에 내용 추가 ex. 직사각형 그리기
  
   # 화면 갱신 
	pygame.display.flip()
 
```

## Object(class)

* **pygame.Surface**

  : 그림을 그릴 일종의 '판'
  - 생성자: Surface((width, height), flags=0, depth=0, masks=None)
  
* **pygame.Rect**

  : 직사각형의 정보를 담고 있는 객체
	  - 생성자: Rect(left, top, width, height)
    - 멤버 변수: x, y, top, left, bottom, right, center, width, height, ... 
  
      ```python	
      # Rect 객체 생성
      my_rect = pygame.Rect(0,0,10,10)
      ```									
								      
 ## Functions
 * **스크린 초기화**
  
   - **pygame.display.set_mode(resolution=(0,0), flags=0, depth=0) -> Surface**
   
     resolution: (width,height)
     
   - **pygame.display.set_caption(title, icontitle=None) -> None**
	   ```python
     # 스크린 초기화
	   pygame.init()
	   screen = pygame.display.set_mode(150,50)
     pygame.display.set_caption("Tetris")
	   ```

*  **직사각형 그리기**
  
	- **pygame.draw.rect(Surface, color, Rect, width=0) -> Rect**
	  
	   : Surface에 Rect 그리기
    
	    ```python
      # 직사각형 그리기
      color = (255,255,255)
      pygame.draw.rect(screen, color, my_rect)
	    ``` 



		

 * **텍스트 보여주기**
 
	  텍스트를 바로 쓸 수는 없고, pygame.font를 이용해 텍스트를 보여준다.
  
	  - **pygame.font.Font(filename, size) -> Font**
	  
	   	 : filename으로부터 새로운 Font 객체 만든다
    
	  - **pygame.font.Font.render(text, antialias, color, background=None) -> Surface**
	  
	   	 : text를 새로운 Surface에 그린다 (antialias는 경계를 부드럽게 하는 것)
    
	  - **pygame.Surface.get_rect() -> Rect**
	  
		  : (0,0)에서 시작하는 Rect 리턴   
  
	  - **pygame.Surface.blit(source, dest, area=None, special_flags=0) -> Rect**
	  
	   	 : source Surface를 dest Surface에 그리기  
 
		```python
		 # "TETRIS" 텍스트 보여주기
	  
		 font = pygame.font.Font(None, 36)
		 text = font.render("TETRIS", 1, color)
		 text_rect = text.get_rect()
		 text_rect.center = (150,150)  # or text_rect = text.get_rect(center=(150,150))
		 screen.blit(text, text_rect)
		```   

* **Display image** 


  - **pygame.image.load(filename) -> Surface**  
 
	  ```python
	  # 이미지 보여주기
	   my_img = pygame.image.load("myimg.jpg")
	   screen.blit(my_img, (100,100))
	  ```
	  
	  
## Full code & Screenshot

   ```python
	import pygame

	# 스크린 초기화
	pygame.init()
	screen=pygame.display.set_mode((350,350)) # set screen size 350*350
	pygame.display.set_caption("연습") # set caption "연습"

	finish=False

	# Rect 객체 생성 
	my_rect=pygame.Rect(0,0,10,20)

	while not finish:
		screen.fill(0)

		for event in pygame.event.get():
			if event.type==pygame.QUIT:
				finish=True

		# 직사각형 그리기
		color = (255,255,255)
		pygame.draw.rect(screen,(255,255,255),my_rect)


		# "TETRIS" 텍스트 보여주기
		font=pygame.font.Font(None,36)
		text=font.render("TETRIS",1,color)
		text_rect=text.get_rect()
		text_rect.center=(100,100)
		screen.blit(text,text_rect)

		# 이미지 보여주기
		my_img = pygame.image.load("myimg.jpg")
		screen.blit(my_img, (50,150))

		pygame.display.flip()		
```



![screenshot](https://user-images.githubusercontent.com/33515697/43069794-08a038ac-8ea9-11e8-96f2-e02f1821b8a6.jpg)

	  
	  
	  
