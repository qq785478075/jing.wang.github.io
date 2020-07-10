---
title: ElementUI时间限制
tags: [vue, Element ui]
categories: [vue, Element ui]
date: 2020-07-10
---

在使用Element UI中，时间选择器是一个常用的模块；而在开发中时间限制是常用的一项功能。
<!-- more -->
```html
<el-date-picker
    v-model="searchData.createTime"
    type="date"
    :picker-options="pickerOptions"
    :editable="false"
    value-format="yyyy-MM-dd"
    placeholder="选择申请时间"
    ></el-date-picker>
```

```html 
data(){
    return{
        pickerOptions: {
        disabledDate(time) {
          //   return time.getTime() < Date.now() - 8.64e7;//设置选择今天以及今天之后的日
          return time.getTime() > Date.now(); //设置选择今天以及今天以前的日期
          //   return time.getTime() < Date.now();//设置选择今天之后的日期（不能选择当天时间）
          //   return time.getTime() > Date.now() - 8.64e7; //设置选择今天之前的日期（不能选择当天）
        }
      },
    }
}
```

效果如下：
![](/images/Video_2020-07-10_180853.gif)