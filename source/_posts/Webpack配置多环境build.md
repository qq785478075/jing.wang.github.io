---
title: Webpack配置多环境build
tags: [webpack]
categories: [Webpack]
date: 2019-01-30 14:03:05
comments: false
---

用vue cli2.0 脚手架搭建的项目，脚手架默认生成 `dev.env.js`，`prod.env.js` 两个环境变量声明文件，build时默认使用 `prod.env.js` ，这不便于我们分别 build 测试环境和 生产环境代码
<!-- more -->

目前我们的前端项目中使用到Webpack的前提下，在 config 目录下可以看到有 dev.env.js，prod.env.js 两个环境变量声明文件，build时默认使用 prod.env.js ，这不便于我们分别 build 测试环境和 生产环境代码
这个声明文件内容大致如下

###### dev.env.js

```html
'use strict'
const merge = require('webpack-merge')
const prodEnv = require('./prod.env')
 
module.exports = merge(prodEnv, {
  NODE_ENV: '"development"',
  LOGOUT_URL: '"http://sso.example.org:9999/logout"'
})
```

在其中声明的变量可以在我们的代码中通过 process.env.LOGOUT_URL 来引用：
form.action = process.env.LOGOUT_URL
在 build 阶段使用哪个 xxx.env.js 的声明即决定了最终build输出内容中变量的值。
在此我只做抛砖引玉，通过简单的扩展，添加一个自定义的 xxx.env.js 文件，并通过build命令传参来控制使用哪个文件。


比如我们就缺少一个test环境的配置，具体步骤如下：

###### 1、创建 config/test.env.js

```html
'use strict'
module.exports = merge(prodEnv, {
  NODE_ENV: '"test"',
  BASE_API: '"/"',
  LOGOUT_URL: '"http://172.16.0.95/logout"'
})
```

###### 2、创建 process-argv.js
在 build 目录创建 process-argv.js，内容如下：
```html
const processArgv = process.argv.splice(2)
module.exports = processArgv

```

process.argv 用于读取node xxx.js --yyy 命令的传参，比如 --yyy 即参数。但只有第一次使用会得到，再次使用则获取不到，所以单独用一个文件来存储后可多次调用。

###### 3、编辑 build/build.js

将 ` const spinner = ora('building for production...') `这行改为：

```html
const processArgv = require('./process-argv')
if (processArgv.indexOf('--test') >= 0) {
  process.env.NODE_ENV = 'test'
}
const spinner = ora(`building for ${process.env.NODE_ENV}...`)

```

###### 4、编辑 build/webpack.prod.conf.js
将 `  const env = require('../config/prod.env')  ` 这行改为：

```html
let envName = 'prod'
const processArgv = require('./process-argv')
if (processArgv.indexOf('--test') >= 0) {
  envName = 'test'
}
console.log(`building ${envName}`)
const env = require(`../config/${envName}.env`)

```

###### 5、package.json 增加命令
```html
//...
"scripts": {
  "test-build": "node build/build.js --test",
},
...

```

即执行 node build/build.js --test，代表 --test 参数指定了使用 build/test.env.js 作为环境变量声明。
不指定时，则默认仍然是prod。
