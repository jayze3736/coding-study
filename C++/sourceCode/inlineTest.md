<pre>
<code>
*
inline 키워드는 일반 함수 선언 앞에 그냥 써주기만 하면 됨
컴파일러가 알아서 오버헤드를 줄이는 방향으로 코드를 바꿔서 컴파일하도록 함

*/

#include <iostream>
using namespace std;

inline int f(int x) {
	return x % 2;
}

int main() {
	int sum = 0;

	for (int i = 0; i < 10000; i++) {
		if (f(i)) {
			sum += i;
		}
	}
	cout << sum;
}
</code>
<pre>
