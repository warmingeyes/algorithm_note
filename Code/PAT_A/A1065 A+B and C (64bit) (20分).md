# A1065 A+B and C (64bit) (20分)

题目类型：简单模拟

PS:

1. 只有没有其他输出时，`0 0`及`-2 0`作为`0 0`输出

AC代码：

```c++
#include<cstdio>
#include<iostream>

using namespace std;

int main()
{
    int x, y;
    int flag = 0;
    while(scanf("%d%d", &x, &y) != EOF)
    {

        if(x * y == 0 && flag == 0)
            printf("0 0");
        else if(x * y != 0 && flag != 0)
            printf(" %d %d", x * y, y-1);
        else if(x * y != 0 && flag == 0)
            printf("%d %d", x * y, y-1);

        flag = 1;

    }

    return 0;
}
```

