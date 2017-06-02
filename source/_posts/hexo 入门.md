---
title: Hexo搭建个人博客 
abstract: 这是摘要
tags: hexo 
---

## 缘起


今天终于下定决心搭建好了自己的个人博客。其实很早就一直有这个想法，但是不太了解git以及github，听说hexo更是不知道是什么东西。最近，我再寻找一种代替svn的东西来管理我的代码和项目，所以有兴趣去了解了一下git，并在自己电脑上搭建好了环境，试着玩一些简单的操作。今天偶然看别人的博客域名居然是`.github.io`结尾，正好最近在学习这一块，于是就网上搜索了一下，原来就是用hexo搭建的自己的博客系统，非常方便，于是自己也尝试了一把，途中磕磕绊绊，终于搞定了，目前还处于材料阶段，正在深入。今天把我的经验分享出来。

  

## 安装git


根据你的终端，可以去git官网下载最新的[git安装包](https://git-scm.com/download)，并安装到计算机上。
![](/imgs/git-windows.png)

  

## 关联github


1  在[github](https://github.com)上注册账号

2  创建仓库：注意，仓库名一定是`[github用户名].github.io`，点击`Create repository`即可

3 生成添加秘钥：在终端Git Bash执行：

```BASH
ssh-keygen -t rsa -C "Github的注册邮箱地址"
```

一路`Enter`过来就好，待秘钥生成完毕，会得到两个文件**id_rsa**和**id_rsa.pub**，用带格式的记事本打开id_rsa.pub，Ctrl + a复制里面的所有内容，然后进入[https://github.com/settings/ssh](https://github.com/settings/ssh)，将复制的内容粘贴到Key的输入框，随便写好Title里面的内容，点击`Add SSH key`按钮即可

  

## 安装node.js

点击进入[node.js官网](https://nodejs.org/en/)

目前node.js有两个推荐版本，分为[通用版](https://nodejs.org/dist/v4.6.0/node-v4.6.0.pkg)和[最新版](https://nodejs.org/dist/v6.7.0/node-v6.7.0.pkg)，点击可直接进行下载。下载好后，按照既定的套路安装即可

  

## 安装hexo

进入[hexo官网](https://hexo.io/)，可以查看相关文档，下面我简述一下我的安装过程

打开git bash，进入到需要安装hexo的文件夹（自己创建）：

```bash
$ cd [安装的文件夹]
```

安装hexo：

```bash
$ npm install hexo-cli -g
```

检查是否安装成功：

```bash
$ hexo
```

  若安装成功，会打印如下信息

![hexo安装成功](/imgs/hexo-1.png)





## 初始化博客

```bash
// 建立一个博客文件夹，并初始化博客，<folder>为文件夹的名称，可以随便起名字，也可以省略，省略则默认当前文件夹
$ hexo init <folder>
// 进入博客文件夹，<folder>为文件夹的名称
$ cd <folder>
// node.js的命令，根据博客既定的dependencies配置安装所有的依赖包
$ npm install
```

初始化博客后，该文件夹下面会生成相应文件

![hexo初始化成功](/imgs/hexo-2.png)



## 配置博客

用格式的编辑器打开`_config.yml`文件，修改相应配置

```
# Hexo Configuration
## Docs: https://hexo.io/docs/configuration.html
## Source: https://github.com/hexojs/hexo/

# Site
title: 这里写博客的标题
subtitle: 这里写博客的子标题
description: 这里写描述
author: 作者
language: zh-CN
timezone: chongqing

# URL
## If your site is put in a subdirectory, set url as 'http://yoursite.com/child' and root as '/child/'
url: http://chenfeng0713.com/
root: /
permalink: :year/:month/:day/:title/
permalink_defaults:

# Directory
source_dir: source
public_dir: public
tag_dir: tags
archive_dir: archives
category_dir: categories
code_dir: downloads/code
i18n_dir: :lang
skip_render:

# Writing
new_post_name: :title.md # File name of new posts
default_layout: post
titlecase: false # Transform title into titlecase
external_link: true # Open external links in new tab
filename_case: 0
render_drafts: false
post_asset_folder: false
relative_link: false
future: true
highlight:
  enable: true
  line_number: true
  auto_detect: false
  tab_replace:

# Category & Tag
default_category: uncategorized
category_map:
tag_map:

# Date / Time format
## Hexo uses Moment.js to parse and display date
## You can customize the date format as defined in
## http://momentjs.com/docs/#/displaying/format/
date_format: YYYY-MM-DD
time_format: HH:mm:ss

# Pagination
## Set per_page to 0 to disable pagination
per_page: 10
pagination_dir: page

# Extensions
## Plugins: https://hexo.io/plugins/
## Themes: https://hexo.io/themes/
theme: Nlvi

# Deployment
## Docs: https://hexo.io/docs/deployment.html
deploy:
  type: git 
  repo: git@github.com:chenfeng0713/chenfeng0713.github.io.git 
  branch: master 

```

上面的配置已经是我改过的配置，其中主要改动两个地方

1 配置博客的相关信息

```
title: 这里写博客的标题
subtitle: 这里写博客的子标题
description: 这里写描述
author: 作者
language: zh-CN
timezone: chongqing
```

2 配置统一资源定位符（个人域名）

```
url: http://chenfeng0713.com/
```

3 配置部署信息

```
deploy:
  type: git 
  repo: git@github.com:chenfeng0713/chenfeng0713.github.io.git 
  branch: master 
```

其中`chenfeng0713`为github上注册的用户名

修改配置文件完成之后保存即可

## 新增文章

在git bash终端输入以下命令新增一个markdown文件

```bash
$ hexo new "文章标题"
```

新建markdown文件在本地博客文件夹`source `> `_posts`下，也可以在该文件夹下直接新建markdown文件,达到同样的效果

用Markdown编辑器打开文件，windows我用的是[Typora编辑器](https://www.typora.io/#windows)，还蛮好用，至于Markdown的语法这里不多讲，自己google



## 发布服务

执行如下命令，进行本地发布：

```bash
$ hexo server
```

发布成功后，在浏览器输入：http://localhost:4000/，就可以在浏览器看到我们搭建好的博客和文章，如果4000端口被占用，可以手动指定端口，如下：

```bash
$ hexo server -p 5000
```

如果要部署在github上，只需要在终端执行以下命令即可：

```bash
$ hexo generate
$ hexo deploy
```

然后我们访问：https://chenfeng0713.github.io就可以啦

注意：执行`deploy`是报错：Deployer not found: git

解决方案：在终端执行命令：

```
npm install hexo-deployer-git --save
```

然后再执行`hexo deploy`即可