---
title: python3利用venv和pip管理虚拟环境
date: 2019-10-07 16:24:48
categories:
 - 备忘
tags:
 - python
 - venv
 - 虚拟环境
---
以前一直不重视python项目的包管理，在交接时总是不明确项目具体需要依赖哪些第三方库，为此复习一下python3虚拟环境的创建和包管理，希望以后能养成一个项目一个环境的习惯
<!-- more -->
## 使用venv创建虚拟环境
### venv
venv是python3标准库中内置的模块，功能和以前的virtualenv类似

### 创建虚拟环境
在项目根目录下
```
python -m venv my-venv
```
my-venv是创建的虚拟环境的名字，可以自由修改，执行命令后在项目根目录下会创建对应虚拟环境的文件夹

### 激活虚拟环境
在项目根目录下
* windows:
    ```
    my-venv\scripts\activate
    ```
* linux:
    ```
    source my-venv/bin/activate
    ```
    或
    ```
    . my-venv/bin/activate
    ```

激活虚拟环境后能在命令行提示符前面看见当前虚拟环境的名字
```
(my-venv) $
```

## 依赖的导出和导入
在激活的虚拟环境中依赖的安装和卸载这里就不赘述了

查看环境中的所有依赖：
```
(my-venv) $ pip list
```
导出依赖列表
```
(my-venv) $ pip freeze > requirements.txt
```
安装requirements.txt中所有依赖
```
(my-venv) $ pip install -r requirements.txt
```