- 자바 바이트코드 형태

```
<index><opcode> [<operand1> [<operand2>...]] [<comment>]
```

- 퀵소트 구현한 Quick 클래스 자바 코드

```java


public class Quick {
	
	int[] data;

	
public void quickSort(int start,int end){
		
		
		// pivot : 기준. 배열의 첫번째 요소를 기준으로 한다
		int pivot=start;
		// j : (pivot보다 작은 값)교체할 위치
		int j= pivot;
		// i : 배열 순회 위한 인덱스
		int i=pivot+1;
		
		int temp;
		
		if(start<end){
			
			for(;i<=end;i++){
				
				if(data[i]<data[pivot]){
					j++;
					
					temp=this.data[j];
					
					this.data[j]=this.data[i];
					this.data[i]=temp;
				}
			}
			
			temp=this.data[j];
			
			this.data[j]=data[pivot];
			this.data[pivot]=temp;
			
			this.quickSort(start, j-1);
			this.quickSort(j+1, end);
		}
		
	}

}
```

- 바이트 코드

```javap -s -v Quick.class```로 바이트 코드 분석하기

  - 상수 풀
  
  ![image](https://user-images.githubusercontent.com/33515697/49103870-dcb00a80-f2bf-11e8-9afa-596935863c2f.png)
  
  
  

  - 코드 1
  
  ![public Quick bytecode](https://user-images.githubusercontent.com/33515697/49101279-2812ea80-f2b9-11e8-9b3e-b5de3f07960b.png)
  ![image](https://user-images.githubusercontent.com/33515697/49135382-e0787700-f329-11e8-9e7e-c804a8fbe273.png)
    ```
    0 : aload_0
    ```
    
    지역변수배열의 0번째 위치(이 경우 this)에 있는 값을 피연산자 스택으로 로드
  
    ```
    1 : invokespecial #10 //Method java/lang/Object."<init>":()V
    ```
    
    상위 클래스의 생성자를 호출
   
     ```
     4 : return 
     ```
   
     반환값 없이 함수 종료
   
  - 코드 2
    
    ![image](https://user-images.githubusercontent.com/33515697/49102426-2d256900-f2bc-11e8-838d-4c63022eefb5.png)
    ![image](https://user-images.githubusercontent.com/33515697/49102504-56de9000-f2bc-11e8-96dd-25dca3c086e3.png)
    ![image](https://user-images.githubusercontent.com/33515697/49102541-6e1d7d80-f2bc-11e8-80f9-f91b6130f34e.png)
    ![image](https://user-images.githubusercontent.com/33515697/49135450-10c01580-f32a-11e8-8078-7e80a48377b2.png)

    
    - LineNumberTable - ```line 원래 코드의 위치 : 바이트코드의 위치```
    - LocalVariableTable - 지역변수 저장 
    
    
   
   \# 부분이 나의 분석
   
   로드 - '피연산자 스택에' 로드 ,''부분 생략
   
   저장 - '피연산자 스택의 값 지역변수 테이블에' 저장, ''부분 
   ```
   public void quickSort(int, int);

   Code:
       
       # quickSort(int start,int end)
       # 지역변수 1번째 : start
       # 지역 변수 2번째 : end
       
       # int pivot=start;
       0: iload_1                   # 지역변수 1번째 위치의 정수값 로드      
       1: istore_3                  # 지역변수 3번째 위치에 정수형태로 저장
       
       # int j=pivot
       2: iload_3                   # 지역변수 3번째 위치의 정수값 로드
       3: istore        4           # 지역변수 4번째 위치에 정수형태로 저장
       
       # int i=pivot+1;
       5: iload_3                   # 지역변수 3번째 위치의 정수값 로드   
       6: iconst_1                  # 1 로드
       7: iadd                      # 피연산자 스택의 정수 두 값 더하기 
       8: istore        5           # 지역변수 5번째 위치에 저장
       
      # if(start<end)
      10: iload_1                   # 지역변수 1번째 위치의 정수값 로드(start)
      11: iload_2                   # 지역변수 2번째 위치의 정수값 로드   (end)
      12: if_icmpge     126         # start>= end면 126: 으로 가라 (조건문 false)
      
      # for(;i<=end;i++)
      15: goto          72          # 그렇지 않다면 72: 로 가라 (조건문 true)
      
      # if(data[i]<data[pivot])
      18: aload_0                   # 지역변수 0번째 위치의 값 로드 (this)
      19: getfield      #18         # 상수풀의 #18 가져오기 (data 배열)
      22: iload         5           # 지역변수 5번째 위치의 정수값 로드 (i)
      24: iaload                    # data[i] 로드
      25: aload_0                   # 지역변수 0번째 위치의 값 로드 (this)
      26: getfield      #18         # 상수풀의 #18 가져오기 (data 배열)
      29: iload_3 	            # 지역변수 3번째 위치의 정수값 로드 (pivot)
      30: iaload                    # data[pivot] 로드
      31: if_icmpge     69          # data[i]>=data[pivot] 면 69: 로 가라
      
      # j++
      34: iinc          4, 1        # 그렇지 않다면, 지역변수 4번째 위치의 값(j)을 1 증가 
      
      # temp=this.data[j]
      37: aload_0                   # 지역변수 0번째 위치의 값 로드 (this)
      38: getfield      #18         # 상수풀의 #18 가져오기 (data 배열)
      41: iload         4           # 지역변수 4번째 위치의 정수값 로드 (j)
      43: iaload                    # data[j] 로드 
      44: istore        6           # 지역변수 6번째 위치에 저장 (temp)
      
      # this.data[j]=this.data[i]
      46: aload_0                   # 지역변수 0번째 위치의 값 로드 (this)
      47: getfield      #18         # 상수풀의 #18 가져오기 (data 배열)
      50: iload         4           # 지역변수 4번째 위치의 정수값 로드 (j)
      52: aload_0                   # 지역변수 0번째 위치의 값 로드 (this)
      53: getfield      #18         # 상수풀의 #18 가져오기 (data 배열)
      56: iload         5           # 지역변수 5번째 위치의 정수값 로드 (i)
      58: iaload                    # data[i] 로드
      59: iastore                   # data[j]에 저장
      
      # this.data[i]=temp
      60: aload_0		    # 지역변수 0번째 위치의 값 로드 (this)
      61: getfield      #18         # 상수풀의 #18 가져오기 (data 배열)
      64: iload         5           # 지역변수 5번째 위치의 정수값 로드 (i)
      66: iload         6           # 지역변수 6번째 위치의 정수값 로드 (temp)
      68: iastore                   # data[i]에 저장
      
      # i++
      69: iinc          5, 1
      
      # for 문의 조건식 i<=end 부분
      72: iload         5           # 지역변수 5번째 위치의 정수값 로드(i)  
      74: iload_2                   # 지역변수 2번째 위치의 정수값 로드(end)
      75: if_icmple     18          # i가 end보다 작거나 같으면 18: 로 가라
      
      # temp=this.data[j]
      78: aload_0                   # 지역변수 0번째 위치의 값 로드 (this)
      79: getfield      #18         # 상수풀의 #18 가져오기 (data 배열)
      82: iload         4           # 지역변수 4번째 위치의 정수값 로드 (j)
      84: iaload                    # data[j] 로드
      85: istore        6           # 지역변수 6번째 위치에 정수형태로 저장 (temp=data[j])
      
      # this.data[j]=this.data[pivot]
      87: aload_0                   # 지역변수 0번째 위치의 값 로드 (this)
      88: getfield      #18         # 상수풀의 #18 가져오기 (data 배열)
      91: iload         4           # 지역변수 4번째 위치의 정수값 로드 (j)
      93: aload_0                   # 지역변수 0번째 위치의 값 로드 (this)
      94: getfield      #18         # 상수풀의 #18 가져오기 (data 배열)     
      97: iload_3                   # 지역변수 3번째 위치의 정수값 로드 (pivot)
      98: iaload                    # data[pivot] 로드
      99: iastore                   # data[j] 에 정수 형태로 저장
     
     # this.data[pivot]=temp
     100: aload_0                    # 지역변수 0번째 위치의 값 로드 (this)
     101: getfield      #18          # 상수풀의 #18 가져오기 (data 배열)
     104: iload_3                    # 지역변수 3번째 위치의 정수값 로드 (pivot)
     105: iload         6            # 지역변수 6번째 위치에 정수값 로드 (temp)
     107: iastore                    # data[pivot]에 정수 형태로 저장
     
     # this.quickSort(start,j-1)
     108: aload_0                  # 지역변수 0번째 위치의 값 로드 (this)
     109: iload_1                  # 지역변수 1번째 위치의 정수값 로드 (start)
     110: iload         4          # 지역변수 4번째 위치의 정수값 로드 (j)
     112: iconst_1                 # 정수 1 로드
     113: isub                     # 피연산자 스택의 정수 2개 값 빼기 (j-1)
     114: invokevirtual #20        # 상수풀 #20인 this.quickSort 함수 호출 (인자로 피연산자 스택 값 넣어줌)
     
     # this.quickSort(j+1,end)
     117: aload_0                  # 지역변수 0번째 위치의 값 로드 (this)
     118: iload         4          # 지역변수 4번째 위치의 정수값 로드 (j)
     120: iconst_1                 # 정수 1 로드
     121: iadd                     # 피연산자 스택의 정수 2개 값 더하기
     122: iload_2                  # 지역변수 2번째 위치의 값 로드 (end)
     123: invokevirtual #20        # 상수풀 #20인 this.quickSort 함수 호출 (인자로 피연산자 스택 값 넣어줌)
     
     # 리턴
     126: return                   # 반환값 없이 함수 
   ```
   
 
   
   
