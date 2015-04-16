title: javascript中数组常用方法介绍
date: 2012-10-05 23:31:29
tags: [数组,js]
categories: javascript
description: js中数组的常见用法
toc: true

---
js中数组操作频率非常高，掌握常用方法可以极大提高开发效率

###join()连接
`arr.join();`  讲数组连成字符串,参数：分隔符

例：颠倒一句话：
 `alert("welcom to beijing".split(' ').reverse().join(' '));`
### push(titem);
向数组最后面添加一个元素
### pop();
弹出最后一个元素并返回这个元素 [1,2,3,4].pop()→4，原来的数组变成[1,2,3]

###shift();
弹出第一个元素并返回这个元素 [1,2,3,4].shift()→1，原来的数组变成[2,3,4]
   
###unshift();
在数组最前面添加一个元素[1,2,3].unshift(4),原数组变成[4,1,2,3]

###splice()
- 删除：splice(开始，删除长度);
- 替换：`splice(2,2,'a','b');`
- 添加：`splice(开始位置，0，ele1,...);`
   
###reverse() 颠倒
[1,2,3].reverse(),变成[3,2,1]


###sort(); 排序
   
	sort(function(n1,n2){
	    return n1-n2;
	});


###concat(数组2,数组3....);   连接数组
	var arr=[1,2,3];
	var arr2=[4,5];
	var arr3=[6,7];
	alert(arr2.concat(arr,arr3,[8,9],10,'abc'))