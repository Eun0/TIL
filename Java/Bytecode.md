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
    
   
   \# 부분이 나의 분석
   ```
   public void quickSort(int, int);

   Code:
       
       # quickSort(int start,int end)
       # 지역변수 1번째 : start
       # 지역 변수 2번째 : end
       
       # int pivot=start;
       0: iload_1                   # 지역변수 1번째 위치의 정수값 로드      
       1: istore_3                  # 지역변수 3번째 위치에 정수값 저장
       
       # int j=pivot
       2: iload_3                   # 지역변수 3번째 위치의 정수값 로드
       3: istore        4           # 지역변수 4번째 위치에 정수값 저장
       
       # int i=pivot+1;
       5: iload_3                   # 지역변수 3번째 위치의 정수값 로드
       6: iconst_1                  # 1 로드
       7: iadd                      # 정수 두 값 더하기 (5:+6:)
       8: istore        5           # 지역변수 5번째 위치에 정수값 저장
       
       # 지역변수 상황
       # 1번째 : start
       # 2번째 : end
       # 3번째 : pivot
       # 4번째 : j
       # 5번째 : i
       
      # if(start<end)
      10: iload_1                   # 지역변수 1번째 위치의 정수값 로드(start)
      11: iload_2                   # 지역변수 2번째 위치의 정수값 로드(end)
      12: if_icmpge     126         # start가 end보다 크거나 같으면 126: 으로 가라 (조건문 false)
      15: goto          72          # 그렇지 않다면 72: 로 가라 (조건문 true)
      
      #
      18: aload_0                     
      19: getfield      #18                 // Field data:[I
      22: iload         5
      24: iaload
      25: aload_0
      26: getfield      #18                 // Field data:[I
      29: iload_3
      30: iaload
      31: if_icmpge     69
      34: iinc          4, 1
      37: aload_0
      38: getfield      #18                 // Field data:[I
      41: iload         4
      43: iaload
      44: istore        6
      46: aload_0
      47: getfield      #18                 // Field data:[I
      50: iload         4
      52: aload_0
      53: getfield      #18                 // Field data:[I
      56: iload         5
      58: iaload
      59: iastore
      60: aload_0
      61: getfield      #18                 // Field data:[I
      64: iload         5
      66: iload         6
      68: iastore
      69: iinc          5, 1
      
      # for(;i<=end;i++)
      72: iload         5                # 지역변수 5번째 위치의 정수값 로드(i)  
      74: iload_2                        # 지역변수 2번째 위치의 정수값 로드(end)
      75: if_icmple     18               # i가 end보다 작거나 같으면 18: 로 가라
      
      78: aload_0
      79: getfield      #18                 // Field data:[I
      82: iload         4
      84: iaload
      85: istore        6
      87: aload_0
      88: getfield      #18                 // Field data:[I
      91: iload         4
      93: aload_0
      94: getfield      #18                 // Field data:[I
      97: iload_3
      98: iaload
      99: iastore
     100: aload_0
     101: getfield      #18                 // Field data:[I
     104: iload_3
     105: iload         6
     107: iastore
     108: aload_0
     109: iload_1
     110: iload         4
     112: iconst_1
     113: isub
     114: invokevirtual #20                 // Method quickSort:(II)V
     117: aload_0
     118: iload         4
     120: iconst_1
     121: iadd
     122: iload_2
     123: invokevirtual #20                 // Method quickSort:(II)V
     126: return
   ```
   
 
   
   
