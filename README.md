# PTA_7-21
# 求特殊方程的正整数解
# 本题要求对任意给定的正整数N，求方程 X^2 + Y^2 = N 的全部正整数解。

# 输入格式：输入在一行中给出正整数N（≤10000）。

# 输出格式：输出方程 X^2 + Y^2 = N 的全部正整数解，其中X≤Y。每组解占1行，两数字间以1空格分隔，按X的递增顺序输出。如果没有解，则输出No Solution。
```cpp
#include<iostream>
using namespace std;

int main() {
	int n;
	cin >> n;
	bool isSolution = false;

	if (n > 10000 || n <= 0) {
		cout << "No Solution" << endl;
		return 0;
	}

	for (int x = 1;x * x <= n;x++) {

		for (int y = x;y * y <= n;y++) {

			if (x * x + y * y == n) {
				cout << x << " " << y << endl;
				isSolution = true;
			}
		}
	}

	if (!isSolution) {
		cout << "No Solution" << endl;

	}
	return 0;
}