---
title: Hexo 错误记录
date: 2020-03-02 15:16:17
tags: [hexo] 
categories: [hexo]
comments: false
---


 Hexo 错误记录
<!--more-->

大致错误如下:
```html
FATAL Something's wrong. Maybe you can find the solution here: https://hexo.io/docs/troubleshooting.html
TypeError [ERR_INVALID_ARG_TYPE]: The "mode" argument must be integer. Receivedan instance of Object
```
![](/images/1593746937.jpg)

在百度多次搜索、验证，验证找到错误原因为node.js版本太高导致，但是自己又不想卸载原本的nodejs版本，所以在网上找了个叫 [<font color="red">nvm</font>](https://github.com/coreybutler/nvm-windows) 的工具降低 node的版本；接下来就可以 <font color="red">hexo g -d</font>  完美解决此次错误

```html
Error: ERROR: The key you are authenticating with has been marked as read only.
fatal: Could not read from remote repository.
```
![](/images/1593748047(1).jpg)
![](/images/2020-07-03_132647.png)

在配置ssh key文件时勾选上<font color="red">Allow write access</font> 选项