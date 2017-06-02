---
title: Hexo搭建个人博客 
tags: hexo 
---

**缘起**
=================

今天终于下定决心搭建好了自己的个人博客。其实很早就一直有这个想法，但是不太了解git以及github，听说hexo更是不知道是什么东西。最近，我再寻找一种代替svn的东西来管理我的代码和项目，所以有兴趣去了解了一下git，并在自己电脑上搭建好了环境，试着玩一些简单的操作。今天偶然看别人的博客域名居然是`.github.io`结尾，正好最近在学习这一块，于是就网上搜索了一下，原来就是用hexo搭建的自己的博客系统，非常方便，于是自己也尝试了一把，途中磕磕绊绊，终于搞定了，目前还处于材料阶段，正在深入。今天把我的经验分享出来。

  

**安装git**
=================

根据你的终端，可以去git官网下载最新的[git安装包](https://git-scm.com/download)，并安装到计算机上。
![](/imgs/git-windows.png)

  

**关联github**
=================

1  在[github](https://github.com)上注册账号

2  创建仓库：注意，仓库名一定是`[github用户名].github.io`，点击`Create repository`即可

3 生成添加秘钥：在终端Git Bash执行：

```BASH
ssh-keygen -t rsa -C "Github的注册邮箱地址"
```

一路`Enter`过来就好，待秘钥生成完毕，会得到两个文件**id_rsa**和**id_rsa.pub**，用带格式的记事本打开id_rsa.pub，Ctrl + a复制里面的所有内容，然后进入[https://github.com/settings/ssh](https://github.com/settings/ssh)，将复制的内容粘贴到Key的输入框，随便写好Title里面的内容，点击`Add SSH key`按钮即可

  

**安装node.js**
=================
点击进入[node.js官网](https://nodejs.org/en/)

目前node.js有两个推荐版本，分为[通用版](https://nodejs.org/dist/v4.6.0/node-v4.6.0.pkg)和[最新版](https://nodejs.org/dist/v6.7.0/node-v6.7.0.pkg)，点击可直接进行下载。下载好后，按照既定的套路安装即可

**安装hexo**
=================


**初始化博客**
=================


**配置博客**
=================


**新增文章**
=================


**发布服务**
=================
