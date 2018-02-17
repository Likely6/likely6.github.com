---
title: 传入date对象和日期格式返回格式化后的日期
date: 2018-02-16
categories: JS
tags: JS
---

{% highlight r %}
/**
 * @parama  {Object} Date对象
 * @paramb  {String} 日期格式 如:'yyyy-MM-dd hh:mm:ss' | 'yy年MM月dd日 hh时mm分'
 * @return  {String}
 */
let formatDate = (date, fmt = 'yyyy-MM-dd hh:mm:ss') => {
	if (/(y+)/.test(fmt)) {
		fmt = fmt.replace(RegExp.$1, date.getFullYear().toString().substr(-RegExp.$1.length))
	}
	let o = {
		'M+': date.getMonth() + 1,
		'd+': date.getDate(),
		'h+': date.getHours(),
		'm+': date.getMinutes(),
		's+': date.getSeconds()
	}
	for (let i in o) {
		if (RegExp(`(${i})`).test(fmt)) {
			let str = o[i].toString()
			fmt = fmt.replace(RegExp.$1, RegExp.$1.length === 1 ? str : ('0'+str).substr(-2))
		}
	}
	return fmt
}
{% endhighlight %}
