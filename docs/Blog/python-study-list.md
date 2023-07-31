# 列表

```python
inp = input("请输入你的名字")
```

    请输入你的名字李思涵

```python
print(inp)
```

```python
a
fa
asfasf
```

    李思涵

```python
inp = input("数字")
```

    数字3

```python
print(inp)
```

    3

```python
print(inp+"无语")
```

    3无语

```python
inp = int(input("再来"))
print(inp+"无语")
```

    再来6
    


    ---------------------------------------------------------------------------

    TypeError                                 Traceback (most recent call last)

    ~\AppData\Local\Temp\ipykernel_13512\1933184884.py in <module>
          1 inp = int(input("再来"))
    ----> 2 print(inp+"无语")
    

    TypeError: unsupported operand type(s) for +: 'int' and 'str'

```python
print(inp+3)
```

    9

```python
list=[1,2,3,4,5,6]
```

```python
list[0]
```

    1

```python
list[:]
```

    [1, 2, 3, 4, 5, 6]

```python
list[0:6:2]
```

    [1, 3, 5]

```python
list[0:6:-1]
```

    []

```python
list[0:6:3]
```

    [1, 4]

```python
list[-1]
```

    6

```python
list[0:6:-2] 
```

    []

```python
list[::-2]
```

    [6, 4, 2]

## 增删改查

### append在末尾添加一个新元素

```python
heros=['钢铁侠','绿巨人']
```

```python
heros.append('黑寡妇')
```

```python
heros
```

    ['钢铁侠', '绿巨人', '黑寡妇']

### extend在末尾添加几个元素

```python
heros.extend(["鹰眼","灭霸","雷神"])
```

```python
heros
```

    ['钢铁侠', '绿巨人', '黑寡妇', '鹰眼', '灭霸', '雷神']

### 可以使用:操作(切片)来代替

```python
s=[1,2,3,4,5]
```

```python
s[len(s):]=[6]
```

```python
s
```

    [1, 2, 3, 4, 5, 6]

```python
s[len(s):]=[7,8,9]
```

```python
s
```

    [1, 2, 3, 4, 5, 6, 7, 8, 9]

### insert任意位置插入元素

```python
s=[1,3,4,5]
```

```python
s.insert(1,2)
```

```python
s
```

    [1, 2, 3, 4, 5]

```python
s.insert(len(s),6)
```

```python
s
```

    [1, 2, 3, 4, 5, 6]

### remove删除指定元素(内容)

```python
heros.remove("灭霸")
```

```python
heros
```

    ['钢铁侠', '绿巨人', '黑寡妇', '鹰眼', '雷神']

```python
heros.remove("金莲")
```

    ---------------------------------------------------------------------------

    ValueError                                Traceback (most recent call last)

    ~\AppData\Local\Temp\ipykernel_4012\2787210069.py in <module>
    ----> 1 heros.remove("金莲")
    

    ValueError: list.remove(x): x not in list

### pop删除指定(位置)元素

```python
heros.pop(2)
```

    '黑寡妇'

```python
heros
```

    ['钢铁侠', '绿巨人', '鹰眼', '雷神']

```python
heros.clear()
```

```python
heros
```

    []

### 替换实际上是两步操作先删除，再插入

```python
heros=['蜘蛛侠', '绿巨人', '黑寡妇', '鹰眼', '灭霸', '雷神']
```

```python
heros[4]="钢铁侠"
```

```python
heros
```

    ['蜘蛛侠', '绿巨人', '黑寡妇', '鹰眼', '钢铁侠', '雷神']

```python
heros[3:]=["武松","林冲","李逵"]
```

```python
heros
```

    ['蜘蛛侠', '绿巨人', '黑寡妇', '武松', '林冲', '李逵']

### sort排序

```python
nums=[3,1,9,6,8,3,5,3]
```

```python
nums.sort()
```

```python
nums
```

    [1, 3, 3, 3, 5, 6, 8, 9]

### reverse排序

```python
nums.reverse()
```

```python
nums
```

    [9, 8, 6, 5, 3, 3, 3, 1]

```python
heros.reverse()
```

```python
heros
```

    ['李逵', '林冲', '武松', '黑寡妇', '绿巨人', '蜘蛛侠']

### 参数设置同样效果

```python
nums=[3,1,9,6,8,3,5,3]
```

```python
nums.sort(reverse=True)
```

```python
nums
```

    [9, 8, 6, 5, 3, 3, 3, 1]

### count查找某个元素出现的次数

```python
nums.count(3)
```

    3

### index获取索引值(第一次出现)

```python
heros.index("绿巨人")
```

    4

```python
heros[heros.index("绿巨人")]="神奇女侠"
```

```python
heros
```

    ['李逵', '林冲', '武松', '黑寡妇', '神奇女侠', '蜘蛛侠']

```python
nums=[3,1,9,6,8,3,5,3]
```

```python
nums.index(3)
```

    0

### index(x,start,end)

```python
nums.index(3,1,7)
```

    5

### copy拷贝

#### shallow copy

```python
nums_copy1=nums.copy()
```

```python
nums_copy1
```

    [3, 1, 9, 6, 8, 3, 5, 3]

```python
nums_copy2=nums
```

```python
nums_copy2
```

    [3, 1, 9, 6, 8, 3, 5, 3]

```python
nums_copy3=nums[:]
```

```python
nums_copy3
```

    [3, 1, 9, 6, 8, 3, 5, 3]

## list的* +

```python
s=[1,2,3]
```

```python
t=[4,5,6]
```

```python
s+t
```

    [1, 2, 3, 4, 5, 6]

```python
s*3
```

    [1, 2, 3, 1, 2, 3, 1, 2, 3]

## 嵌套列表

```python
matrix=[[1,2,3],[4,5,6],[7,8,9]]
```

```python
matrix=[[1,2,3],
        [4,5,6],
        [7,8,9]]
```

```python
matrix
```

    [[1, 2, 3], [4, 5, 6], [7, 8, 9]]

### 访问嵌套列表

```python
for i in matrix:
    for each in i:
        print(each)
```

    1
    2
    3
    4
    5
    6
    7
    8
    9

#### 换行

```python
for i in matrix:
    for each in i:
        print(each,end=' ')
    print()
```

    1 2 3 
    4 5 6 
    7 8 9 

```python
matrix[0]
```

    [1, 2, 3]

```python
matrix[0][0]
```

    1

```python
matrix[1][1]
```

    5

```python
matrix[2][2]
```

    9

```python
A = [0]*3
```

```python
A
```

    [0, 0, 0]

```python
for i in range(3):#从0到2
    A[i]=[0]*3
```

```python
A
```

    [[0, 0, 0], [0, 0, 0], [0, 0, 0]]

### 错误写法-虽然结果相同

```python
B=[[0]*3]*3
```

```python
B 
```

    [[0, 0, 0], [0, 0, 0], [0, 0, 0]]

```python
A[1][1]=1
```

```python
A
```

    [[0, 0, 0], [0, 1, 0], [0, 0, 0]]

```python
B[1][1]=1
```

```python
B
```

    [[0, 1, 0], [0, 1, 0], [0, 1, 0]]

#### 每个嵌套中的元素都被改变-探究(is)

```python
x = "FishC"
```

```python
y = "FishC"
```

```python
x is y
```

    True

```python
 x=[1,2,3]
```

```python
y=[1,2,2]
```

```python
x is y
```

    False

##### 可知同个位置存放，而list会开两个内存

```python
A[0] is A[1]
```

    False

```python
A[1] is A[2]
```

    False

```python
B[0] is B[1]
```

    True

```python
B[1] is B[2]
```

    True

#### A每个元素单独开辟一个空间

B每个元素始终指向同一个空间

## 变量不是盒子

```python
x=[1,2,3]
```

```python
y=x
```

### 变量的赋值与拷贝

#### 赋值不会创建新空间，是引用，拷贝则是创建新空间。不互相影响

### 浅拷贝和深拷贝

```python
x = [1,2,3]
```

```python
y=x.copy()
```

```python
y
```

    [1, 2, 3]

```python
x[1]=1
```

```python
x
```

    [1, 1, 3]

```python
y
```

    [1, 2, 3]

```python
x=[1,2,3]
```

```python
y=x[:]
```

```python
x[1]=1
```

```python
x
```

    [1, 1, 3]

```python
y
```

    [1, 2, 3]

#### 二维开始有区别

```python
x=[[1,2,3],[4,5,6],[7,8,9]]
```

```python
y=x.copy()
```

```python
x[1][1]=0
```

```python
x
```

    [[1, 2, 3], [4, 0, 6], [7, 8, 9]]

```python
y
```

    [[1, 2, 3], [4, 0, 6], [7, 8, 9]]

#### 引入深拷贝 copy.deepcopy(x)

```python
import copy
```

```python
x=[[1,2,3],[4,5,6],[7,8,9]]
```

```python
y=copy.copy(x)
```

```python
x[1][1]=0
```

```python
x
```

    [[1, 2, 3], [4, 0, 6], [7, 8, 9]]

```python
y
```

    [[1, 2, 3], [4, 0, 6], [7, 8, 9]]

```python
x=[[1,2,3],[4,5,6],[7,8,9]]
```

```python
y=copy.deepcopy(x)
```

```python
x[1][1]=0
```

```python
x
```

    [[1, 2, 3], [4, 0, 6], [7, 8, 9]]

```python
y
```

    [[1, 2, 3], [4, 5, 6], [7, 8, 9]]

## 列表推导式 [expression for target in iterable]

```python
list_1=[1,2,3]
```

```python
list_1*3
```

    [1, 2, 3, 1, 2, 3, 1, 2, 3]

```python
list
```

    list

```python
list_1=[1,2,3]
```

```python
for i in range(len(list_1)):
    list_1[i]=list_1[i]*3
```

```python
list_1
```

    [3, 6, 9]

```python
oho=[1,2,3,4,5]
```

```python
oho=[i * 2 for i in oho]
```

```python
oho
```

    [2, 4, 6, 8, 10]

### 不仅仅少写代码，speed will be faster

#### 使用C，而python使用虚拟机pvm

#### 循环是迭代替换

#### 推导式是直接创建

```python
x = [i for i in range(10)]
```

```python
x
```

    [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]

```python
x = [i + 1for i in range(10)]
```

```python
x
```

    [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]

```python
x = []
```

```python
for i in range(10):
    x.append(i+1)
```

```python
x
```

    [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]

```python
y = [c * 2 for c in "FishC"]
```

```python
y
```

    ['FF', 'ii', 'ss', 'hh', 'CC']

### ord将字符转化为Unicode编码

```python
code = [ord(c) for c in "FishC"]
```

```python
code
```

    [70, 105, 115, 104, 67]

```python
matrix=[[1,2,3],[4,5,6],[7,8,9]]
```

```python
col2=[row[1] for row in matrix]
```

```python
col2
```

    [2, 5, 8]

```python
diag = [matrix[i][i] for i in range(len(matrix))]
```

```python
diag
```

    [1, 5, 9]

```python
diag=[]
```

```python
A=[0]*3
```

```python
A

```

    [0, 0, 0]

```python
A=[[0]*3 for i in A]
```

```python
A=[0]*3
```

```python
A=[[0]*3 for i in range(3)]
```

```python
A
```

    [[0, 0, 0], [0, 0, 0], [0, 0, 0]]

```python
A=[[0]*3 for i in A]
```

```python
A
```

    [[0, 0, 0], [0, 0, 0], [0, 0, 0]]

```python
A[1][1]=1
```

```python
A
```

    [[0, 0, 0], [0, 1, 0], [0, 0, 0]]

## 列表推导式 [expression for target in iterable if condition]

```python
[i for i in range(10) if i % 2 == 0]
```

    [0, 2, 4, 6, 8]

```python
enve=[i for i in range(10) if i % 2 == 0]
```

```python
enve
```

    [0, 2, 4, 6, 8]

```python
enve=[i + 1 for i in range(10) if i % 2 == 0]
```

```python
enve
```

    [1, 3, 5, 7, 9]

### 先执行if语句再执行左侧for语句

```python
words=["Great","FishC","Brilliant","Excellent","Fantistic"]
```

```python
fwords=[w for w in words if w[0] == 'F']
```

```python
fwords
```

    ['FishC', 'Fantistic']

### 列表推导式 [expression for target in iterable if condition

                          for target in iterable2 if condition2
                          for target in iterable3 if condition3
                          --
                          for target in iterableN if conditionN]嵌套循环

```python
matrix=[[1,2,3],[4,5,6],[7,8,9]]#内存上横向存储
```

```python
flatten=[col for row in matrix for col in row]
```

```python
flatten
```

    [1, 2, 3, 4, 5, 6, 7, 8, 9]

```python
flatten = []
```

```python
for row in matrix:
    for col in row:
        flatten.append(col)
```

```python
flatten
```

    [1, 2, 3, 4, 5, 6, 7, 8, 9]

### 笛卡尔积

```python
[x + y for x in "fishc" for y in "FISHC" ]
```

    ['fF',
     'fI',
     'fS',
     'fH',
     'fC',
     'iF',
     'iI',
     'iS',
     'iH',
     'iC',
     'sF',
     'sI',
     'sS',
     'sH',
     'sC',
     'hF',
     'hI',
     'hS',
     'hH',
     'hC',
     'cF',
     'cI',
     'cS',
     'cH',
     'cC']

### 临时变量 _

```python
_ = []
```

```python
for x in "fishc":
    for y in "FISHC":
        _.append(x+y)
```

```python
_
```

    ['fF',
     'fI',
     'fS',
     'fH',
     'fC',
     'iF',
     'iI',
     'iS',
     'iH',
     'iC',
     'sF',
     'sI',
     'sS',
     'sH',
     'sC',
     'hF',
     'hI',
     'hS',
     'hH',
     'hC',
     'cF',
     'cI',
     'cS',
     'cH',
     'cC']

```python
[[x,y] for x in range(10) if x % 2 == 0 for y in range(10) if y % 3 == 0]
```

    [[0, 0],
     [0, 3],
     [0, 6],
     [0, 9],
     [2, 0],
     [2, 3],
     [2, 6],
     [2, 9],
     [4, 0],
     [4, 3],
     [4, 6],
     [4, 9],
     [6, 0],
     [6, 3],
     [6, 6],
     [6, 9],
     [8, 0],
     [8, 3],
     [8, 6],
     [8, 9]]

```python
_ = [];
```

```python
for x in range(10):
    if x % 2 == 0:
        for y in range(10):
            if y % 3 == 0:
                _.append([x,y])
```

```python
_
```

    [[0, 0],
     [0, 3],
     [0, 6],
     [0, 9],
     [2, 0],
     [2, 3],
     [2, 6],
     [2, 9],
     [4, 0],
     [4, 3],
     [4, 6],
     [4, 9],
     [6, 0],
     [6, 3],
     [6, 6],
     [6, 9],
     [8, 0],
     [8, 3],
     [8, 6],
     [8, 9]]

## KISS原则:Keep It Simple & Stupid

```python

```
