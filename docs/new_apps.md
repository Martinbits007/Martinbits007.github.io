# 开发日志
## 项目起源
1.本项目由trae软件做出了第一版
## 问题与总结
1.端口问题：

（1）首先127.0.0.1是本机回环地址，就好比本机电脑是一栋大楼，每个软件或者项目运行需要一个端口（这个就是房间），最开始使用的是8000端口，但是发现被占用

所以通过终端改为9000端口

（2）端口问题：本质上是由后段进程没有结束造成的

解决方案：在bush中加入ctrl+c来结束后端的进程

（3）html问题：在<head>标签中，首先就是lang = "zh-CN" 这个就是告诉浏览器用什么语言

而charset = "UTF-8"则是像一本字典一样让浏览器识别该文字应该显示成什么样子

（4）标签问题：首先是<div>这个标签，这个是对前端html页面进行一个分区

2.Javascript语法问题：

（1）基础的js标签
```html

<script>
    console.log("Hello Word")
</script>

<!-- 一般情况下<scrip>标签写在html文件的最后面-->

<script src="index.js"></script>
```

（2）变量

var（全局作用域，不实用），let（let的值可以被修改），const（const的值不能被修改）

（3）原生数据类型

不用声名直接用（null与undefined的区别是null是被定义了，而undefin是未定义的）

```html
<script>
    const username = "小明";
    const login = undefined;
</script>
```

（4）函数

①常规函数

function 函数名() {

&emsp;&emsp;//代码

}

②匿名函数

function () { }

③箭头函数

() = > {}

④表达式函数

let fn = function () {

}

（2）try...catch语句

在try是用来运行危险并且容易报错的代码，如果不加并且出现报错代码时会直接出现卡死不运行

这是就会用catch语句来进行晁错并且运行

3.http请求与前后端连接的文体

（1）通过fetch发送http POST请求，浏览器即刻生成第一个promise

（2）然后以json字符串发送给后端

（3）这时后端会对json字符串进行校验

（4）当后端校验通过了会发送完整的http请求(其中就包含response对象)

（5）然后会把js利用response把其变为js对象

（6）再将response存入data对象里面

4.登录运用jwt技术做后端登录校验，可能后期会换成redis+token技术

3.fastapi后端
（1）首先，需要导包
```python
# FastAPI 核心必备
from fastapi import FastAPI, HTTPException, Depends, Query, Path, Body
#FastAPI是一个大类，用这个大类来创建一个后端的大对象，这个对象本身就是后端
#HTTPException是发送错误信息，比如状态码401，或者错误信息
#Depends就是依赖，用来优先执行
from fastapi.middleware.cors import CORSMiddleware
#fastapi.middleware.cors这个是前后端相连接的文件包
#COREMiddleware用于http传输管道
from fastapi.security import HTTPBearer, HTTPAuthorizationCredentials
#用于实现token

# 数据校验模型 必备
from pydantic import BaseModel, Field

# 时间处理（JWT过期时间专用）
from datetime import datetime, timedelta

# JWT 生成和解码
from jose import JWTError, jwt

# 密码加密（存加密密码，不存明文）
from passlib.context import CryptContext

# 类型注解（可选但必常用）
from typing import Optional, List, Dict, Any
```