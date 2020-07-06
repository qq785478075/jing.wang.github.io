---
title: vue-cli 3.0
date: 2019-03-26 14:03:05
tags: [vue]
categories: [vue, vue3.0]
comments: false
---

vue-cli 3.0搭建项目
<!--more-->

#安装全局快速原型设计
```html
npm install -g @vue/cli-service-global
```

#使用以下命令来创建新项目
```html
vue create hello-world
```
如下图所示：
![](/images/1593768388483.png)

这个默认的设置非常适合快速创建一个新项目的原型，而手动设置则提供了更多的选项，它们是面向生产的项目更加需要的。

如下图所示：
![](/images/1593768385539.png)

选择后按回车键

如下图所示：
![](/images/1593768387042.png)

#根目录下新建  vue.config.js 文件
```html
module.exports = {
    publicPath: process.env.NODE_ENV === 'production' ? './' : './',//部署应用包时的基础路径
    outputDir: 'test',//生产环境构建文件的目录
    assetsDir: '',//放置生成的静态资源 (js、css、img、fonts) 的 (相对于 outputDir 的) 目录
    indexPath:'index.html',//指定生成的 index.html 的输出路径 (相对于 outputDir)。也可以是一个绝对路径
    filenameHashing:true,//生成的静态资源文件名中包含了是否 hash
    transpileDependencies:[],//如果你想要通过 Babel 显式转译一个依赖，可以在这个选项中列出来
    productionSourceMap:false,//是否需要map文件
    css:{
        modules:true,//是否允许css预处理（scss|sass|less|styl）文件
    }
}
```