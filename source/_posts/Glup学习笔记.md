---
title: Glup学习笔记
date: 2018-03-02 15:16:17
tags: [gulp] 
categories: [笔记,打包工具]
comments: false
---

使用Gulp打包压缩Html、Css、Js
<!--more-->
1. node.js 安装
2. 淘宝镜像的安装：<code>npm install -g cnpm --registry=https://registry.npm.taobao.org</code>
3. 全局安装gulp:<code>cnpm install --global gulp</code>
4. 项目安装gulp:<code>cnpm install --save-dev gulp</code>
5. 初始化一个package.json文件：<code>gulp init</code>
6. 然后执行:<code>cnpm install gulp --save-dev</code>
7. 项目安装gulp插件如编译less文件:<code>cnpm install --save-dev  gulp-less （less编译）</code>
``` html
cnpm install --save-dev  gulp-sass	（sass编译）
cnpm install --save-dev gulp-uglify （JS压缩）
cnpm install --save-dev gulp-minify-html（html压缩）
cnpm install --save-dev gulp-concat （js文件合并）
cnpm install –-save-dev  gulp-imagemin （图片压缩）
cnpm install --save-dev gulp-babel  (es6语法)
npm install --save-dev gulp-babel babel-preset-env (es6语法)
cnpm install --save-dev babel-preset-es2015  (es6转换es5)
cnpm install --save-dev gulp-connect  (自动刷新)

```

删除安装的外挂：

首先在全局安装<code>npm i -g rimraf</code>； 
然后转到你的根目录输入  <code>rimraf -rf node_modules/package</code>(package 依旧是外挂名字  比如  <code>gulp-less</code>);