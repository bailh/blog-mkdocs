---
title: AcWing 3446. 整数奇偶排序
tags:
- AcWing
- 算法与数据结构
---
## AcWing 3446.整数奇偶排序

### 题目

输入 10个整数，彼此以空格分隔。
重新排序以后输出(也按空格分隔)，要求:
先输出其中的奇数,并按从大到小排列；
然后输出其中的偶数,并按从小到大排列。

---------------------------------------------------

输入格式
任意排序的 10个整数，彼此以空格分隔。
输出格式
按照要求排序后输出，整数之间由空格分隔。
数据范围
输入整数取值范围 [0,100]。

```c++
输入样例：
4 7 3 13 11 12 0 47 34 98
输出样例：
47 13 11 7 3 0 4 12 34 98

## 
```

思路

while(cin>>a)输入用数组存起来；

sort（）排序

sort(  greater <int> ()) 从大到小

### 题解

``` C++
==#include <bits/stdc++.h>==
==using namespace std;==
==int main()==
=={==
    ==int ans = 0, res = 0;==
    ==int a, b[100], c[100];==
    ==memset(b,0,sizeof(b));==
    ==memset(c,0,sizeof(c));==

​    for(int i = 0; i < 10; i++)
​    {
​        cin >> a;
​        if(a % 2 == 0) b[ans++] = a;
​        if(a % 2 != 0) c[res++] = a;
​    }
​    sort(c, c + res, greater<int>());
​    sort(b, b + ans);
​    for(int i = 0; i < res; i++) cout << c[i] << ' ';
​    for(int i = 0; i < ans; i++) cout << b[i] << ' ';
​    return 0;

==}==
```

### <a name="test">收获</a>

C++ 中对**内存**的要求很严格，一开始没有如下代码，导致出现*段错误*，后来查询，知道

<u>主函数的变量要进行初始化</u>

```
==memset(b,0,sizeof(b));==
==memset(c,0,sizeof(c));==
```

另外，如果不会greater<int>()可以使用for(int i  = 10; i > 0; i --)同样实现[从大到小](#test)的排序输出
