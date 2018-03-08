---
title: 添加浏览器前缀
date: 2018-02-19
categories: JS
tags: JS
---

>js中根据不同浏览器自动添加浏览器前缀

{% highlight r %}
/**
 * parama {String} css属性
 * return {String} 如果没有这个属性返回false 有则返回兼容浏览器的属性
 */
let addPrefix = (style) => {
	let div = document.createElement('div').style
	let ucStyle = style.charAt(0).toUpperCase() + style.substr(1)
	let vender = ['webkit', 'moz', 'o', 'ms']
	for (let i in vender) {
		if (div[vender[i] + ucStyle] !== undefined) {
			return vender[i] + ucStyle
		}
	}
	if (div[style] !== undefined) {
		// 不需要添加前缀
		return style
	} else {
		// 无此css属性
		return false
	}
}
// 例 在Chrome下
console.log(addPrefix('color'))	//return 'color'
console.log(addPrefix('transition'))  //return 'webkitTransition'
console.log(addPrefix('style'))  //return false
{% endhighlight %}