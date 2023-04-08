<h2>전위 ++ 연산자 오버로딩</h2>

``` 
#include <iostream> 
using namespace std; 

class MyClass {
public:
    MyClass(int value) : m_value(value) {}
    MyClass& operator++() {
        ++m_value;
        return *this;
    }
    void display(){
        cout << "Value : " << m_value << endl; 
    }
private:
    int m_value;
};

int main(){
    MyClass m(10); 
    ++m; 
    m.display(); 
    
    return 0; 
}


```

전위 ++ 오버로딩을 구현하였습니다. MyClass 클래스를 만들고 오퍼레이터 오버로딩을 통해서 전위 ++를 
MyClass 객체에서도 사용할 수 있게되었습니다. 

<h2>후위 ++ 연산자 오버로딩</h2>

```


#include <iostream> 

using namespace std; 

class MyClass {
public:
    int value;

    MyClass(int v) : value(v) {}

    // 후위 증가 연산자 오버로딩
    MyClass operator++(int) {
        MyClass temp(value);
        value++;
        return temp;
    }
    void display(){
        cout << "value : " << value << endl; 
    }
};

int main(){
    MyClass obj(10);
    obj++; // obj의 값을 1 증가시키고, obj 이전의 값을 result에 저장
    
    obj.display(); 
    return 0; 
}



```



++ 후위연산자 오버로딩을 구현하였습니다. MyClass를 만들고 오퍼레이터 오버로딩을 통해 
MyClass 객체에서 ++를 사용할 수 있도록 하였습니다. ++를 사용하면 value의 값이 1 증가한 객체를 반환합니다.

<h2>stack 생성과 출력</h2>



```


#include <iostream>
#include <stack>
using namespace std;

int main()
{
    stack<int> s; //템플릿<> int로 사용 //
    s.push(10);
    s.push(20);
    s.push(30);
    s.push(40);
    s.push(50);
    // 스택 s에 데이터 저장 //
 
 while (!s.empty()) {
        cout << s.top() << " "; s.pop();
        // 각 스택의 내용을 top() 함수를 사용하여 가져오고, // 
        // pop() 함수를 사용하여 스택에서 데이터를 제거 //
    }
    return 0;
}




```


<h2>자료구조 예제</h2>



```


#include <iostream>
#include <queue>

int main() {
    std::queue<int> myQueue; // 정수형 큐 생성

    myQueue.push(1); // 큐에 1 추가
    myQueue.push(2); // 큐에 2 추가
    myQueue.push(3); // 큐에 3 추가

    while (!myQueue.empty()) { // 큐가 비어있지 않을 동안
        int frontValue = myQueue.front(); // 큐의 맨 앞 원소 조회
        std::cout << frontValue << " "; // 큐의 맨 앞 원소 출력
        myQueue.pop(); // 큐의 맨 앞 원소 제거
    }
    std::cout << std::endl; // 줄바꿈

    return 0;
}



```



C++의 STL을 이용하여 자료구조 큐를 구현하였습니다. 
큐에 1,2,3을 추가한 뒤 큐의 제일 앞의 원소를 출력하고 제거하는 예제를 작성하였습니다.

<h2>알고리즘 예제</h2>



```



#include <iostream>
#include <algorithm> // std::sort 사용을 위한 헤더

int main() {
    int arr[] = {3, 1, 4, 1, 5, 9, 2, 6, 5, 3, 5}; // 정수형 배열 생성

    std::sort(arr, arr + 11); // 배열의 첫 번째 원소와 마지막 원소를 지정하여 정렬

    for (int i = 0; i < 11; i++) {
        std::cout << arr[i] << " "; // 정렬된 배열 출력
    }
    std::cout << std::endl; // 줄바꿈

    return 0;
}



```



C++ 의 STL을 활용하여 정렬 알고리즘을 구현하였습니다. 
정렬되어있지 않은 정수형 배열의 원소를 정렬하고 출력하는 예제를 작성하였습니다. <br>  
토의 : STL의 자료구조와 알고리즘에는 어떤 것이 있는지를 토의하였습니다. 
먼저 자료구조의 경우에는 수업시간에 배웠던 stack 외에도 큐와 벡터, 리스트 등 다양한 자료구조가 있었습니다. 
C++의 STL을 통해 쉽고 간편하게 자료구조를 구현할 수 있다는 사실에 대해서 알 수 있었습니다. 
큐는 스택과 함께 많이 쓰이는 자료구조입니다. 따라서 자료구조 예제로써 큐를 구현하게되었습니다. 
또한 STL을 사용하여 다양한 알고리즘을 구현할 수 있습니다. 
알고리즘의 경우 정렬, 검색, 순열과 조합 등 다양한 알고리즘을 STL로 구현할 수 있습니다.
알고리즘을 직접 코드로 구현할 필요가 없이 라이브러리 형태로 불러오는 것이기 때문에 
간단하고 쉽게 알고리즘을 구현하여 사용할 수 있다는 장점이 있습니다. 
다양한 알고리즘 중 가장 기본적인 정렬 알고리즘을 예제로 작성하기로 하였습니다. 

<br> <br> 

<h2>C++의 주요특징과 토의</h2>


객체 지향 프로그래밍
컴파일 언어
정적 타입
메모리 관리
풍부한 라이브러리
다중 패러다임 지원
연산자 오버로딩
예외 처리
템플릿
포인터와 참조
네임스페이스
상수와 매크로
함수 오버로딩
스마트 포인터
다중 상속
정적 멤버
참조자
프렌드
키워드
포인터 연산 //20

위의 C++ 특징들 중 두가지를 가지고 팀원과 토의를 진행했습니다.
첫째는 다중 상속의 장단점입니다. 
다중 상속은 클래스로부터 상속을 받아 사용하기에 코드의 재사용성이 
높고, 다양한 인터페이스를 구현할 수 있다는 장점이 있지만
상속 그래프가 복잡해지면 코드의 가독성이 떨어져 보이는 결과가 
나올 수도 있기에 유지보수가 어려워질 수 있다는 의견도 나왔습니다. 
그러므로 다중 상속은 여러 장점도 있지만 사용시에 주의가 필요하며 
코드의 가독성을 고려하며 사용해야한다는 결론이 나왔습니다.

두번째는 객체 지향 프로그래밍(OOP)에 대해 토의를 진행했습니다.
객체 지향 프로그래밍은 프로그램을 객체(Object)라는 기본적인 프로그래밍 단위로 취급하고
객체들 간의 상호작용을 중심으로 프로그램을 설계 및 구현하는 명령형 프로그램이며
현재 배우고 있는 C++을 포함, Java, Python 등에 사용됩니다.
캡술화, 상속, 다형성 등 많은 특징과 장점들을 가지고 있지만 코드의 복잡성 등 단점또한 존재하고
그러다보니 초기 프로그래밍 방식인 절차적 프로그래밍(PP)의 간단하고 직관적인 구조를 
선호하는 사람들도 여전히 존재하고 있습니다.
토의를 진행하며 두 프로그래밍 방식 사이에서 프로젝트의 요구사항, 또는 개발 환경에 따라 
적절한 프로그래밍 방식을 사용하는 것이 중요하다는 결론이 나올 수 있었습니다.

