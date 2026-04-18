from socket import send_fdsfrom time import daylight

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

补充：常量也是一种变量，必须大写，PI=3.14
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

2.转移字符：\' \"（在字符串中的'和"），\n （换新的一行），\t（缩进 制表符）

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
#### 1.5.1算数运算符

1.分类：算术运算符，赋值运算符，比较运算符，逻辑运算符

2.算数运算符：= 、- 、* 、 **//**（除不尽会保留小数点前一位的数）、/（有可能是浮点数）、 **（幂指数）

#### 1.5.2赋值运算符

1.赋值运算符：= 、+= 、-= 、*= 、/= 、%= 、 //= 、 **=

#### 1.5.3比较运算符

1.比较运算符：== 、！= 、> 、 >= 、 < 、 <=

#### 1.5.4逻辑运算符

1.逻辑运算符：and（逻辑与） 、or（逻辑或）、not（逻辑非，取反）

## 第二章 数据逻辑的处理

### 2.1 条件判断
1.格式：
（1）if语句
```python
if 要判断的条件:
      条件成立时,要执行对应的操作

score = 695
if score>680:
    print("成功录取")
```

注意：条件成立时的代码，一定要缩进，python中是通过缩进来判断代码的归属的

（2）if...else语句

```python
if account == ok_account and password == ok_password: 
    print("登陆成功")
else account ！= ok_account and password ！= ok_password:
    print("登陆失败")
```

（3）if...elif...else

```python
num = int(input("请输入您的数字："))
if num > 0:
    print(f"{num}是一个正数")
elif num<0:
    print(f"{num}为负数")
else:
    print(f"{num}等于0")
```

### 2.2match匹配模式
1，格式：match...case
```python
day = input("请输入数字：")
match day:
    case "1":
        print("周一")
    case "2":
        print("周二")
    case _:
        print("输入错误")
```

### 2.3循环
#### 2.3.1while循环
1.格式：
```python
i = 0
while i < 10: 
    print("人生苦短，我用python")
    i += 1
else:    #可以不加
    print("循环正常")
```

#### 2.3.2for循环
1，格式:
```python
msg = "Hello-Python"
for i in msg:#通常会从0开始取
       print(i)
else:
       print("循环结束")
```
注意：while循环循环次数一般是未知的，只知道循环开始和循环结束的条件，而for则是对一个已知的数据集进行循环

补充：

比如：我要让一个_重复30次可以用
print(" _ " * 30)
2.range语句
```python
range(5)#用法一：从0开始一直到5
range(3,5)#用法二：从3开始，一直到5
range(3,8,2)#用法三：从3开始，隔2个一跳,3,5,7
```

3.嵌套循环
（1）break语句：只能在循环语句中出现，表示结束跳出循环
（2）continue语句：也只能在循环语句中出现，表示跳过这次循环，进入下一次循环

## 第三章 数据存储容器
### 3.1列表（list）
#### 3.1.1列表入门
1.定义：列表名称 = [元素1,元素2,元素3]

eg. s=[54,15,75,108,23]（尽量存储同一类型的数据）

正向：s[0]=54  s[1]=15  s[2]=75  s[3]=108  s[4]=23

反向：s[-5]=54  s[-4]=15  s[-3]=75  s[-2]=108  s[-1]=54

2.获取列表元素

print(s[0])

print(s[-5])

3.修改

s[5]="abc"

print(s)
注意：超出索引会报错

4.删除列表中的元素

del s[5]

#### 3.1.2切片

1.定义：切片就是指对操作的数据截取一部分的操作，可以跳着截取但是也只能是固定长度的

2.格式：序列数据[开始索引:结束索引:步长]

注意：开始索引后面的冒号不能省略

#### 3.1.3列表的常见方法
1.方法：append()、insert()、remove()、pop()、sort()、reverse()

2.append()方法：在列表尾部追加元素

s.append(10086)

3.insert()方法：在指定索引之前插入元素

s.insert(2,92)

4.remove()方法：移除列表第一个匹配到的值

s.remove(75)

5.pop()方法：删除列表中的指定索引的元素

e = s.pop(2) / s.pop()

6.sort()方法：对列表进行排序（默认从小到大）

s.sort()

7.reverse()方法：反转列表

s.reverse()
### 3.2字符串（str）
#### 3.2.1基本操作
1.定义：字符串是字符的容器，一个字符串可以存放任意数量的字符

2.特点：不可变性（不可以修改字符串内的字符），有序性，可迭代性（可遍历）

3.可以通过索引进行访问，几乎与列表一样

#### 3.2.2字符串切片
1.格式：序列对象[开始索引:结束索引:步长]

注意：开始索引默认为0;结束默认为-1;步长为1

正向、反向都可以

如果是-1表示从后向前

#### 3.2.3常用方法
1.注意：无论用什么方法都无法改变字符串内部的内容

2.常用方法：

find() 在字符串中查找字串，返回第一次出现的索引位置，找不到返回-1

count() 统计字串在字符串中出现的次数

upper() 将字符串中所有的字母转换为大写

重新赋值给一个新的字符串

sl = s.upper()

lower() 将字符串中所有的字母转换为小写

重新赋值给一个新的字符串

sl = s.lower()

split() 将字符串按指定分隔符分割成列表

strip() 去除字符串两端的空白字符和指定字符

replace() 将字符串中的指定字串替换为新的字串

startswith() 检查字符是否以指定字串开头，返回布尔值
### 3.3元组（tuple）
#### 3.3.1元组的基本操作
1.定义：元组是不可变的序列，类似于列表，但创建后不能修改

2.格式：

元组名称 = (元素1,元素2,...)

注意：在定义单元素元组时，要写(100,)

定义空元组：
元组名称 = ()

元组名称 = tuple()

3.方法：count() 统计某个元素在元组中出现的次数

index() 查找某个元素在索引中的位置

#### 3.3.2组包与解包
1.组包：将多个值合并到一个容器中

2，解包：将容器解开成独立元素，分别赋值给多个变量

```python
t1 = (1,2,3,4)#下面两种都是组包
t1 = 1,2,3,4

a,b,c,d = t1 #基础解包
e,*f,g = t1#拓展解包，e=1 f=[2,3] g=4，最后f生成的是列表
#应用：在python中交换a，b的值可以用组包与解包

a,b=b,a
```
### 3.4集合（set）
#### 3.4.1 set集合的基本操作
1.定义：无序的（无法通过索引访问元素）、不可重复的、可修改数据容器

2.格式：
```python
set_1 = {1,2,3,4,5}

set_2 = set()#空的集合
```

#### 3.4.2 set集合常用方法
1.方法：

（1）add() 将元素添加到集合中

（2）remove() 移除集合中的指定元素

（3）pop() 随机删除集合中的元素并返回

（4）clear() 清空集合

（5）difference() 求两个集合的差集

s1.difference(s2)

（6）union() 求两个集合的并集

（7）intersection 求两个集合的交集
### 3.5字典（dict）
#### 3.5.1字典的基本操作
1.定义：在字典（dict）中，里面存储的是（key:value）类型的数据

2.格式：
```python
dict1 = {"王琳":675,"小明":608,"许立国":678}#在字典中key必须是唯一的

#空的字典
dict2 = {}
dict3 = ()
```
#### 3.5.2字典的常用操作 
1.方法（增删改查）：

（1）字典名称[key] = value 往字典中添加了一个键值对

（2）字典名称.pop(key) 删除指定的key，并返回key对应的value

（3）del 字典名称[key]

（4）字典名称[key] = value 修改key对应的数值

（5）字典名称[key] 或者  字典名称.get(key) 根据key对应的value

（6）字典名称.keys() 获取所有key

（7）字典名称.values() 获取所有的value

（8）字典名称.items() 获取所有key-value键值对

## 第四章 函数
### 4.1函数
#### 4.1.1函数的定义
1.定义的格式：

（1)定义函数

def 函数名(参数列表)\:

&emsp;&emsp; 函数体

&emsp;&emsp;.......

&emsp;&emsp;return 返回值

（2）调用函数

&emsp;&emsp;函数名(参数)

注意：函数先定义后调用

2.函数的参数与返回值
```python
def circle_area(r):
       area=3.14*r*r
       return area
c_area = circle_area(10)
print(c_area)
```
#### 4.1.2函数的说明文档
1.格式
```python
def circle_area(r):
       """
       该函数是计算圆的面积的
       :param area:圆的面积
       :return: 圆的的面积
       """
       area=3.14*r*r
       return area
c_area = circle_area(10)
print(c_area)
# help(circle_area)
```
#### 4.1.3函数的嵌套
1.简单的嵌套就是调用函数，而这里写的是递归

#### 4.1.4函数中变量的作用域
1.在函数内部定义的变量是内部变量

#### 4.1.5函数的传参方式
1.位置参数：
```python
def reg_stu(name,age,gender,city):
    print("你好")
    return
reg_stu("小明",16,"男","石家庄")
```

2.关键字参数：
```python
def reg_stu(name,age,gender,city):
    print("你好")
    return
stu = reg_stu(name="小明",age=16,gender="男",city="石家庄")#这个时候传参就不用按照位置传参了
```

3.位置传参+关键字参数
```python
#位置参数+关键字参数
```
4.函数的默认参数
（1）默认参数也称为缺省参数，定义函数时，为参数提供默认值，可以不传递有默认值的参数

```python
def reg_stu(name,age,gender,city="石家庄"):#默认参数必须放在未设置参数后面
    print("你好")
    return
stu = reg_stu(name="小明",age=16,gender="男")#如果说传递了参数就会修改为默认参数
```

5.可变参数/不定长参数
（1）位置传递

```python
def cacl_data(*args):#基于位置参数传递的会封装到元组中
       min_data = min(args)
       return min_data
data = cacl_data(1,3,5,76,12,3,4,6)
print(data)
```

（2）关键字传递

```python
def cacl_data(*args,**kwargs): #会封装到字典中，也就是键值对
       min_data = min(args)
       return min_data
data = cacl_data(1,3,5,76,12,3,4,6,round=2,count=0)
print(data)
```

6.参数类型
（1）普通参数：

数字、布尔、字符串、列表、元组、集合、字典

（2）特殊参数：

函数
```python
def add(x,y):
       return x+y

def cacl(x,y,oper)#高阶函数
       return oper(x,y)

sum = oper(1,2,add)


```
7.匿名函数
（1）格式：lambda 参数列表 : 函数体

eg.lambda x,y : x + y

作用：用于简化函数的书写，通常用于高阶函数

## 第五章 模块 
### 5.1模块入门
1.模块的定义：一个.py文件就是一个模块，模块是python中最基本的组织单位

2.格式：

（1）import 模块名 import random , os

（2）import 模块名 as 别名  这个是给模块起一个别名

（3）from 模块名 import 功能名

（4）from 模块名 import 功能名 as 别名

（5）from 模块名 import *  导入该模块的所有的功能

```python
#方法一
import random#首先导入random模块
import random as rd#对模块名重新命名

for i range(100):
       print(rd.randint(1,100))

#方法二
from random import randint#导入模块的方法
for i range(100):
       print(randint(1,100))
```

### 5.2自定义模块
1.同上面，直接import 模块名，引用时直接 模块名.变量/方法
