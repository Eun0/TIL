



# 20180722

## pygame

Frequently used grammar

 URL: https://www.pygame.org/docs/

## Object(class)

* pygame.Surface

  : pygame object for representing images
  - constructor: Surface((width, height), flags=0, depth=0, masks=None)
  
* pygame.Rect

  : pygame object for storing rectangular coordinates
	- constructor: Rect(left, top, width, height)
  - attribute: x, y, top, left, bottom, right, center, width, height, ...
	```python								
	 my_rect = pygame.Rect(0,0,10,10)
	 ```									
 


									      
 ## Functions
 * **Initialize screen**
  
   - **pygame.display.set_mode(resolution=(0,0), flags=0, depth=0) -> Surface**
   
     resolution: (width,height)
     
   - **pygame.display.set_caption(title, icontitle=None) -> None**
	   ```python
	    pygame.init()
	    screen = pygame.display.set_mode(150,50)
		pygame.display.set_caption("Tetris")
		```

*  **Draw a rectangle**
  
	  - pygame.draw.rect(Surface, color, Rect, width=0) -> Rect
	  
	       : draw a rectangular shape on the Surface
		  ```python
		   color = (255,255,255)
		   pygame.draw.rect(screen, color, my_rect)
		``` 



		

 * **Display text**
 
	  we can't display text directly. Use pygame.font
  
	  - pygame.font.Font(filename, size) -> Font
	  
	   	 : create a new Font object from a file
    
	  - pygame.font.Font.render(text, antialias, color, background=None) -> Surface
	  
	   	 : draw text on a new Surface. (antialias means smoothing)
    
	  - pygame.Surface.get_rect() -> Rect
	  
		  : returns a new rectangle which starts at 0,0   
  
	  - pygame.Surface.blit(source, dest, area=None, special_flags=0) -> Rect
	  
	   	 : Draws a source Surface onto dest Surface  
 
		```python
		 #dispaly "TETRIS"
	  
		 font = pygame.font.Font(None, 36)
		 text = font.render("TETRIS", 1, color)
		 text_rect = text.get_rect()
		 text_rect.center = (150,150)  # or text_rect = text.get_rect(center=(150,150))
		 screen.blit(text, text_rect)
		```   

* **Display image** 


  - **pygame.image.load(filename) -> Surface**  
 
	  ```python
	   my_img = pygame.image.load("myimg.jpg")
	   screen.blit(my_img, (100,100))
	  ```
