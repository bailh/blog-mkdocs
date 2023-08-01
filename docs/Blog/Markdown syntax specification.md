# Markdown syntax specification.md

[details见官方文档](https://www.markdown.xyz/basic-syntax/)

## 官方文档很清楚了但是有的语法根据实践有偏差,故列出

### 插入图片

```html
![](image/..)
```

### 跳转

#### 文档跳转

#### 实现方法

假设
concent文件夹中有两个文档
c1.md
c2.md

相对路径
**../ 表示当前目录上一级**

**./ 表示当前目录**

[添加对象](绝对路径)   //括号均为英文  
1

##### 向下跳转

要有文件夹的名称
[content](/content)
[第一章](/content/C1.md)
1
2

##### 同级跳转

相同文件夹下的文件之间相互跳转

[下一章](./C2.md) 	//C1.md
1
[上一章](./C1.md)  //C2.md
返回目录 //C2.md

[返回目录](../README.md) //C2.md
1
绝对路径
返回目录，这采用HTML写法

<a href="https://github.com/BackMountainDevil/The-C-Programming-Language#the-c-programming-language">返回目录</a>
1
返回目录，这采用md（Markdown）写法

[返回目录](https://github.com/BackMountainDevil/The-C-Programming-Language#the-c-programming-language)
————————————————
