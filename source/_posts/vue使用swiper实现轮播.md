---
title: vue使用swiper实现轮播
date: 2019-03-26 14:03:05
tags: [vue, swiper]
categories: [vue, 工具]
---

vue使用swiper实现轮播
<!--more-->
[swiper官网](http://www.swiper.com.cn/demo/index.html)
    

#第一步：安装swiper
```html
npm install --save swiper
```
#第二步：写template
案例：
```html
<template>
	<div id="">
        <div class="swiper-container">
            <div class="swiper-wrapper">
                <div class="swiper-slide" v-for="str in listImg" :style="{ backgroundImage: 'url(' + str.url + ')' }"></div>
            </div>
            <div class="swiper-pagination swiper-pagination-white swiper-pagination-clickable swiper-pagination-bullets">
                <span class="swiper-pagination-bullet" v-for="str in listImg"></span>
            </div>
        </div>
	</div>
</template>

<script>
	import Swiper from 'swiper'
    import 'swiper/dist/css/swiper.min.css'
    import a from '../assets/benner/yichihei.jpg'
    import b from '../assets/benner/yixihei.jpg'
	export default{
		mounted() {
			var mySwiper = new Swiper('.swiper-container',{
				pagination: {//分页器
				    el: '.swiper-pagination',
				    type: 'bullets',//分页器样式
				    clickable :true//是否可以点击
				  },
				loop: true,//无限轮播
                speed: 600,//平滑的速度
				autoplay:true//自动轮播滑动
				})
       },
       data(){
       		return{
       			listImg:[
       				{url:a},
       				{url:b},
       				{url:a}
       				
       			]
       		}
       }

	}
</script>

<style >
	.swiper-container {
		width: 100%;
		height: 10rem;
		margin-top: 44px;
	}
	
	.swiper-container .swiper-wrapper {
		width: 100%;
		height: 100%;
	}
	
	.swiper-slide {
		background-position: center;
		background-size: cover;
		width: 100%;
		height: 100%;
	}
	
	.swiper-slide img {
		width: 100%;
		height: 100%;
	}
	
	.swiper-pagination-bullet {
		width: 0.833rem;
		height: 0.833rem;
		display: inline-block;
		background: #ff5b06;
		opacity:1;
	}
	
</style>
```