# C++ 정리 

## 입출력
### C 스타일 입출력 

    int a
    scanf("%d",&a)               #입력
    printf(a)                    #출력

### C++ 스타일 입출력

    int a  
    std::cin >> a;               #입력
    std::cout << a << std::endl; #출력

### C++ 문자열 입출력

    char a[200];
    std::cin >> a;               #입력
    std::cout << a << std::endl; #출력
_____
## 오버로딩 
    
    int Func(int a){
        return a;
    }
    int Func(int a , int b){
        return a+b;
    }

    std::cout << Func(5) << std::endl;     #5 출력
    std::cout << Func(5 ,5) << std::endl;  #10 출력 
______
## 함수 디폴트 값 선언 

    int Func(int a = 5 , int b = 6){
        return a+b;
    }
    std::cout << Func() << std::endl;      # 11 출력 
    std::cout << Func(10) << std::endl;    # 16 출력
    std::cout << Func(10,10) << std::endl; # 20 출력 


    int Func(int a = 5 , int b ) #에러 사용 불가 

_______
## 인라인 함수 
### C언어 매크로 함수

    #define SQUARE(x) ((x)*(x))
    
    std::cout << SQUARE(5) << std::endl;     # 25 출력 
    std::cout << SQUARE(3.15) << std::endl;  # 9.9225 출력
### C++ 인라인 함수 

    inline int SQUARE(int x){
         return x*x;
    }
    std::cout << SQUARE(5) << std::endl;     # 25 출력 
    std::cout << SQUARE(3.15) << std::endl;  # 9 출력 

### C++ 템플릿

    template <typename T>
    inline T SQUARE(T x){
        return x*x
    }
    std::cout << SQUARE(5) << std::endl;     # 25 출력 
    std::cout << SQUARE(3.15) << std::endl;  # 9.9225 출력 


## 변수 


--------

 ### 변수 선언
-전역 변수(Global variable) : 전역 변수는 함수 외부에서 선언되며 범위(스코프)에 구애받지 않고 프로그램 전체에서 접근할 수 있는 변수이다.

-지역변수(Local variable) : 지역변수는 함수 내보에서 선언되며 해당 함수가 호출되어 실행되면 생성되었다가 함수가 종료되면 사라지는 변수이다. 해당 범위 내에서만 사용 가능하며 다른 함수에서는 접근이 불가하다.

-------
### 변수 타입 
**정수형**
| 타입 | 할당 메모리 크기 | 표현 범위 |
|---|:---:|---:|
| char | 1bytes|-128 ~ 127|
|unsigned char | 1bytes |0~255
|short|2 bytes|-32,768 ~ 32,767|
|unsigned short | 2 bytes|0 ~ 65,535|
|int|4 bytes|-2,147,483,648 ~ 2,147,483,647|
|unsigned int|4 bytes|0 ~ 4,294,967,295|
|long|4 bytes|-2,147,483,648 ~ 2,147,483,647|
|unsigned long|4 bytes|0 ~ 4,294,967,295|
|long long | 8bytes |-9,223,372,036,854,775,808~9,223,372,036,854,775,807|
|unsigned long long |8 bytes|0~18,446,744,073,709,551,615|

**실수형**
| 타입 | 할당 메모리 크기 | 표현 범위 |
|---|:---:|---:|
|float|4 bytes | (3.4 X 10^-38) ~ (3.4 X 10^38)|
|double| 8bytes | 	(1.7 X 10^-308) ~ (1.7 X 10^308)|

**문자형**
| 타입 | 할당 메모리 크기 | 표현 범위 |
|---|:---:|---:|
|char | 1 bytes |  2^-7 ~ (2^7 - 1)|
|unsigned char | 2bytes | 0 ~ 2^8

**bool**
| 타입 | 할당 메모리 크기 | 표현 범위 |
|---|:---:|---:|
|bool| 1 bytes | 0~1|

--------

### 변수 초기화
<br>방법 1  

    int a = 100;

방법 2 

    int a;
    a = 100;

방법3 

    int a(100);
--------
### 변수 이름 규칙 
1.   대소문자 구분
2.   int , float 와 같은 키워드를 변수명으로 사용 불가
3.   변수의 첫 번째 문자는 반드시 일반 문자 또는 _ 사용해야함 
4.   첫 문자 다음에는 일반 문자 숫자 그리고 특수문자 사용 가능 
