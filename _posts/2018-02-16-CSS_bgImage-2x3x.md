---
title: 关于移动端针对不同设备像素比时背景图片使用2x图与3x图的解决办法
date: 2018-02-16
categories: CSS
tags: CSS SCSS
---

一般ui都会给出按像素比大小命名好的2x和3x的应对不同设备像素比的背景图片，然后我们可以使用media查询完成在不同像素比的屏幕下图片的引用。

{% highlight r%}
@mixin bg-image($url) {
	background-image: url($url + '@2x.png');
	@media (-webkit-min-device-pixel-ratio: 3), (min-device-pixel-ratio: 3) {
		background-image: url($url + '@3x.png');
	}
}
{% endhighlight %}