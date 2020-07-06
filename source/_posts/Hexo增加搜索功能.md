---
title: Hexo增加搜索功能
tags: [hexo]
categoties: [hexo, 笔记]
data: 2020-07-06
---

随着时间的推移，博客文章越来越多。为了方便快速找到文章，增加一个站点内的搜索功能是非常必要的。
<!-- more -->

#具体操作：
1.安装搜索：在Hexo的根目录下，打开命令可执行窗口，执行如下命令：
```html
npm install hexo-generator-search --save
```

2.全局配置文件_config.yml，新增如下内容：
```html
search:
  path: search.xml
  field: post
  format: html
  limit: 10000
```

3.hexo主题配置文件（\themes\next_config.yml），修改local_search的enable为true：
```html
# Local search
# Dependencies: https://github.com/flashlab/hexo-generator-search
local_search:
  enable: true
  # if auto, trigger search by changing input
  # if manual, trigger search by pressing enter key or search button
  trigger: auto
  # show top n results per article, show all results by setting to -1
  top_n_per_article: 1
```