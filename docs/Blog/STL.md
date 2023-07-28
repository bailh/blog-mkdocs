---
title: c++的STL
top: 6
descripton: c++的STL具体用法
tag: STL
categories: 算法
---

## sort排序

c++的STL具体用法

### 用法一

```c++
int a[] = {15,4,3,9,7,2,6};

sort(a,a+7);
```

### 用法二 -从大到小

```c++
int a[] = {15, 4, 3, 9, 7, 2 ,6};

sort(a+1,a+4,greater<int>());
```

<!-- more -->

### 用法三-结构体

sort(数组名+n1，数组名+n2,排序规则结构名());

排序规则结构的定义方式

```c++
struct 结构名

{

     bool operator()( const T & a1,const T & a2) const{

//若a1在a2前面，则返回true

//eles返回false

}

}
```
