eference (참조자)

Reference란?

    변수는 할당된 메모리 공간에 붙여진 이름이며, 이름을 통해 메모리 공간에 접근이 가능하다.  
    Reference는 직접 메모리 공간을 할당할 수 없으며, 메모리 공간에 할당된 변수로부터 선언될 수 있다. (변수와 메모리 주소가 같다.)
    즉, Reference는 변수가 또 하나의 이름을 가지고 있는 별칭같은 존재이다.  



Reference와 Variable의 차이점

- NULL 참조자

    Reference는 NULL reference로 선언 할 수 없으며,  대입 및 비교 연산을 할 수 없다.
        ex) Test &test = NULL   //에러
        test = NULL              //에러
        if(NULL != test)        //에러
    
    Variable은 NULL reference로 선언 할 수 있으며, 대입연산을 할 수 있다. 하지만 비교 연산을 할 수 없다.
        ex) Test test = NULL    //성공
        test = NULL            //성공
        if(NULL != test)       //에러




Reference와 Pointer의 차이점

- NULL 참조자

    Reference는 NULL reference로 선언 할 수 없으며,  대입 및 비교 연산을 할 수 없다.
        ex) Test &test = NULL   //에러
        test = NULL              //에러
        if(NULL != test)        //에러
    
    Pointer는 null reference로 선언 할 수 있으며, 대입 및 비교 연산을 할 수 있다.
        ex) Test *test = NULL    //성공
        test = NULL              //성공
        if(NULL != test)        //성공

- 참조 대상

    Reference는 Instance를 직접 참조한다.
    Pointer는 Address를 입력받아 참조한다.

- 참조 대상 변경

    Reference는 한번 참조한 대상을 변경 할 수 없다.
        ex) Test test;
        Test &test_1 = test;
        Test test_2;
        test_1 = test_2;
    가 되더라도 test_1이 참조하고 있는 변수는 test이며, test는 test_2의 값을 지니고 있을 뿐이다.
    Pointer는 참조 대상을 변경 할 수 있다. 




Reference를 사용하는 이유?

    Pointer와 Reference는 NULL을 사용할 수 있는지 없는지로 비교를 하였다. 
    하지만 Pointer는 그보다 자유도가 높아 유저가 직접 메모리에 접근하기도 쉽고 메모리를 해제할 수 도 있다. 이 때문에 유저가 Pointer관리를 잘 해주지 않으면 원하지 않는 assert가 발생할 수 도 있다. 
    반면, Reference는 Pointer보다 자유도는 떨어지지만 위험도를 줄여 줄수 있다. 메모리 관리 측면에서도, 더 이상 메모리를 참조하는 Variable 또는 Reference가 없으면 메모리는 해제가 된다. 

    Reference는 Pointer의 위험성은 줄여주지만 Pointer처럼 사용할 수 있도록 고안되어 탄생한 것 같다.
