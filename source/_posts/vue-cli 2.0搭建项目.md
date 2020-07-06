---
title: vue2.0搭建项目
date: 2018-05-01 14:03:05
tags: [vue]
categories: [vue, vue2.0]
comments: false
---

vue2.0搭建项目说明
<!--more-->
[Vue官网链接](https://cn.vuejs.org/v2/guide/installation.html)
[Vue安装教程链接](https://www.cnblogs.com/binmengxue/p/6831850.html)

目前vue 已经有了vue 3.0版本了 如需使用vue 2.0旧版本 执行以下命令：
```html
npm install -g @vue/cli-init //获取vue 2.0旧版本

```

# 全局安装 vue-cli
```html
npm install vue  //最新稳定版
npm install --global vue-cli
```
# 创建一个基于 webpack 模板的新项目
```html
vue init webpack my-project
 Project name  //项目名称
 Project description  //项目描述
 Author //作者
 Vue build  //vue的建立
 Install vue-router?   //安装vue路由
 Use ESLint to lint your code？  //该选项为使用ESLint规范你的代码，一个空格错误都将报错，不开启，避免不必要的麻烦
 Set up unit tests？  //设置单元测试
 Setup e2e tests with Nightwatch   // Nightwatch建立端到端的测试
 Should we run `npm install` for you after the project has been created? (recommended) (Use arrow keys)  //确认创建项目
```
如下图：
![](/images/image1.png)

# 安装依赖，走你
```html
cd my-project  //跳转至my-project文件路径下
npm install   //初始化webpack模块
npm run dev   //启动服务器
npm install vue-router vue-resource --save  //安装路由模块
```

如下图：
![](/images/image2.png)