 # 방향키로 직사각형 움직이기(key)
 
 ### 두 가지 방법
   - pygame.key.get_pressed()             
   - event.type=pygame.KEYDOWN
   
 
 ## pygame.key.get_pressed()
```python
# 키 눌렀을 때
pressed=pygame.key.get_pressed()
if pressed[pygame.K_UP]: my_rect.top-=3
if pressed[pygame.K_DOWN]: my_rect.top+=3
if pressed[pygame.K_LEFT]: my_rect.left-=3
if pressed[pygame.K_RIGHT]: my_rect.left+=3
```
 
 ## event.type=pygame.KEYDOWN
 
```python
# 키 눌렀을 때

if event.type == pygame.KEYDOWN:
		
	if event.key==pygame.K_UP:
		my_rect.top-=3

	if event.key == pygame.K_DOWN:
		my_rect.top+=3
			
	if event.key==pygame.K_LEFT:
		my_rect.left-=3
			
	if event.key==pygame.K_RIGHT:
		my_rect.left+=3
```
 
 

## 종합 코드
```python
import pygame

# 스크린 초기화
pygame.init()
screen=pygame.display.set_mode((500,500))
pygame.display.set_caption("직사각형 움직이기")

# Rect 객체 생성
my_rect=pygame.Rect(10,10,50,50)

# 이벤트 루프
finish=False
clock=pygame.time.Clock()

while not finish:
	screen.fill(0)

	for event in pygame.event.get():
		if event.type==pygame.QUIT:
			finish=True

	


	# 키 눌렀을 때
	if event.type == pygame.KEYDOWN:
		
		if event.key==pygame.K_UP:
			my_rect.top-=3

		if event.key == pygame.K_DOWN:
			my_rect.top+=3
			
		if event.key==pygame.K_LEFT:
			my_rect.left-=3
			
		if event.key==pygame.K_RIGHT:
			my_rect.left+=3


			
	
	#직사각형 그리기
	pygame.draw.rect(screen,(255,255,200),my_rect)
	
	# 화면 갱신
	pygame.display.flip()
	clock.tick(100)

```

##
