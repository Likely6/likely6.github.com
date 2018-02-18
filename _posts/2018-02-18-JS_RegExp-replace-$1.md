---
title: 正则\$1-\$9在replace方法中的应用 —— 解析url中的参数
date: 2018-02-18
categories: JS
tags: JS RegExp
---

>RegExp.`$`1...`$`9属性用于获取正则表达式中某子表达式匹配的文本内容，每个()内的表达式就是一个子表达式，()也叫一个分组

### 例子
{% highlight r %}
let reg = /^(\d{4})-(\d{1,2})-(\d{1,2})$/
let date = '2018-02-17'
date.match(reg);
let s1 = RegExp.$1
let s2 = RegExp.$2
let s3 = RegExp.$3
console.log(s1, s2, s3)	//return '2018' '02' '17'
{% endhighlight %}

### 使用replace方法与$1解析url
{% highlight r %}
/**
 * @parama  {String}
 * @return  {Object}
 */
let parseUrl = (url) => {
	let reg = /([^?&=]+)=([^?&=]*)/g
	let obj = {}
	url.replace(reg, (res, $1, $2) => {
		obj[$1] = $2
	})
	return obj
}
let url = 'http://gh.moment16.com?id=6&type=js'
console.log(parseUrl(url)) //return {id:'6', type: 'js'}
{% endhighlight %}
>replace({String Regexp},{String Function})

	url.replace(reg, (res, $1, $2, ..., index, str) => {
		// 以上面的url为例 第一次匹配到时
		// res = 'id=6'	匹配到的文本
		// $1 = 'id'	$1是表达式中的第一个分组里的文本
		// $2 = '6'	$2是表达式中的第二个分组里的文本
		// index = 23    index为匹配到的文本在url中的位置
		// str = 'http://gh.moment16.com?id=6&type=js'
	}
