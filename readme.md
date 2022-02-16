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

_____
## 자료형 

 
### 정수형
| 타입 | 할당 메모리 크기 | 표현 범위 |
|---|:---:|:---:|
|short|2 bytes|-32,768 ~ 32,767|
|unsigned short | 2 bytes|0 ~ 65,535|
|int|4 bytes|-2,147,483,648 ~ 2,147,483,647|
|unsigned int|4 bytes|0 ~ 4,294,967,295|
|long|4 bytes|-2,147,483,648 ~ 2,147,483,647|
|unsigned long|4 bytes|0 ~ 4,294,967,295|
|long long | 8bytes |-9,223,372,036,854,775,808~9,223,372,036,854,775,807|
|unsigned long long |8 bytes|0~18,446,744,073,709,551,615|

### 실수형
| 타입 | 할당 메모리 크기 | 표현 범위 |
|---|:---:|---:|
|float|4 bytes | (3.4 X 10^-38) ~ (3.4 X 10^38)|
|double| 8bytes | 	(1.7 X 10^-308) ~ (1.7 X 10^308)|s

### 문자형
| 타입 | 할당 메모리 크기 | 표현 범위 |
|---|:---:|:---:|
|char | 1 bytes |  -128 ~ 127|
|unsigned char | 2bytes | 0~255|

### bool
| 타입 | 할당 메모리 크기 | 표현 범위 |
|---|:---:|:---:|
|bool| 1 bytes | 0~1|

--------
## 포인터와 참조자 
### 포인터

    void Swap(int * ptr1 , int * ptr2){
        int temp = *ptr1;
        *ptr1 = ptr2;
        *ptr2 = temp;
    } # Call - by - reference

### 참조자

    void Swap(int &ref1 , int &ref2){
        int temp = ref1;
        ref1 = ref2;
        ref2 = temp;
    } # Call - by - reference
_____
## new & delete
### 생성 

    int * ptr = new int;
    int * arr = new int[3];

### 소멸 
    delete ptr;
    delete [].arr
____
## 열거형 (enum) 

    enum Color 
    { COLOR_BLACK,  # 0
    COLOR_RED,      # 1
    COLOR_BLUE,     # 2
    COLOR_GREEN,    # 3
    COLOR_WHITE,    # 4
    COLOR_CYAN,     # 5
    COLOR_YELLOW,   # 6
    COLOR_MAGENTA,  # 7
    };

    Color paint(COLOR_RED);
    std::cout << paint             # 1 출력 
    std::cout << color(COLOR_BLUE) # 2 출력
______
## 구조체 
###일단 페스 
______


 _______
 ## 소수 판별
 ### 단일 판별 
    def is_prime(n):
        for i in range(2, round(n ** 0.5)):
            if n % i == 0:
                return False
        return True 
### 1 ~ 10000000 복수 판별  
그 이상은 다른 알고리즘 사용해야함 
~~의 체


_______
## 출력 
### 소수점 고정
    temp = 3.123456789
    cout << fixed;
    cout.precision(6);
    cout << temp        #3.123456

## 구분자로 문자 분리
    string str;
    cin>>str;
    istringstream ss(str);
    string stringbuffer;
    vector<string> v;
    v.clear();
    while(getline(ss,stringbuffer, ':')){
        v.push_back(stringbuffer);
    }