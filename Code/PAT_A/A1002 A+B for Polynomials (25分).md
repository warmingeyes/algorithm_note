# A1002 A+B for Polynomials (25分)

题目类型：简单模拟



AC代码：

```c++
#include<cstdio>
#include<iostream>

using namespace std;

const int maxn = 1005;

int main()
{
    double num[maxn] = {};

    for(int i = 0; i < 2; i++)
    {
        int k;
        scanf("%d", &k);
        for(int j = 0; j < k; j++)
        {
            int a;
            double b;
            scanf("%d %lf", &a, &b);
            num[a] += b;
        }
    }

    int exist = 0;

    for(int i = 0; i < maxn; i++)
    {
        if(num[i] != 0)
            exist++;
    }

    printf("%d", exist);

    for(int i = maxn - 1; i >= 0; i--)
    {
        if(num[i] != 0.0)
            printf(" %d %.1f", i, num[i]);
    }

    return 0;
}
```

