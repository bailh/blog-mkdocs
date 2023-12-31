---
title: Python编程基础
tags:
 - Python
---

## Page1：函数输入与输出

### 输出函数

```python
print('输出单个字符串')
```

输出单个字符串

```python
print('输出','多个信息','用，隔开')

```

输出 多个信息 用，隔开

```python
print('设置','多个信息','的连接符',sep='o')
```

设置o多个信息o的连接符

### 输入函数

```python
input() #直接调用函数就可以输入
```

a
    'a'

```python
input('也可以输入提示信息，提示信息不被录入') 

```

也可以输入提示信息，提示信息不被录入你好
'你好'

### 格式化输出

```python
print('%f' % 1.11163)  # 默认保留6位小数
```

1.111630

```python
print('%.1f' % 1.8)  # 取1位小数
```

    1.8

```python
print('%.3e' % 1.1167)  # 取3位小数，用科学计数法
```

    1.117e+00

```python
print('%.7g' % 9999.5465)  # 取7位有效数字 可以看到按照四舍五入来的
```

    9999.547

### {} 和 format的格式控制

```python
print('我叫{}，今年{}岁。'.format('陈昱杰', 19))
# 省略字段名传递位置参数

```

我叫陈昱杰，今年19岁。

```python

print('身高{0}，家住{1}。'.format(180, '十堰'))
# 通过数字形式的简单字段名传递位置参数

```

身高180，家住十堰。

```python
print('我姐姐已经{work}，今年{age}岁。'.format(work = "毕业了", age = '22'))
# 使用变量名形式的简单字段名传递关键字参数
```

我姐姐已经毕业了，今年22岁。

## Page12：字符串

### 字符串的基本操作

#### ' ' 或者 ""

#### 如果是多行的就用''''''

```python
str1='字符串的创建'
str2="另一种方法"
str3='''换行字符串
的创建'''
```

```python
print(str1,str2,str3,sep='\n************\n')
```

字符串的创建
    ************
    另一种创建方法
    ************
    换行字符串
    的创建

```python
print(str1+str2)
# 合并字符串 +
print(str1 * 2 )
# 复制字符串 * 
print(str1.replace('创建','构建'))
# 修改字符串 replace('a', 'b') 用 a 来replace b
print(str1.find('创建'))
# 查找特定字符 可以看到以第一个位置为准
```

字符串的创建另一种方法
    字符串的创建字符串的创建
    字符串的构建
    4

### 字符串切片

```python
str1[2]
# 切取单个元素 注意从0开始的
```

    '串'

```python
#切取完整对象 实际是利用缺省来切取的
print(str1[:]) #从左往右
print(str1[::])   #从左往右
```

#### k > 0

#### k < 0

```python
print(str1[::-1])#从右往左
```

    字符串的创建
    字符串的创建
    建创的串符字

```python
## start_index和end_index全为正（+）索引的情况 
#str1='字符串的创建'
#str2="另一种方法"
#str3='''换行字符串
#的创建'''
```

#### 左闭右开

```python
print(str1[2:4]) #step=1，从左往右取值，start_index=2到end_index=4同样表示从左往右取值。
print(str1[:4])  #step=1，表示从左往右取值，而start_index省略时，表示从端点开始
       #因此这里的端点是“起点”，即从“起点”值0开始一直取到end_index=4（该点不包括）。
print(str1[:4:-1])#step=-1，从右往左取值，而start_index省略时，表示从端点开始
        #因此这里的端点是“终点”，即从“终点”值9开始一直取到end_index=4（该点不包括）。
print(str1[4:])   #step=1，从左往右取值，从start_index=4开始，一直取到“终点”值4。
print(str1[6::-1]) #step=-1，从右往左取值，从start_index=4开始，一直取到“起点”0。
```

    串的
    字符串的
    建
    创建
    建创的串符字

```python
## start_index和end_index全为负（-）索引的情况 
```

```python
#str1 = "  字  符  串    的  创  建"
#          0   1  2     3   4   5
#         -6  -5  -4   -3  -2  -1
```

```python
print(str1[-1:-6:-1])  #step=-1，从右往左取值，start_index=-1到end_index=-6同样是从右往左取值。
print(str1[-6:-1])  #step=1，从左往右取值，而start_index=-6到end_index=-1同样是从左往右取值。
print(str1[:-4]) #step=1，从左往右取值，从“起点”开始一直取到end_index=-4（该点不包括）。
print(str1[:-6:-1]) #step=-1，从右往左取值，从“终点”开始一直取到end_index=-6（该点不包括）。
print(str1[-4:]) # step=1，从左往右取值，从start_index=-4开始，一直取到“终点”。
print(str1[-4::-1]) #step=-1，从右往左取值，从start_index=-4开始，一直取到“起点”。 
print(str1[-4:-2:-1]) #这样就会为空 不输出
```

    建创的串符
    字符串的创
    字符
    建创的串符
    串的创建
    串符字

## Page13：字符串的相关函数使用

```python
S='  aa!bb!cc!dd!EE  '
#创建一个字符串
```

```python
S.split('!')
#使用!分割字符串 split
```

    ['  aa', 'bb', 'cc', 'dd', 'EE  ']

```python
S.strip()
#删除字符串的空格 strip()
```

    'aa!bb!cc!dd!EE'

```python
print(S.isalnum())
#字符串含有**数字和字母**以外的字符,判断为False isalnum
print('aabbccddEE'.isalnum())
#字符串只有数字和字母,判断为True isalnum
```

    False
    True

```python
S.count('!')
#统计字符串中!字符的个数
```

    4

```python
S.count('!',2,6)
#统计索引在2:6的字符串中!出现的次数 即限定区间左闭右开
```

    1

```python
S.lstrip()
#去掉字符串的左边空格 left
```

    'aa!bb!cc!dd!EE  '

```python
S.rstrip()
#去掉字符串的右边空格 right
```

    '  aa!bb!cc!dd!EE'

```python
S.upper()
#将小写字母完全变成大写字母
```

    '  AA!BB!CC!DD!EE  '

```python
S.lower()
#将大写字母完全变成小写字母
```

    '  aa!bb!cc!dd!ee  '

```python
S.capitalize()
#开始是空格的话,此函数不起作用 
#此函数的作用是将字符串的第一个字母变成大写,其他字母变小写
```

```python
S.lstrip().capitalize()
#把字符串的第左边一个字母变成大写 
```

    'Aa!bb!cc!dd!ee  '

```python
S.title()
#把所有单词的第一个字母变成大写 注意是单词 再次用！分割的
```

    '  Aa!Bb!Cc!Dd!Ee  '

## Page14：转义字符的使用

```python
print('转义字符示例：\n换行')
print('转义字符示例：\r回车')
print('转义字符示例：\r','水平制表')
print('转义字符示例：\v垂直制表')
print('转义字符示例：\0空字符')
```

    转义字符示例：
    换行
    回车
     水平制表
    转义字符示例：垂直制表
    转义字符示例： 空字符

```python
# \n 换行 \r 回车 
# 水平制表 就相当于空8格 用来制表对其 下面是一个实例
```

```python
print("\t姓\v名\t班\v级\t\t学\v校")
print("\t陈昱杰\t统计2班\t\t武汉科技大学") 
```

     姓名 班级  学校
     陈昱杰 统计2班  武汉科技大学

```python
# 垂直制表 感觉很不常用
```

```python
print('416 \v asfa')
```

    416  asfa

## Page15：列表

```python
List = list('这里是一个列表123') # , 用来分隔
List
#创建一个列表
```

    ['这', '里', '是', '一', '个', '列', '表', '1', '2', '3']

```python
List.insert(3,'%')
List
#对列表添加元素
```

    ['这', '里', '是', '%', '一', '个', '列', '表', '1', '2', '3']

```python
print(List.pop())   #移除列表中的一个元素（默认最后一个元素），并且返回该元素的值 pop()
List.pop(3)    #输入索引移除索引位置上的值即%
List
```

    3
    




    ['这', '里', '是', '一', '个', '列', '表', '1', '2']

```python
List[4]='new' #有点像数组
List
#将列表索引为4的元素修改成'New'
```

    ['这', '里', '是', '一', 'new', '列', '表', '1', '2']

```python
List.index('表')
#查找元素'表'的位置并返回索引 index
```

    6

```python
'这' in List
#判断元素是否存在与列表
```

    True

```python
'我是陈昱杰' in List
```

    False

```python
List+list('新列表')
#合并列表 + 
```

    ['这', '里', '是', '一', 'new', '列', '表', '1', '2', '新', '列', '表']

```python
List*3
#重复列表 竖着来
```

    ['这',
     '里',
     '是',
     '一',
     'new',
     '列',
     '表',
     '1',
     '2',
     '这',
     '里',
     '是',
     '一',
     'new',
     '列',
     '表',
     '1',
     '2',
     '这',
     '里',
     '是',
     '一',
     'new',
     '列',
     '表',
     '1',
     '2']

```python
#切片操作省略
```

## Page16：列表的其他用法

```python
List.append('obj')
List
#在列表末尾添加新的对象 app end
```

    ['这', '里', '是', '一', 'new', '列', '表', '1', '2', 'obj']

```python
List.count('fbj')
#统计某个元素在列表中出现的次数
```

    0

```python
List.extend(list('新列表'))
List
#在列表末尾一次性追加另一个序列中的多个值（用新列表扩展原来的列表） ext end
```

    ['这', '里', '是', '一', 'new', '列', '表', '1', '2', 'obj', '新', '列', '表']

```python
List.remove('是')
List
#移除列表中某个值的第一个匹配项 注意是第一个
```

    ['这', '里', '一', 'new', '列', '表', '1', '2']

## Page17：元组基本操作

```python
Tuple = tuple(list('元组'))
Tuple
```

    ('元', '组')

```python
Tuple = tuple
Tuple
```

    tuple

```python
Tuple0=(1,) #创建一个元素的元组时,为了避免歧义,需要在元素后面加个, 【】 （）
Tuple1=('1','2','3')
Tuple=tuple(list('这里是一个元组')) #元组tuple()
Tuple
#创建元组
```

    ('这', '里', '是', '一', '个', '元', '组')

```python
len(Tuple) 
#求元组长度
```

    7

```python
Tuple+Tuple1
#合并两个元组
```

    ('这', '里', '是', '一', '个', '元', '组', '1', '2', '3')

```python
Tuple*2
#重复元组
```

    ('这', '里', '是', '一', '个', '元', '组', '这', '里', '是', '一', '个', '元', '组')

```python
'这' in Tuple
#判断元素是否存在于元组
```

    True

```python
sorted((2,3,5,6,8))
#对元组中的元素进行排序 sort是从小到大
```

    [2, 3, 5, 6, 8]

```python
#切片操作省略
```

## Page18：集合

```python
Set=set(list('这里是一个集合一'))
Set
#创建集合,集合元素不重复,所以'一'只有一个认第一个的位置
```

    {'一', '个', '合', '是', '这', '里', '集'}

```python
Set.add('x')
Set
#向集合添加元素 直接加到第一个
```

    {'x', '一', '个', '合', '是', '这', '里', '集'}

```python
Set2=set(list('新元素'))
Set.update(Set2)
Set
#把集合Set2的元素添加到Set
```

    {'x', '一', '个', '元', '合', '新', '是', '素', '这', '里', '集'}

```python
Set.remove('新')
Set
#删除集合中的元素'新'
```

    {'x', '一', '个', '元', '合', '是', '素', '这', '里', '集'}

```python
Set.discard('x')
Set
#删除指定元素，但是如果集合中没有的话就什么也不做 discard
```

    {'一', '个', '元', '合', '是', '素', '这', '里', '集'}

```python
print(Set.pop()) 
print(Set)
#随机删除一个，并返回该值 pop还记得在列表中是最后一个 这里随机的是’这‘
```

    里
    {'一', '集', '是', '个', '元', '素', '合', '这'}

## Page19：集合运算操作简便写法

```python
# 在对集合做运算时，不会影响原来的集合，而是返回一个运算结果
# 创建两个集合
A = {1,2,3,4,5}
B = {3,4,5,6,7}
```

```python
# 并集
print(A | B) 
print(A.union(B) )          #联合
```

    {1, 2, 3, 4, 5, 6, 7}
    {1, 2, 3, 4, 5, 6, 7}

```python
# 交集
print(A & B)                                      
print(A.intersection(B))      #交集的结果           
```

    {3, 4, 5}
    {3, 4, 5}

```python
# 差集
print(A - B)
print(A.difference(B))                 #-等同于difference
```

    {1, 2}
    {1, 2}

```python
# 异或集合
print(A ^ B)        
print(A.symmetric_difference(B))    #C语言^二进制取异或
```

    {1, 2, 6, 7}
    {1, 2, 6, 7}

## Page20：字典

```python
#使用大括号来创建字典{ } 
#字典是可以重复的
Dict  = {"name":"陈昱杰","age":19,"pay":40000,"job":"学不会计算机"}
#使用关键字参数和类型构造函数来创建字典
Dict
```

    {'name': '陈昱杰', 'age': 19, 'pay': 40000, 'job': '学不会计算机'}

```python
Dict = dict(name="陈昱杰",age=19,pay=40000,job="学不会计算机")
Dict
```

    {'name': '陈昱杰', 'age': 19, 'pay': 40000, 'job': '学不会计算机'}

```python
Dict.update({'AddKey':'AddValue'})
Dict
#向字典中添加键值对   'AddKey':'AddValue' updata合并 也在里面
#                   Add      Key      Value  小驼峰
```

    {'name': '陈昱杰', 'age': 19, 'pay': 40000, 'job': '学不会计算机', 'AddKey': 'AddValue'}

```python
Dict.pop('name')
Dict
#删除'name'对应的键值对
```

    {'age': 19, 'pay': 40000, 'job': '学不会计算机', 'AddKey': 'AddValue'}

```python
Dict['pay']=10000
Dict
#修改键'pay'的值为10000
```

    {'age': 19, 'pay': 10000, 'job': '学不会计算机', 'AddKey': 'AddValue'}

```python
DictMerged = Dict.copy() #复制字典,避免合并结果影响原始字典 拷贝引用
Dict2={'AddKey1':'AddValue1','AddKey2':'AddValue2','AddKey3':'AddValue3'}# 新字典
DictMerged.update(Dict2)#通过updata合并两个字典
DictMerged
```

    {'age': 19,
     'pay': 10000,
     'job': '学不会计算机',
     'AddKey': 'AddValue',
     'AddKey1': 'AddValue1',
     'AddKey2': 'AddValue2',
     'AddKey3': 'AddValue3'}

```python
'age' in Dict
#判断键在不在字典中
```

    True

```python
Dict.keys()#查看所有键 s
```

    dict_keys(['age', 'pay', 'job', 'AddKey'])

```python
Dict.values()#查看所有值 对 s
```

    dict_values([18, 10000, 'Python工程师', 'AddValue'])

```python
Dict.items()#查看键值对 item 项 s 
```

    dict_items([('age', 19), ('pay', 10000), ('job', '学不会计算机'), ('AddKey', 'AddValue')])

## Page23：循环

### for 循环

```python
for i in range(5):
    print(i)#注意空格 range 从0到5 换行输出
```

    0
    1
    2
    3
    4

```python
for i in range(2,6):#依旧是左闭右开
    print(i)
```

    2
    3
    4
    5

```python
for i in range(2,6,2):#步长
    print(i)
```

    2
    4

```python
Object=list('列表内容')#var
for i in Object:
    print(i)
else:
    print('循环结束')
```

    列
    表
    内
    容
    循环结束

### while循环

```python
a=2
while a<5:  #python就是简便 连()都不用 while 跟 else 都可以
    print(a)
    a += 1
else:
    print('循环结束')
```

    2
    3
    4
    循环结束

## Page24：分支结构

### 单分支

```python
a = 3
if a < 2:
    print(a)    
    
if a > 2:
    print(a)
```

    3

### 双分支

```python
a = 3
if a < 2:
    print(a)
else:
    print('a不小于2')

```

    a不小于2

### 多分支

```python
a = 2
if a < 2:
    print('a小于2')
elif a > 2:
    print('a大于2')
else:
    print('a等于2')
```

    a等于2

## Page26：列表推导式

```python
data=[]
for i in range(5): #0 1 2 3 4 
    data.append(i**2-i*2)
print(data)

data1=[i**2-i*2 for i in range(5)]
print(data1)
```

    [0, -1, 0, 3, 8]
    [0, -1, 0, 3, 8]

```python
#既然到这里不妨比较一下 2**3**4 (2**3)**4 上下 左右 这种式子要从右到左
print(2**3**4)
```

    2417851639229258349412352

```python
print((2**3)**4)
```

    4096

```python
data=[]
for i in range(10):
    if i%2==0:
        data.append(i**2)
print(data)

data1=[i ** 2 for i in range(10) if i % 2 == 0] #偶数 连：都没有
print(data1)
```

    [0, 4, 16, 36, 64]
    [0, 4, 16, 36, 64]

## Page26：pass、break和continue

### pass

```python
for i in range(3):
    #没有内容,会报错
```

      File "C:\Users\探索者\AppData\Local\Temp\ipykernel_11816\1463202553.py", line 2
        #没有内容,会报错
                 ^
    IndentationError: expected an indented block

```python
for i in range(3):
    pass
    #pass占位 不报错 占位符号
```

### break

```python
for i in range(3):
    print('break前')
    print(i)
    break
    print('break后')
#break停止整个循环
```

    break前
    0

### continue

```python
for i in range(6):
    print('continue前')
    print(i)
    continue
    print('continue后')
#continue停止一次循环的后半段 进入下一次循环
```

    continue前
    0
    continue前
    1
    continue前
    2
    continue前
    3
    continue前
    4
    continue前
    5

## Page28:函数使用

### def函数

```python
def fun1(x,y): #定义def
    return x ** y
fun1(2,3)#按照顺序传入参数 funl
```

    8

```python
def fun1(x,y):
    return x ** y
fun1(y = 2, x = 3)#通过名称传入参数,可以忽略位置顺序
```

    9

```python
def fun1(x , y = 3):
    return x**y
fun1(x = 3) #设置默认值,没有传入相应参数时会首先应用默认参数
```

    27

### lambda函数

```python
f = lambda x , y: x ** y #return 匿名函数 可以不用函数名称
f(2 , 3)
```

    8

## Page29:类

```python
class test: #self是类的名称 s1   s2  是成员变量
    def __init__(self,s1,s2):
        self.s1 = s1
        self.s2 = s2

    def f1(self):
        return self.s1 + self.s2

    def f2(self, x): #注意，号
        return (x**self.s2, x**self.s2)
aa=test(s1=2,s2=3) #定义aa
print('查看属性值', aa.s1)
print("输出f1: ", aa.f1())
print("输出f2: ", aa.f2(3))
```

    查看属性值 2
    输出f1:  5
    输出f2:  (27, 27)

## Page32:读写文件

### 写文件

```python
with open('test.txt','w') as f:
    f.write('Hello, world!\n')
    f.write('Goodbye, world!')
```

```python
f=open('test1.txt','w')
f.write('Hello, text!\n')
f.write('Goodbye, text!')
f.close()
```

### 读文件

```python
with open('test1.txt','r') as f:
    context=f.readlines()
    for i in context:
        print(i)
        
with open('test1.txt','r') as f:
    context=f.read() #一行一行的读
    for i in context:
        print(i)
```

    Hello, text!
    
    Goodbye, text!
    H
    e
    l
    l
    o
    ,
     
    t
    e
    x
    t
    !
    
    
    G
    o
    o
    d
    b
    y
    e
    ,
     
    t
    e
    x
    t
    !

```python
file = open('test1.txt','r') #路径
context = file.readlines()
for i in context:
    print(i)
file.close()
```
