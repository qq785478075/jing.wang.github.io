---
title: react中间件
tags: [react]
categories: [react]
date: 2019-02-22 14:03:05
comments: false
---

react 学习笔记之 中间件
<!-- more -->

# Middleware的由来

在redux中，action仅仅是携带了数据的普通js对象。 action creator 返回的值是这个action类型的对象。然后通过store.dispatch()进行分发。

同步的情况下一切都很完美，但是reducer无法处理异步的情况。
例如：我希望点击一个按钮，2秒之后更新视图，显示消息 “Hi”。
那么我们就需要在action 和 reducer之间架起一座桥梁来处理异步。


# Redux异步流

### redux-thunk:
store.disptch 参数可以是一个 function

#### 使用方法：

1. 引入

```html
 import thunk from 'redux-thunk'
```

2. 加入中间件

const store = createStore(fetchReducer,applyMiddleware(thunk))