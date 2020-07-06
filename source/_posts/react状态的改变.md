---
title: react状态的改变
tags: [react]
categories: [react]
date: 2019-02-20 14:03:05
comments: false
---

react 学习笔记之 状态的改变
<!-- more -->

** getInitlState:定义初始状态（ES6中已不再使用，改成在constructor中设定）**
** this.state: 读取状态 **
** this.setState:更新组件的状态 **

## 知识点补充：
** constructor **是ES6中一种用于创建和初始化class创建的对象的特殊方法
使用 ** constructor ** 方法：
例1：

```html
class Square extends Polygon {
    constructor(length) {
        // 在这里, 它调用了父类的构造函数, 并将 lengths 提供给 Polygon 的"width"和"height"
        super(length, length);
        // 注意: 在派生类中, 必须先调用 super() 才能使用 "this"。
        // 忽略这个，将会导致一个引用错误。
        this.name = 'Square';
    }
    get area() {
        return this.height * this.width;
    }
    set area(value) {
        // 注意：不可使用 this.area = value
        // 否则会导致循环call setter方法导致爆栈
        this._area = value;
    }
}

```
例2：

```html
class Polygon {
    constructor() {
        this.name = "Polygon";
    }
}

class Square extends Polygon {
    constructor() {
        super();
    }
}

class Rectangle {}

Object.setPrototypeOf(Square.prototype, Rectangle.prototype);

console.log(Object.getPrototypeOf(Square.prototype) === Polygon.prototype); //false
console.log(Object.getPrototypeOf(Square.prototype) === Rectangle.prototype); //true

let newInstance = new Square();
console.log(newInstance.name); //Polygon

```

如前所述，如果不指定构造方法，则使用默认构造函数。对于基类，默认构造函数是：

```html
constructor() {}

```

对于派生类，默认构造函数是：
```html
constructor(...args) {
  super(...args);
}

```

** super() ** s说明：执行父类的构造器
