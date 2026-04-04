from pickletools import string1from pickletools import string1from pickletools import string1from markdown.extensions.toc import stashedHTML2text

# python学习日志

## 第一章 基础语法
### 1.1入门程序
- 步骤：

（1）首先点击新建项目

（2）选择venv虚拟环境

eg.需求输出 hello word（**#** 是python中注释的写法，“Ctrl+/”为快捷键）

```python
print("hello word") #python代码结尾不需要加 ;
```
### 1.2数据存储与运算
#### 1.2.1字面量与变量

1.字面量（一共五种）：-5（数字类型int，float），True/False（布尔类型），"hello"（字符串），**None**（空值），列表/元组/集合/字典（数据容器）

```python
print(5)
print(True)
print("hello")
print(None)
```

2.变量：在定义变量时，不用表明变量名，在python中变量属于动态变量

eg.      
num=1114.1

```python
nums = 1
print(nums)

nums+=1
print(nums)
```

注意：在开发中一般只能用同一类型的变量类型的赋值

#### 1.2.2标识符

1.定义：为变量、函数、类等元素起的名字

2.要求：（1）只能包含字母、数字、下划线
       （2）不能以数字开头
       （3）不能用关键字
       （4）大小写不一样，变量也不一样
### 1.3常见数据类型
#### 1.3.1基本的数据类型
1.类型：整数（int）、浮点数（float）、字符串（str）、布尔值（bool）、空值（Nonetype)

2.如何查看数据类型：运用type()函数来查询变量的类型,或者运用isinstance(数据，类型)来查看
eg.
```python
print(type("hello"))#用法一
print(type(1))
print(type(True))

nums=1#用法二
print(nums)
print(type(nums))

nums=1
print(isinstance(nums,int))
```
#### 1.3.2字符串
1.字符串的表达方式：
```python
s1="hello"#注意s1与s2均不能换行

s2='hello'

s3="""
尊敬的客户你好
     感谢您选择我们公司的产品       
"""

```

2.转移字符：\' \"（在字符串中的'和"），\n （换新的一行），\t（缩进）

3.字符串的拼接：在多数情况下我们运用+来拼接

```python
s1="我要吃饭"
s2="早上好"
print("s1+","+s2")
```

注意：只能拼字符串，如果里面有非字符串内容，可以利用str(变量名称)进行强制类型转换

#### 1.3.3字符串的格式化
1.定义：通过%占位符完成字符串和变量的快速拼接，（1）%表示我要占位，s表示将变量转为字符串放入占位的位置，（2）也可以通过 f"内容{变量/表达式}"
```python
s1="你好"#方法一
s2=1
print("%s,我是南宫春水" % s1)
print("%s,我是第%s" % (s1,s2))

print(f"我是第{s2}")#方法二

print("10*4=",10+4)#方法三
```
### 1.4输入与输出
1.用法：通过input语句进行输入，s=input(提示信息)，然后运用print语句输出
```python
name=input("请输入您的名字：")
print(f"欢迎您，{name}")
```

注意：无论您在键盘上输入什么数据，最后获取的数据永远都是字符串类型

### 1.5运算符
1.分类：算术运算符，赋值运算符，比较运算符，逻辑运算符
2.算数运算符：=、-、*、**//**（除不尽会保留小数点前一位的数）、/（有可能是浮点数）、 **（幂指数）