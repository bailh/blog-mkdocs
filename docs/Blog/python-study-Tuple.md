# python-study-Tuple


```python
rhyme = (1,2,3,4,5, "上山打老虎")
```


```python
rhyme
```




    (1, 2, 3, 4, 5, '上山打老虎')




```python
rhyme[0]
```




    1




```python
rhyme[-1]
```




    '上山打老虎'



### <a name="jump_1">不支持修改</a>
```python

rhyme[1]=10#不支持修改
```


    ---------------------------------------------------------------------------

    TypeError                                 Traceback (most recent call last)

    ~\AppData\Local\Temp\ipykernel_17308\1184099170.py in <module>
    ----> 1 rhyme[1]=10
    

    TypeError: 'tuple' object does not support item assignment



```python
rhyme[:3]
```




    (1, 2, 3)




```python
rhyme[3:]
```




    (4, 5, '上山打老虎')




```python
rhyme[:]
```




    (1, 2, 3, 4, 5, '上山打老虎')




```python
rhyme[::2]
```




    (1, 3, 5)




```python
rhyme[::-1]
```




    ('上山打老虎', 5, 4, 3, 2, 1)




```python
nums= (3,1,9,6,8,3,5,3)
```


```python
nums.count(3)
```




    3




```python
heros=("蜘蛛侠","绿巨人","黑寡妇")
```


```python
heros.index("黑寡妇")
```




    2




```python
s=(1, 2, 3)
```


```python
t=(4,5,6)
```


```python
s+t
```




    (1, 2, 3, 4, 5, 6)




```python
s*3
```




    (1, 2, 3, 1, 2, 3, 1, 2, 3)



## ,用于切割元组


```python
w=s, t
```


```python
w
```




    ((1, 2, 3), (4, 5, 6))




```python
for each in s:
    print(each)
```

    1
    2
    3
    


```python
for i in w:
    for each in i:
        print(each)
```

    1
    2
    3
    4
    5
    6
    


```python
s=(1,2,3,4,5)
```


```python
[each*2 for each in s]
```




    [2, 4, 6, 8, 10]




```python
(each*2 for each in s) #生成器
```




    <generator object <genexpr> at 0x00000241A7CCF200>



### 没有元组推导式


```python
x=(520)
```


```python
x
```




    520




```python
type(x)
```




    int




```python
x = (520,)
```


```python
x
```




    (520,)




```python
type(x)
```




    tuple



## 打包和解包


```python
t=(123,"FishC",3.14)
```


```python
t
```




    (123, 'FishC', 3.14)




```python
x, y, z = t
```


```python
x
```




    123




```python
y
```




    'FishC'




```python
z
```




    3.14



### both applyed to list and tuple


```python
t=[123,"FishC",3.14]
```


```python
x, y, z = t
```


```python
x
```




    123




```python
y
```




    'FishC'




```python
z
```




    3.14



#### 左右变量数量一致


```python
a, b, *c="FishC"
```


```python
a
```




    'F'




```python
b
```




    'i'




```python
c
```




    ['s', 'h', 'C']



### 多重赋值


```python
x, y = 10, 20
```


```python
x
```




    10




```python
y
```




    20




```python
_=(10,20)
```


```python
x, y = _
```


```python
x
```




    10




```python
y
```




    20



## security


```python
s=[1,2,3]
```


```python
t=[4,5,6]
```


```python
w=(s,t)
```


```python
w
```




    ([1, 2, 3], [4, 5, 6])




```python
w[0][0]=0
```


```python
w
```




    ([0, 2, 3], [4, 5, 6])



### [此时对于元组中可变的列表，依然可以更改](#jump_1)


```python

```
