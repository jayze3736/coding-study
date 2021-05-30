<pre>
<code>
/*
이번에 복습할 내용은 클래스, 생성자, 소멸자, 인라인 함수, 오버 헤드, 상속 지정자, 
멤버함수 선언, 필드 선언 방법

먼저 객체란, 현실세계의 사물을 프로그램으로 본 뜬 것을 말한다. 클래스는 객체를 만드는 데 필요한 설계도를 의미하며
객체를 프로그램상에 실체화한 것을 인스턴스라고 한다.

생성자 함수는 클래스에서 객체를 생성하는 시점에 호출되는 함수를 의미하며 객체 내부의 필드를 초기화하거나
또는 사전에 필요한 파일 또는 실행해야하는 작업을 수행한다.

반대로 소멸자는 객체가 소멸될때 실행되는 함수를 의미한다.

함수의 호출과정에는 오버헤드라는 것이 존재한다. 함수를 호출할때 다음과 같은 과정을 밟는다.
함수 호출 -> 함수가 호출된 주소를 저장 -> CPU에서 레지스터값을 받음 -> 함수의 호출정보를 스택에 저장 
-> 함수 실행 -> 함수의 리턴값을 임시 저장소에 저장 -> 저장한 레지스터값 CPU에 복귀 -> 돌아갈 주소를 알아내어 리턴
함수 호출 과 함수 실행이 되는 과정을 제외한 나머지 과정, 즉 CPU가 연산을 처리하고 활동하는데 걸리는 시간을 오버헤드라고한다.
그런데 매 함수 호출과정에 이러한 오버헤드가 붙는다면 짧은 코드를 여러개 수행하면 오버헤드가 많아져서 시스템 효율이 떨어진다.
따라서 컴파일러에서 자체적으로 판단하여 시스템의 효율을 떨어뜨릴 수 있는 함수 호출을 다른 명령줄로 바꾸어서 컴파일하도록 하는
함수 선언의 결과를 인라인 함수라고 한다.

멤버 함수는 클래스내에서 선언과 정의를 동시에 가능하지만 구현부와 선언부로 나누어서도 가능하다. 보통 헤더파일과 cpp 파일로 나누어서
코드를 작성할때 필요하다.

private, protected, public 상속 지정자를 사용하는 이유는 접근 되지않아야 하는 데이터를 보호하기 위함이다. 예를 들면 게임 내에서
절대 수정되지말아야하는 값인 NPC 이름, 도감 번호, 메뉴 이름 등 외부에서 접근하지않도록 해야하는 값을 상속 지정자로 보호한다.

*/

/*
1. 보통 클래스에 생성자를 작성하지않으면 자동으로 컴파일러가 매개 변수가 없는 기본 생성자를 생성한다.
그러나 사용자가 인자가 있는 생성자를 선언하고 매개 변수가 없는 생성자를 선언하지않으면 자동으로 추가하지않으므로
인자 없이 객체 생성시 컴파일 에러가 발생한다.

2. 위임 생성자: 
Circle():Circle(1,0) {
		//radius = 1;
		//centerposition = 0;
	}
생성자 호출시 다른 생성자에 인자를 추가하여 코드를 더 간단하게 만들 수 있다.


*/

#ifdef COMPILE_THIS

#include <iostream>
using namespace std;
//std는 표준 이름 공간으로 표준 라이브러리는 std라는 이름공간에 만들어져있다.

class Circle {
public:
	double radius;
	double getArea();
	int centerposition;
	Circle():Circle(1,0) {
		//radius = 1;
		//centerposition = 0;
	}

	Circle(double r, int cp) {
		radius = r;
		centerposition = cp;
	}


private:
	double pi = 3.14;


};
// 클래스에 {}끝에 ; 세미콜론이 항상 붙어야한다는점에 유의하자.


//클래스내에서 선언&정의를 동시에 하지않고 클래스 외부에서 정의할때는 범위 지정 연산자 ::를 사용하여 정의해야한다.
//(Return Type) (Class Name)::(Function Name)(){}

double Circle::getArea()
{
	return radius * radius * pi;
}



int main() {

	Circle c;
	//인자가 없는 객체는 뒤에 () 없이 작성 ㅋㅋㅋ
	Circle d(2, 5);

	cout << "Area: " << c.getArea() << " CenterPoint: " << c.centerposition << endl;
	cout << "Area: " << d.getArea() << " CenterPoint: " << d.centerposition << endl;


	
}

#endif

</code>
</pre>