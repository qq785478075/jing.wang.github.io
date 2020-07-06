---
title: react组件的声明
tags: [react]
categories: [react]
date: 2019-02-20 14:03:05
comments: false
---

react 学习笔记之 组件的声明
<!-- more -->

# 语法介绍

##  ReactDOM.render

* 作用：描画DOM
* 参数1：DOM对象
* 参数2：注入点

例：
```html
ReactDOM.render(
    <h1>Hello, world!</h1>,
    document.getElementById('example')
);

```

# 组件的声明

## ES5:

```html
var Hello = React.createClass({
    render:function(){
        return(
            <div>Hello World!</div>
        )
    }
})

```

## ES6:
```html
class Hello extends React.Component{
    render(){
        return(
            <div>Hello World!</div>
        )
    }
}

```