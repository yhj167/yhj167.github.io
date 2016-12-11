---
layout:     post
title:      "[机器学习]TensorFlow安装与入门"
subtitle:   ""
date:       2016-12-5 20:00:00
author:     "Yinhj"
header-img: "img/post-bg-re-vs-ng2.jpg"
header-mask: 0.3
catalog:    true
tags:
- TensorFlow
- 机器学习

---


​    virtualenv 可以用来建立一个专属于项目的python环境，保持一个干净的环境。只需要通过命令创建一个虚拟环境，不用的时候通过命令退出，删除。**实践证明用虚拟环境能避免很多糟心的事。**

下面介绍一下安装方法：

安装 virtualenv;

安装 virtualenvwrapper;

安装 Numpy，Scipy，Matplotlib 等Python科学计算的库;

### 1.安装 virtualenv
> $ sudo pip install virtualenv

然后建立一个测试目录：

> $ mkdir testvirtual
>
> $ cd testvirtual

就可以成功创建一个虚拟环境 env1：

> $ virtualenv env1

进入env1:

> source env1/bin/activate

退出:

> deactivate

### 2.安装 virtualenvwrapper

Virtaulenvwrapper是virtualenv的扩展包，可以更方便地新增，删除，复制，切换虚拟环境。

运行下面命令就安装成功了，默认安装在 /usr/local/bin下面：

> $ sudo easy_install virtualenvwrapper

接下来创建一个文件夹，用来存放所有的虚拟环境：

> $ mkdir ~/workspaces
>
> $ cd ~/workspaces

但是在使用virtualenvwrapper之前，要运行virtualenvwrapper.sh文件，需要设置环境变量，vim  ~/.bashrc打开配置文件，把下面两行代码加上，**但是mac比较特殊直接写不管用**。

> export WORKON_HOME=~/workspaces
>
> source /usr/local/bin/virtualenvwrapper.sh

因为**unix下当shell是login shell，.bash_profile才加载，而.bashrc相反**。
Linux下，打开终端terminal是non-login shell。
OSX下，运行Terminal.app是一个login shell，所以.bash_profile会加载，而bashrc不会加载。

直接在命令行写也可以，但是每次启动shell都要手动输入很麻烦，下面是解决方法是 vim ~/.bash_profile打开配置文件把下面代码加上：

> if [ "${BASH-no}" != "no" ]; then
>
> ​	[ -r ~/.bashrc ] && . ~/.bashrc
>
> fi

接下来，创建一个或者多个虚拟环境 env1，env2：

> $ mkvirtualenv env1

成功后，当前路径前面就会有 (env1)

> $ mkvirtualenv env2

#### 下面是一些基本操作命令

列出虚拟环境：

> $ lsvirtualenv -b

> env1
>
> env2

切换虚拟环境：

> $ workon env1

查看环境里安装了哪些包：

> $ lssitepackages

进入当前环境：

> $ cdvirtualenv

进入当前环境的site-packages：

> $ cdsitepackages
>
> $ cdsitepackages pip

复制虚拟环境：

> $ cpvirtualenv env1 env3
>
> Copying env1 as env3...

退出虚拟环境：

> $ deactivate

删除虚拟环境：

> $ rmvirtualenv env2

> Removing env2...

### 3.安装 Numpy，Scipy，Matplotlib 等

接下来安装Python的各种包，就比较顺畅了，比如安在env1上：

```
$ workon env1
```

**安装numpy**
`pip install numpy`

我没安装成功，然后下载后本地安装的：

```
pip install /Users/Angela/Downloads/numpy-1.11.2-cp27-cp27m-macosx_10_6_intel.macosx_10_9_intel.macosx_10_9_x86_64.macosx_10_10_intel.macosx_10_10_x86_64.whl
```

最好都本地安装，大多直接安装不成功。如果在线安装超时，可以建个文件：

```
mkdir ~/.pip
vim ~/.pip/pip.conf
```

内容如下，设置超时时间和指定源：

```
[global]
timeout = 6000
index-url = http://e.pypi.python.org/simple
[install]
use-mirrors = true
mirrors = http://e.pypi.python.org
```

**安装scipy**
`$ pip install scipy`

**安装matplotlib**
`$ pip install matplotlib`

**安装ipython**
`$ pip install ipython[all]`

**安装pandas**
`$ pip install pandas`

**安装Statsmodel**
`$ pip install statsmodel`

**安装scikit-learn**
`$ pip install scikit-learn`

按照顺序全部安装成功，后续就可以在虚拟环境上做分析了。

------

以后每次进入虚拟环境就执行如下代码即可：

```
$ workon env1
$ cdvirtualenv
```

退出虚拟环境就用

```
$ deactivate
```

### 4.virtualenv自带pip，如果不用虚拟环境也行。
安装pip方法如下：
pip是常用的Python包管理工具，类似于Java的maven。用python的同学，都离不开pip。 
在新mac中想用home-brew安装pip时，遇到了一些小问题：

<pre><code>
bogon:~ wanglei$ brew install pip
Error: No available formula with the name "pip"
Homebrew provides pip via: `brew install python`. However you will then
have two Pythons installed on your Mac, so alternatively you can install
pip via the instructions at:

  https://pip.readthedocs.org/en/stable/installing/#install-pip
</code></pre>

由此可见，在home-brew中，pip的安装是跟python一起的。

换种方式：

<pre><code>
bogon:~ wanglei$ sudo easy_install pip
Password:
Searching for pip
Reading https://pypi.python.org/simple/pip/
...
</code></pre>

稍等片刻，pip就安装完毕


### 5.安装TensorFlow

下载tensorflow（可以百度网盘直接下载，避免FQ）。 网盘地址：[tensorflow下载](https://pan.baidu.com/s/1dE2i9tn)。

一些依赖包如果安装不顺畅，可以去pypi.python.org直接下载，比如numpy我没安装上，下载包后本地安装上了。

直接安装依赖包会遇到很多坑，比如和现有版本冲突等安装失败。可以安装virtualenv来隔离环境，会自动安装six-1.10等很多依赖包，之后就可以安装Numpy、Scipy、Matplotlib 等库。

**最后，装完后安装tensorflow**

```
pip install /Users/Angela/Downloads/TensorFlow/mac/tensorflow-0.5.0-py2-none-any.whl
```

我下载的TensorFlow文件放在/Users/Angela/Downloads/目录’下了。

