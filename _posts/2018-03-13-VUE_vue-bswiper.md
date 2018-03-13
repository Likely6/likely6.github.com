---
title: vue-bswiper轮播组件
date: 2018-03-13
categories: VUE
tags: VUE vue-bswiper better-scroll
---

[vue-bswiper](https://github.com/Likely6/vue-bswiper)是基于[better-scroll](https://ustbhuangyi.github.io/better-scroll/doc/zh-hans/#better-scroll)的vue的轮播组件，它通过props控制是否自动轮播,是否可以循环切换,控制轮播速度、自动轮播时图片切换速度等。

>npm安装

	npm i vue-bswiper --save

<br/>
>props

| 参数 | 说明 | 类型 | 默认值 |
| ---- | ---- | ---- | --- |
| loop | 是否可以循环切换图片 | Boolean | true |
| autoPlay | 是否自动播放 | Boolean | true |
| speed | 动画滚动速度 | Number | 800 |
| interval | 自动切换图片的时间间隔 | Number | 2000 |
| showDot | 是否显示分页器 | Boolean | true |

<br/>
>例子
>html应该按照下面例子的结构,其中a标签可以替换成其他标签

```html
<template>
  <div class="banner">
    <Swiper :autoPlay="false">
      <a href="http://gh.moment16.com">
        <img src="http://d300.paixin.com/thumbs/1016676/40179869/staff_1024.jpg?imageView2/2/w/400/h/400">
      </a>
      <a href="javascript:void(0)">
        <img src="http://d007.paixin.com/thumbs/1003434/9017610/staff_1024.jpg?imageView2/2/w/400/h/400">
      </a>
    </Swiper>
  </div>
</template>
```

```javascript
<script>
import BSwiper from 'vue-bswiper'
export default {
  components: {
    BSwiper
  }
}
</script>
```

```css
<style lang="scss" scoped>
.banner{
  width:100%;
  height: 200px;
}
</style>
```
<br/>