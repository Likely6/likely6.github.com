---
title: 获取指定范围随机数与洗牌函数
date: 2018-02-19
categories: JS
tags: JS random
---

{% highlight r %}
/**
 * @parama {Number}
 * @paramb {Number}
 * @return {Number} 返回值(Integer)	>=min && <=max
 */
// 随机函数
let getRandom = (min = 0, max = 10) => {
	if (min > max) {
		let box = min
		min = max
		max = box
	}
	return Math.floor(Math.random() * (max - min + 1) + min)
}
// 洗牌函数一
let shuffle = (arr = []) => {
	return arr.sort(() => {
		// 通过sort的return值来实现数组打乱
		return Math.random() - 0.5
	})
}
// 洗牌函数二
let shuffle = (arr = []) => {
	for (let i in arr) {
		// 通过每循环一次就与第i个元素及前面的随机元素调换位置来实现数组打乱
		// 这里需要用到前面的随机函数
		let random = getRandom(0, i)
		let box = arr[i]
		arr[i] = arr[random]
		arr[random] = box
	}
	return arr
}
{% endhighlight %}