# PyV8
`PyV8`是对`V8`引擎的`Python`封装, 可以直接渲染`JS`.

## Windows
根据系统位数(`右键我的电脑`-->`属性`-->`系统类型`中查看), 双击运行`Windows`目录中对应的`*.exe`安装包, 在`Windows`上直接进行安装(需要先安装了`Python 2.7`, 软件会自动检测`Python`的`Path`路径).

```
PS: 注意Python是32还是64位, 如果Python是32位的, 系统是64位的, 在安装时需要选择只为 当前用户 安装, 否则安装PyV8时, 会提示register表没有路径.
```

## Linux
将`Linux`目录下的`PyV8.tar.gz`解压(`tar -xzvf PyV8.tar.gz`, 解压到当前目录), 将解压后的`PyV8`文件夹下的所有内容, 拷贝到`Python`安装目录下的`lib/site-packages/`下面. 如果是虚拟环境, 就拷贝到虚拟环境目录下的`lib/site-packages`.

## 使用示例
```
# -*- coding:utf-8 -*-

from PyV8 import JSContext


# 创建JSContext对象并进入
js = JSContext()
js.__enter__()

# script是字符串
js.eval(script)

# 调用JS中的函数, Func为JS中的函数名
func = js.locals.Func

# 执行
Func()

# 调用JS中的变量, result是JS中的变量名
r = str(js.eval('result'))
print r
```
