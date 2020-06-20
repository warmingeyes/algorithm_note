# A1046 Shortest Distance (20分)

题目类型：简单模拟

PS：

1. 数组要开的足够大！
2. 直接在`distance`中存每个节点的长度进行遍历，测试点2会超时，因为magnitude太大了。需要对长度进行前缀价格处理！



AC代码：

```c++
#include<cstdio>
#include<iostream>
#include<algorithm>

using namespace std;

const int maxn = 100010;

int result(int x[], int m, int n, int k)
{
    int flag = 0;
    flag = x[n-1] - x[m-1];

    return min(flag, k - flag);

};


int main()
{
    int n;
    scanf("%d", &n);
    int distance[maxn], sum = 0;
    for(int i = 1; i <= n; i++)
    {
        scanf("%d", &distance[i]);
        sum += distance[i];
        distance[i] = sum;
    }

    int m;
    scanf("%d", &m);
    for(int i = 0; i < m; i++)
    {
        int a,b;
        scanf("%d %d", &a, &b);
        int c = min(a,b);
        int d = max(a,b);
        printf("%d", result(distance, c, d, sum));
        if(i != m -1)
            printf("\n");
    }

    return 0;
}

```

