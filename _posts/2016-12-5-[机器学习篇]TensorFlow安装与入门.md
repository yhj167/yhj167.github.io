---
layout:     post
title:      "[机器学习篇]TensorFlow安装与入门"
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

### 1.安装pip
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



###2.安装TensorFlow

下载tensorflow（可以百度网盘直接下载，避免FQ）。 网盘地址： 
https://pan.baidu.com/s/1dE2i9tn
这一步看似比较简单，我在安装的时候就踩到了很多坑，折腾了半天才整好。在这里也主要讲解一下这里的坑。

安装的时候一直报错，主要是应为需要去下载几个依赖包，其中最重要的就是six-1.10.0,这个包需要去pypi.python.org下载，起初自己下载安装了，但是还是有问题，在python 
中查看包的版本始终是six-1.4.1,最后终于把six文件删除之后才把python的默认包指向到1.10.0，终于安装成功。（注意这里要安装成功还必须要有文件处理权限，OSX 
10.11为大家添加了rootless来保护一些系统文件，关闭请参考其他文章，有关闭的详细步骤）
在安装six模块成功后，还需要安装其他的一些依赖，这里再食用一种新办法：使用国内的一些pypi源。最终在清华大学的源上，下载到了six－1.10.0模块，同时通过在pip命令中添加 
https://pypi.tuna.tsinghua.edu.cn/simple/选项，可以实现依赖包的自动下载，其中比较重要的是numpy包。
网上有的教程是安装virtualenv来隔离环境，安装可以成功，但是在建议环境的时候需要下载python的环境所需包，在这里没有命令制定pypi源，最终没有实现安装，所以采取了这一极端的方法。
