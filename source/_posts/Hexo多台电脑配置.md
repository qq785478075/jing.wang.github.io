---
title: Hexo 多台电脑配置
date: 2020-03-02 15:16:17
tags: [hexo] 
categories: [hexo]
comments: false
---

Hexo 多台电脑配置
<!--more-->

在之前的一篇文章中描述了[<font color="red">Hexo 加 github搭建</font>](/Hexo-github搭建博客笔记/#more)怎么从零开始搭建、备份<font font-size="12px" color="blue">个人博客</font>的文章

今天说一下多台电脑同时配置 hexo

首先确保自己已经使用hexo在github搭建好了自己的个人博客。
![](/images/2020-07-03_162103.png)

对username.github.io仓库 hexo分支拉取到本地;
命令如下：
```html
git clone https://github.com/*****/****.github.io.git

```
此时从github 拉取的代码为 master主分支 这是我们需要切换分支，命令如下：
```html
git chckout hexo
//hexo 为切换分支的名称
```
此时本地会有一个新的hexo项目，但是由于.gitignore文件中过滤了node_modules\，所以克隆下来的目录里没有node_modules\，这是hexo所需要的组件，所以要在该目录中重新安装hexo，但不需要hexo init。
```html
npm install hexo
npm install hexo --save
npm install
npm install hexo-deployer-git --save

```

####新建一篇文章测试
```html
hexo s //本地服务
```

####推送到hexo分支
```html
git add .
git commit -m "add work PC test"
git push origin hexo
```

####部署到master分支
```html
hexo g -d
```

####日常操作
如果上面的过程都操作无误的话，你就可以在任何能联网的电脑上写博客啦。一般写博客的流程是下面这样。

####写博客前
不管你本地的仓库是否是最新的，都先pull一下，以防万一：
```html
git pull origin hexo
```

写博客
hexo new “title”
然后打开source/_posts/title.md，撰写博文。

写完博客
先推送到hexo分支上：
```html
git add .
git commit -m "add work PC test"
git push origin hexo
```

最后部署到master分支上
```html
hexo g -d
```
整个流程大概就是这样。