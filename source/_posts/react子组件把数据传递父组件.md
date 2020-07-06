---
title: react子组件把数据传递父组件
tags: [react]
categories: [react]
date: 2019-02-20 14:03:05
comments: false
---

react 学习笔记之 子组件把数据传递父组件
<!-- more -->

列：
```html
import React, { Component } from 'react';
import PropTypes from 'prop-types'; //传参数据类型检测模块
import './App.css';

//组件的声明
class Hello extends React.Component {
  constructor() { 
    super();
    //初始化state
    this.state = {
      list:['HTML','CSS','JavaScript','Vue','React']
    };
    //推荐这种修正指针方式。如果不修正指针方法this指向不正确。
    this.addList = this.addList.bind(this);
  };

  addList(){
    //获取input的输入值
    let val = this.refs.addVal.value;
    //更改数组
    this.state.list.push(val);
    //初始化input框的值
    this.refs.addVal.value = '';
    console.log(this.state.list);
    //更新页面数据。如果不执行一下步骤，数据是改变了，但是页面数据没有刷新
    this.setState({
      list:this.state.list
    })
  }

  render() {
    return (
      <div>
        <h1>{this.state.message}</h1>
        <div>{this.props.title}</div>
        <input type='text' ref='addVal'/>
        <button onClick={this.addList}>Add List</button>
        <br/>
        <button onClick={()=>{this.props.sendDataFromChild('这是子组件传递过来的数据')}}>数据从子到父的传递</button>
        <ul>
          {/*读取state数据 */}
          {
            this.state.list.map((item,i)=>{
              return <li key={i}>{item}</li>
            })
          }
        </ul>
      </div>
    )
  };
}

//限制传参的数据类型
Hello.propTypes = {
  title: PropTypes.string,
}

class App extends Component {
  constructor(){
    super();
    this.state = {
      message:'父组件的数据'
    }
    //修正指针
    this.sendDataFromChild = this.sendDataFromChild.bind(this)
  };

  sendDataFromChild(val){
    this.setState({
      message:val
    })
  }

  render() {
    return (
      <div className="App">
        <h1>{this.state.message}</h1>
        <Hello title="标题测试" sendDataFromChild={this.sendDataFromChild}/>
      </div>
    );
  }
}

export default App;

```