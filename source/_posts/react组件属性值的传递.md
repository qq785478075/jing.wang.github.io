---
title: react组件属性值的传递
tags: [react]
categories: [react]
date: 2019-02-20 14:03:05
comments: false
---

react 学习笔记之 组件属性值的传递
<!-- more -->

#组件接收属性值的传递：

this.props.属性名

例：
```html
<Header title="留言" />
var Header = React.createClass({
    render:function(){
        return <h2>{this.props.title}</h2>
    }
})
```

如果需要验证接收属性值数据类型需安装 ` prop-types ` 模块
```html
npm install prop-types

```
然后通过下面的写法对你的某一个组件的道具中的变量进行类型检测：

```html
yourComponent.propTypes = {
    属性1：属性1的变量类型，
    属性2：属性2的变量类型
    //...
}
```

# 检测全部数据类型的变量

```html
Son.propTypes = {
     optionalArray: PropTypes.array,//检测数组类型
     optionalBool: PropTypes.bool,//检测布尔类型
     optionalFunc: PropTypes.func,//检测函数（Function类型）
     optionalNumber: PropTypes.number,//检测数字
     optionalObject: PropTypes.object,//检测对象
     optionalString: PropTypes.string,//检测字符串
     optionalSymbol: PropTypes.symbol,//ES6新增的symbol类型
}
```