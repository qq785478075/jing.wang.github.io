---
title: Hexo+github搭建博客笔记
date: 2018-02-28 11:48:43
tags: [hexo] 
categories: 笔记
comments: false
---
基于Hexo和github搭建的个人博客，安装过程及问题在此做的不定期整理，并会随时上传至github平台
<!--more-->

#安装Node
[node官网下载](http://nodejs.cn/)

1. 根据自己的Windows版本选择相应的安装文件，要是不知道，就安装32-bit的吧。如图：
![node安装](http://ww3.sinaimg.cn/large/9fe4afa0gw1faljhotcr1j20dv0atq4u.jpg)
2. 保持默认设置即可，一路Next，安装很快就结束了。 然后我们检查一下是不是要求的组件都安装好了，同时按下Win和R，打开运行窗口。如图：
![node安装](http://ww3.sinaimg.cn/large/9fe4afa0gw1faljikc6nbj20bh06l3z7.jpg)
3. 在新打开的窗口中输入cmd，敲击回车，打开命令行界面。（下文将直接用打开命令行来表示以上操作，记住哦~） 在打开的命令行界面中，输入：
``` html
node -v
npm -v
```
如果结果如下图所示，则说明安装正确，可以进行下一步了，如果不正确，则需要回头检查自己的安装过程。
![node安装](http://ww4.sinaimg.cn/large/9fe4afa0gw1faljiuibwdj20it0cb3zd.jpg)



#安装Git
[Git官网下载](https://git-scm.com/downloads)

* 和Node.js一样，设置都只需要保持默认
* 打开命令行，输入<code>git --version</code>检查是否安装正确,如图：
![Git安装检查](http://ww2.sinaimg.cn/large/9fe4afa0gw1faljp87tpkj20it0cbdgo.jpg)

# github账户的注册和配置

1. 登录进github [GitHub官网](https://github.com/)
2. 创建代码库
 登陆之后，点击页面右上角的加号，选择New repository 如图：
![创建代码库](http://ww2.sinaimg.cn/large/9fe4afa0gw1faljww56v8j20ci0a975c.jpg)
 进入代码库创建页面：
在Repository name下填写 yourname.github.io 如图：
![创建代码库](http://ww4.sinaimg.cn/large/9fe4afa0gw1faljv7hoqhj20p40fz0vo.jpg)
** 注意：比如我的github名称是qq785478075 ,这里你就填 qq785478075.github.io,如果你的名字是xujun，那你就填 xujun.github.io **

# 安装Hexo
** 安装Hexo——确保电脑已经安装Node.js以及Git环境 **
** 命令行在git bash下输入 **
1. 命令行输入：
``` html 
$ npm install -g hexo-cli #全局安装
$ npm install hexo --save
```
2. 查看是否安装成功
``` html 
$ hexo -v
```
3. Hexo相关配置
``` html 
$ hexo init #初始化hexo
$ npm install #安装所需要的组件(生成器)
$ hexo s #运行
```

# 配置Hexo
1. 配置身份信息
``` html 
$ git config -- golbal user.name "yourname"
$ git config -- golbal user.email "youremail"
$ ssh-keygen -t rsa -C "youremail" #生成密钥，密钥位置会给出提示 id_rsa.pub
```

2. 配置身份信息
``` html 
deploy:
	type: git
	repo: git@github.com:yourname/yourname.github.io.git
	branch；master
注：这里的repo中填写的是SSH-Key
```


3. 连接代码库
登录Github，点击头像下的settings，添加ssh

 新建一个new ssh key，将id_rsa.pub文件里的内容复制上去

 输入 ssh -T git@github.com，测试添加ssh是否成功。如果看到Hi后面是你的用户名，就说明成功了

4. 在生成以及部署文章之前，需要安装一个扩展：npm install hexo-deployer-git --save 

5. 使用编辑器编好文章，那么就可以使用命令：hexo d -g，生成以及部署了	
> 假如ssh-key配置失败，那么只要以下步骤就能完全解决
> 首先，清除所有的key-pair
> ssh-add -D
> rm -r ~/.ssh
> 删除你在github中的public-key
> 重新生成ssh密钥对
> ssh-keygen -t rsa -C "xxx@xxx.com"



