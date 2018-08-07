# 기본 개념

c로 공부한다.

## 시스템 생명 주기 (system life cycle)

- 요구사항(requirement) : 프로젝트 목적을 정의한명세들의 집합. 입력->결과 정보

- 분석(analysis) : 문제를 실제 다룰 수 있을 정도의 작은 단위들로 나눈다.
  - Bottom-Up & Top-DOWN
  
- 설계(design) : 프로그램이 필요로 하는 자료 객체와 연산 관점에서 시스템 접근 

- 코딩(coding) : 자료 객체 표현 선택, 연산 알고리즘 작성

- 검증(verification): 정확성 증명,테스트,오류 제거

## 포인터

포인터 : 메모리의 주소

- 중요 연산자

  - \& : 주소 연산자
  
  - \* : 역참조 연산자
  
- 포인터는 음이 아닌 정수 (메모리 주소) => 포인터에 대한 사칙연산 가능

- 가리키는 자료형에 따라 포인터의 크기 달라짐

- 널 포인터(null pointer) : 아무것도 가리키지 않음, 거짓(False)으로 해석

  - 검사 : if(pointer == NULL), if(!pointer)
  
## 포인터 예시  

a는 정수 변수고, pa는 정수에 대한 포인터.

간단히 int* 를 정수에 대한 포인터 타입이라 생각하면 된다!
  
![image](https://user-images.githubusercontent.com/33515697/43755158-968e6a52-9a49-11e8-99d1-9ab7ebc649ac.JPG)

![image](https://user-images.githubusercontent.com/33515697/43755159-98e0c4a8-9a49-11e8-9c11-3a9b00797399.JPG)


## 동적 메모리 할당

실행 중 새로운 메로리 할당 (heap 기법). malloc 이용한다.

- malloc : 필요한 양의 공간을 요구. 할당된 메모리 필요 없는 경우(or 프로그램종료) free 해야함  (#include <stdlib.h> 필요)
  
  - 호출 : malloc(필요한 메모리 크기) 
  </br> 
  
  ```C
  pi = (int*) malloc(sizeof(int)); 
  ```

  - 요구 크기 메모리 영역에 대한 **시작 주소 포인터(void*)** 리턴
  
  - 요구 공간 사용 불가능 시 NULL 포인터 리턴
  
  - free : 메모리 해제
    - 호출: free(포인터)
  
  
## malloc 예시

- 기본 형태

  ![image](https://user-images.githubusercontent.com/33515697/43580311-f5f750ca-968f-11e8-8b0b-7a9a40fd860d.png)

- 개선 (메모리 부족으로 실패할 경우 대비 => null pointer 대비)

  ![image](https://user-images.githubusercontent.com/33515697/43580395-50aaf4b8-9690-11e8-9d24-13d7f902a34c.png)





  


