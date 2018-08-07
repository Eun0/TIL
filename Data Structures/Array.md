# 1차원 배열

<index,value> 쌍의 집합. 배열의 index는 0부터 시작

ex)

|index|value|
|--|--|
|0|3|
|1|6|
|2|9|

<=>

int list[3]={3,6,9}


## c 언어에서의 배열

int list[5]

컴파일러 list[0],list[1],...에 연속적인 메모리 주소 할당한다.

list[0]의 주소(=list)는 ***'기본 주소(base address)'*** 라 한다.


- list[i] : list의 index가 i인 것에 접근해서 value값 찾기 => 포인터로 해석

- 기본 주소: a
  list[i]의 주소: a+i*sizeof(리스트타입)
  
 ![image](https://user-images.githubusercontent.com/33515697/43758110-104ac550-9a56-11e8-83b2-170a0cbeec59.png)
  

  
- 배열 선언

```C
// index 2 까지 초기화
// index 3 부터는 쓰레기값
int list[]={1,2,3};

// index 2 까지 초기화
// index 3 부터는 쓰레기값
int list[3]={1,2,3};

// index 2까지 0으로 초기화
// index 3부터는 쓰레기 값
int list3[3]={0,};

```
- 접근 시 offset 곱하지 않는다.
  
=> (list+i) = &list[i]
  
=> *(list+i) = list[i]
  
  
## 배열과 함수

- Call by value 임에도 불구하고 배열 매개변수가 원래 값들을 바꾼다.

```C
// 배열 원소 합 구하는 함수

// 방법 1
int sum1(int li[], int n) {

	int sum = 0;

	for (int i = 0; i < n; i++)
	{
		sum += li[i];
	}

	return sum;
}

//방법 2
int sum2(int* plist, int n) {

	int sum = 0;

	for (int i = 0; i < n; i++)
	{
    // sum += plist[i] 도 o.k
		sum += *(plist + i);
	}

	return sum;
}
```


## 1차원 배열 동적 할당

![image](https://user-images.githubusercontent.com/33515697/43756981-2c04d424-9a52-11e8-9e99-1bfa0801ac54.png)

![image](https://user-images.githubusercontent.com/33515697/43757030-5c7303f6-9a52-11e8-8abc-ea000770a1af.png)

</br>



</br>
</br>

# 2차원 배열
  
![image](https://user-images.githubusercontent.com/33515697/43759871-8ae2b764-9a5b-11e8-81d4-6fb2d899b0a5.JPG)


- 배열 선언

![image](https://user-images.githubusercontent.com/33515697/43759268-af6ff90e-9a59-11e8-9feb-367f2ef1939a.png)

## 2차원 배열 동적 할당

- malloc 이용

```C
#include <stdio.h>
#include <stdlib.h>

// 크기 s 공간 만들어 p에 할당
#define MALLOC(p,s) \
	if(!((p)=malloc(s))){\
		fprintf(stderr,"Insufficient memory");\
		exit(EXIT_FAILURE);\
	}


int ** make2dArray(int rows, int cols) {

	int **x;

	// row 포인터 만들기
	MALLOC(x, rows * sizeof(*x));

  // 각 row에 cols 수 만큼 메모리 할당
  for (int i = 0; i < rows; i++)
	{
  
		MALLOC(x[i], cols * sizeof(**x));
    
    // 0으로 초기화
    for (int j = 0; j < cols; j++)
		{
			x[i][j] = 0;
		}

	}

	return x;
}

void main() {
	
	int **myArray;
	myArray = make2dArray(3, 5);
	myArray[2][4] = 6;

  // 배열 출력
	for (int i = 0; i < 3; i++)
	{
		for (int j = 0; j < 5; j++)
		{
			printf_s("%d ", myArray[i][j]);
		}

		puts("");
	}
  
  // 메모리 해제
	for (int i = 0; i < 3; i++)
	{
		free(myArray[i]);
	}
	free(myArray);
	

}
```

- make2dArray 의미.
  
  사각형: 
![malloc](https://user-images.githubusercontent.com/33515697/43767819-e1853730-9a70-11e8-82f2-109ec974c388.gif)



결과

![image](https://user-images.githubusercontent.com/33515697/43764627-db963494-9a68-11e8-8c07-16aaf7329bbb.png)

</br>

- calloc : 메모리 할당하고 할당된 메모리 0으로 초기화

```C
int ** make2dArray(int rows, int cols) {

	int **x;

	// row 포인터 만들기
	x = (int**) calloc(rows * sizeof(*x));

  // 각 row에 cols 수 만큼 메모리 할당
  for (int i = 0; i < rows; i++)
	{
		x[i] = (int*) calloc(cols * sizeof(**x));
	}

	return x;
}
```

하면 똑같은 결과 나온다.

</br>

- realloc : malloc이나 calloc으로 이미 할당된 메모리크기를 재조정한다.





  
  




