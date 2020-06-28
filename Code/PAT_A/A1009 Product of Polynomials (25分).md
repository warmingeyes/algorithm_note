# A1009 Product of Polynomials (25分)

题目类型：简单模拟

PS:

1. 一定在对赋值和输出有效值时对数据的边界进行限制！！！

   

AC代码：

```c++
#include<cstdio>
#include<iostream>

using namespace std;
const int maxn = 2001;

int main()
{
    int k,flag = 0;
    double num[3][maxn] = {};

    for(int i = 0; i < 2; i++)
    {
        scanf("%d", &k);
        for(int j = 0; j < k; j++)
        {
            int a;
            double b;
            scanf("%d%lf", &a, &b);
            num[i][a] = b;
        }
    }

    for(int i = 0; i < 1001; i++)
    {
        for(int j = 0; j < 1001; j++)
            num[2][i+j] += num[0][i] * num[1][j];
    }

    for(int i = 2000; i >= 0; i--)
    {
        if(num[2][i] != 0)
            flag++;
    }

    printf("%d", flag);

    for(int i = 2000; i >= 0; i--)
    {
        if(num[2][i] != 0.0)
            printf(" %d %.1lf", i, num[2][i]);
    }
    return 0;
}
```

