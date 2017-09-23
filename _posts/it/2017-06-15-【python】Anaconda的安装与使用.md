---
layout: post
title: "【python】Anaconda的安装与使用"
date: 2017-06-15 
tag: 计算科学
---  

## Anaconda的安装与使用
作者：Neo Luo  
时间：2017-06-15

----

Anaconda是专注于数据分析的Python发行版本，包含了conda、Python等190多个科学包及其依赖项。

Anaconda优势：

（1）不需要配置python环境变量。

（2）已经集成很多packages，且安装也方便。

（3）可配置不同python环境，切换方便。

conda 是开源包（packages）和虚拟环境（environment）的管理系统。

packages 管理： 可以使用 conda 来安装、更新 、卸载工具包 ，并且它更关注于数据科学相关的工具包。在安装 anaconda 时就预先集成了像 Numpy、Scipy、 pandas、Scikit-learn 这些在数据分析中常用的包。另外值得一提的是，conda 并不仅仅管理Python的工具包，它也能安装非python的包。比如在新版的 Anaconda 中就可以安装R语言的集成开发环境 Rstudio。

虚拟环境管理： 在conda中可以建立多个虚拟环境，用于隔离不同项目所需的不同版本的工具包，以防止版本上的冲突。对纠结于 Python 版本的同学们，我们也可以建立 Python2 和 Python3 两个环境，来分别运行不同版本的 Python 代码。

### 1. 下载

https://www.continuum.io/downloads

### 2. 安装

直接点击一路安装即可。

安装完anaconda，就相当于安装了Python、IPython、集成开发环境Spyder、一些包等等。

Anaconda Navigtor ：用于管理工具包和环境的图形用户界面，后续涉及的众多管理命令也可以在 Navigator 中手工实现。

Jupyter notebook ：基于web的交互式计算环境，可以编辑易于人们阅读的文档，用于展示数据分析的过程。

qtconsole ：一个可执行 IPython 的仿终端图形界面程序，相比 Python Shell 界面，qtconsole 可以直接显示代码生成的图形，实现多行代码输入执行，以及内置许多有用的功能和函数。

spyder ：一个使用Python语言、跨平台的、科学运算集成开发环境。

 输入conda list来看一下所有安装时自带的Python扩展。包括了常用的Numpy，Scipy，matplotlib和 networkx 等，以及beautiful-soup，requests，flask，tornado等网络相关的扩展。

安装完成后，我们还需要对所有工具包进行升级，以避免可能发生的错误。
```
conda upgrade --all
```

### 3. python包管理

主要命令如下：
```
conda list #查看已安装列表  
conda install scikit-learn #安装某一个包  
conda install numpy scipy pandas #安装多个包  
conda install numpy=1.10 #设定安装包版本  
conda remove package_name #删除  
conda update package_name #更新  
conda search search_term #模糊查询  
```

### 4. Python环境管理

默认的环境是root，你也可以创建一个新环境。
```
conda create -n py2 python=2.7 pandas
```
其中，py2是env_name，后面可设定Python版本和需要安装包的列表。

其他常用操作如下：
```
conda env list #显示所有环境  
activate env_name #启动某个环境  
deactivate #退出  
conda env remove -n env_name #删除  
conda env export > environment.yaml #将当前环境下的package信息存入YAML文件中  
conda env create -f environment.yaml #用他人分享的YAML文件来创建一样的运行环境  
```

----

**参考资料：**

[1]《致Python初学者们-Anaconda入门使用指南》  
http://www.th7.cn/Program/Python/201702/1115361.shtml

[2]《Anaconda安装及使用教程》  
http://www.360doc.com/content/16/1029/18/25664332_602357786.shtml
