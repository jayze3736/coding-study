<pre>
<code>
/*
생성자는 객체 생성시 호출되며 필요한 작업을 사전에 하는데 호출되는 함수이다. 반대로
소멸자는 객체 소멸시 호출되며 작업을 마치는데 호출되는 함수이다.
이때 소멸자의 호출 순서는 LIFO 처럼 최근에 생성된 것이 먼저 호출된다.
주의!!!!!!!!!!!!!!!!!!!) 생성자 및 소멸자는 무조건 public으로 선언되어야 한다.
*/

/*
실행결과는 6 5 4 3 2 1 순으로 실행됨, 최근에 생성된 객체부터 소멸자가 실행됨
*/

#ifdef COMPILE_THIS

#include <iostream>
using namespace std;

void f();


class CallbyOrder {
	int index;
public:
	CallbyOrder() {}
	CallbyOrder(int i) {
		index = i;
	}
	~CallbyOrder() {
		cout << "My index is " << index << endl;
	}

};

CallbyOrder c1(1);
CallbyOrder c2(2);

int main() {
	CallbyOrder c3(3);
	CallbyOrder c4(4);

	f();
}

void f() {
	CallbyOrder c5(5);
	CallbyOrder c6(6);

}

#endif

</code>
<pre>
