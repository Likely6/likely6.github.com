---
title: 补0的两种方法
date: 2018-02-16
categories: JS ES6
tags: JS ES6
---

>ES6方法  str.repeat(n) 返回一个新字符串，表示将原字符串重复n次

{% highlight r %}
/**
 * @parama  {Number String} 需要补0的数字
 * @paramb  {Number} 该串数字的长度
 * @return  {String}
 */
# 方法一
let addZero = (str, length = 2) => {
	str = str.toString()
	if (str.length > length) {
		return str
	}
	return (Array(length).join('0') + str).substr(-length)
}
# 方法二
let addZero = (str, length = 2) => {
	str = str.toString()
	length = str.length < length ? length - str.length : 0
	return '0'.repeat(length) + str
}
{% endhighlight %}
