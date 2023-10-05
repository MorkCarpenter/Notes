# KMP
>一个人能走的多远不在于他在顺境时能走的多快，而在于他在逆境时多久能找到曾经的自己  ———————— KMP

不想写笔记，如果我忘了那就再学一遍。
```cpp
#include<iostream>
using namespace std;
char P[100010], S[1000005];
int ne[100010];
int n, m;
int main() {
	ios::sync_with_stdio(false);
	cin >> n >> P + 1 >> m >> S + 1;
	for (int i = 2, j = 0; i <= n; ++i) {
		while (j && P[i] != P[j + 1])j = ne[j];
		if (P[i] == P[j + 1])j++;
		ne[i] = j;
	}
	for (int i = 1, j = 0; i <= m; i++)
	{
		while (j && S[i] != P[j + 1]) j = ne[j];
		if (S[i] == P[j + 1]) j++;
		if (j == n)
		{
			printf("%d ", i - n);
			j = ne[j];
		}
	}

	return 0;
}
```

