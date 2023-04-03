## 1. 도형 클래스 CPoly로부터 두 정수를 상속 받고, 면적 계산하는 과정을 함수 오버라이딩을 통해 다형성(Polymorphism) 을 구현하시오. 

~~~
#include<iostream>
using namespace std;
class CPoly{
protected:
    int w, h;
public:
    virtual int Area()=0;
};

class CRect: public CPoly{
public:
    CRect(int a, int b){w=a; h=b;}
    int Area() override {return(w*h);}
};
class CTri: public CPoly{
public:
    CTri(int a, int b){w=a; h=b;}
    int Area() override {return(w*h/2);}
};
int main(){
    CRect r(4,3);
    CTri t(4,3);
    CPoly* p=NULL;
    p=&r;    cout << p->Area() << endl;
    p=&t;    cout << p->Area() << endl;
}
~~~
### 설명
 이 프로그램은 CPoly라는 기본 클래스를 정의합니다. CPoly는 w와 h라는 두 개의 데이터 멤버와 Area()라는 순수 가상 함수를 갖고 있습니다. 이렇게 함으로써 CPoly는 추상 클래스가 되며, 인스턴스화 할 수 없게 됩니다.

 CRect와 CTri라는 두 개의 파생 클래스가 CPoly에서 상속받아 정의됩니다. CRect는 너비 w와 높이 h를 갖는 직사각형을 나타내고, CTri는 밑변 w와 높이 h를 갖는 삼각형을 나타냅니다. 두 클래스 모두 Area() 함수를 구현하여 도형의 면적을 계산합니다.

 main() 함수에서는 CRect와 CTri 객체를 생성하고, CPoly 포인터를 사용하여 Area() 함수를 호출합니다. 이는 다형성을 보여주며, CPoly 포인터가 가리키는 객체의 유형에 따라 적절한 Area() 함수가 호출됩니다.
 

## 2. 사각형의 가로 세로를 변수로 가지는 클래스를 정의하고, 가로와 세로 값을 출력하는 << 오퍼레이터를 오버로딩 하시오.

~~~
#include <iostream>
using namespace std;
class CRect{
	int w, h;
public:
	CRect(int a, int b){w=a,h=b;}
    friend ostream& operator <<(ostream &os, CRect &r){
	  	os << r.w << " " << r.h;
	    return os;
    }
};
int main(){
	CRect r(2,3);
	cout << r << endl;
}
~~~

### 설명

 이 프로그램은 C++로 작성된 예제로, CRect 클래스를 정의하고, 클래스 내에 w와 h 두 개의 정수형 멤버 변수를 가지고 있습니다. CRect 클래스에는 int a와 int b를 인자로 받는 생성자가 정의되어 있습니다. 생성자에서는 w 변수에 a를, h 변수에 b를 대입합니다.

 이 예제에서는 CRect 클래스에 << 연산자를 오버로딩하여 CRect 객체를 출력할 때, w와 h 값을 출력할 수 있도록 만들어집니다. 이를 위해서, << 연산자 오버로딩 함수를 CRect 클래스의 friend 함수로 정의하고, w와 h 값을 출력하는 ostream 객체를 반환합니다.

main() 함수에서는 CRect 클래스의 객체 r을 생성하고, cout 객체를 이용해 r 객체를 출력합니다. 이때, CRect 클래스의 << 연산자가 호출되어 r 객체의 w와 h 값을 출력하게 됩니다.

### 소감

20191125 박형민 혼자서 개인으로 하는 과제보다 팀과제로 서로 코드에 대해 이야기 해보면서 이해가 되지 않는 부분에 대해서 더 쉽게 이해할 수 있었습니다. 또한 카페와 수업시간에 정리한 내용과 챗지피티를 활용해보면서 어렵게 생각했던 C++에 대해서 조금더 쉽게 접근해 볼 수 있었던거 같습니다. 이러한 자료를 잘활용하여 C++을 자료를 참고하지 않고도 스스로 코딩을 할 수 있도록 열심히 공부해 보겠습니다. C++화이팅!!!!! 

20191122 김준영 이번 팀 프로젝트를 통해 수업 시간에 교수님께서 가르쳐 주신 상속과 오퍼레이터 오버 로딩을 다시 배워보았는데
처음 상속과 오퍼레이터 오버 로딩을 배울 때는 이해가 잘 안되었지만 형민이와 준영이가 옆에서 많이 도와주고 교수님께서 알려주신 chat gpt를 활용하여 공부해 본 결과
처음 배울 때보다 더 많이 이해가 된 거 같다 하지만 완벽히 이해하기 위해서는 노션과 깃허브에 수업 시간에 배운 것을 정리하고
cpp 카페를 참고하면서 손으로 직접 적어가면서 외우면 완벽히 나만의 것으로 만들수 있을것 같다.

20191135 천준영 친구들과 함께 상속과 오퍼레이터 오버로딩에 관한 예제를 작성하면서 서로 부족한 부분에 대해서 채워주고 설명해 주었습니다. 팀 프로젝트를 진행하면서 세명 다 모르는 것은 chat gpt에게서 정보를 얻으면서 수업시간에 배운 내용들을 다시 한번 배우는 좋은 시간이었습니다. 감사합니다.

