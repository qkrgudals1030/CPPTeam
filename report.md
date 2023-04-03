### 1. 도형 클래스 CPoly로부터 두 정수를 상속 받고, 면적 계산하는 과정을 함수 오버라이딩을 통해 다형성(Polymorphism) 을 구현하시오. 

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

 

### 2. 사각형의 가로 세로를 변수로 가지는 클래스를 정의하고, 가로와 세로 값을 출력하는 << 오퍼레이터를 오버로딩 하시오.

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

###소감
20191125 박형민 

