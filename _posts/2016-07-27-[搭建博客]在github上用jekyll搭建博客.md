---
layout:     post
title:      "[搭建博客]在github上用jekyll搭建博客"
subtitle:   ""
date:       2016-07-27 20:20:00
author:     "Yinhj"
header-img: "img/post-bg-re-vs-ng2.jpg"
header-mask: 0.3
catalog:    true
tags:
- jekyll
- 搭建博客

---


## 前言

Yinhj 的 Blog 就这麽开通了。
[跳过前言](#jump)

2016年，Yinhj总算有个地方可以写点自己的东西了。

以前不喜欢在大众博客网站上写东西，一是感觉不好用，二是我们单位上不了外网-_-!!!。总之写点东西非常麻烦，导致实践中没有很好地形成总结，这样对长期的自身发展来说不好，实践中的一些思考过一阵又忘了，缺少积累。

于是周末花了两天时间，在github上建了自己的博客，但是要写一个漂亮的博客还需要漂亮的模板，看上了基于jekyll和hexo实现的两种模板，前者基于ruby实现，后者基于node.js实现。个人还是喜欢jekyll，[jekyllthemes](http://jekyllthemes.org)上供下载的模板很多，[知乎](https://www.zhihu.com/question/20223939)上分享的模板也很多。编辑博客用markdown脚本来写([详细教程](http://wowubuntu.com/markdown/#list))，编辑器有很多，我比较喜欢[Typora](http://typora.io)，即写即现。主要的时间还是花在模板移植上了，环境安装和修改，第一次还是花了不少时间！

如果不想每次更新博客后都要提交一遍才能看效果，可以启动本地jekyll服务:
> $ jekyll serve --watch
然后访问http://localhost:4000，按CTRL+C退出。


<p id = "jump"></p>
---

### 参考资料

[用github + Jekyll写博客](http://blog.csdn.net/u014015972/article/details/50497254)

[Mac下Jekyll安装](http://www.jianshu.com/p/07064eb79740)

[Jekyll+多说，建立属于你的轻博客](http://www.ituring.com.cn/article/114888)

