---
title: 关于移动端图标点击范围太小问题
date: 2018-02-16
categories: 前端 CSS
tags: CSS SCSS
---

{% highlight r %}
@mixin extend-click() {
	position:relative;
	&:before {
		content: '';
		position: absolute;
		top: -10px;
		right: -10px;
		bottom: -10px;
		left: -10px;
	}
}
{% endhighlight %}