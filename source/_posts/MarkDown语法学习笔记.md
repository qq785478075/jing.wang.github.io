---
title: MarkDown语法学习笔记
date: 2018-02-28 14:03:05
tags: [MarkDown]
categories: 笔记
---

关于Markdown的使用手册

<!--more-->

# 标题

1. 用#标记
> 在 标题开头 加上1~6个#，依次代表一级标题、二级标题....六级标题
> #一级标题
> > ##二级标题
> > ###三级标题
> > #####四级标题
> > ######五级标题
> > ######六级标题

2. 用=和-标记
> 在 标题底下 加上任意个=代表一级标题，-代表二级标题
> > This is an H1 =============
> > This is an H2 -------------


# 列表

1.无序列表：在文字前加上 *、-或+即可变成无序列表
> * *red
> + +blue
> - -green

2.有序列表：在文字前加上1.2.3.即可变成有序列表
> 1. red
> 2. blue
> 3. green

> 注：符号和文字之间加上一个字符的空格

# 引用

引用以>来表示，引用中支持多级引用、标题、列表、代码块、分割线等常规语法。

> 这是一段引用    //在`>`后面有 1 个空格
> 
>     这是引用的代码块形式    //在`>`后面有 5 个空格
>     
> 代码例子：
>     
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
    }

> 一级引用
> > 二级引用
> > > 三级引用


# 分割线
在一行中用三个以上的*、-、_来建立一个分隔线
***
---
___

# 强调
两个*或_代表加粗，一个*或-代表斜体，~~代表删除

**加粗文本** 或者 __加粗__
*斜体* 或者 _斜体_
~~删除~~
注：前后都需要添加

#图片与链接

图片为:
``` html5
	![Alt text](/path/to/img.jpg "Optional title")
```
* Alt text 为如果图片无法显示时显示的文字
* /path/to/img.jpg 为图片所在路径 路径可以使用绝对路径也可以使用相对路径，建议使用绝对路径
* Optional title 显示标题。显示效果为在你将鼠标放到图片上后，会显示一个小框提示，提示内容就是Option title 里的内容
* 迁入HTML代码
``` html5

<img scr="./xxx.png" width = "300" height = "200" alt = "图片名称" align = center />

*<div align="center">
	<img/>
</div>
```
* 链接为：
``` html5
	[]()
```


# 换行
``` html5
	<br>
```



	
