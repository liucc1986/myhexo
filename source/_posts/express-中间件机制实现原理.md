title: "express 中间件机制实现原理"
date: 2014-04-14 14:28:41
tags: [中间件,express]
categories: nodejs
description: connect 核心原理.
toc: true


---

### 功能：

    app.use(fn1);
	app.use（fn2);
	app.use（fn2);
	app.use（...);
	...
###其中原理：

非常简单，就是讲功能函数fn1.。。按照use的顺序依次加入一个数组，app.run()的时候这个数组里的函数依次执行。
代码如下:
    

	function MiddleWare(){
	    this._stack=[];//stack命名参考：栈（stack）在计算机科学中是限定仅在表尾进行插入或删除操作的线性表
	
	}
	MiddleWare.prototype.use=function(callback){
	     this._stack.push(callback);
	
	}
	MiddleWare.prototype.run(fnEnd){
	    var index=0;
	    var _this=this;
	    function next(){
	        if(index<_this._stack.length){
	            _this._stack[index++](next)//注意index是先赋值后+1
	            //index++ //不可以这样写因为这里是同步的 走不到这里
	        }else{
	            fnEnd();
	        }
	    }
	
	}

###中间件测试：

	var app=new MiddleWare();
	app.use(function(next){
	    console.log('test1');
	next();//如果next不调用则不会继续往下传递
	});
	ware.use(function(next){
	    console.log('test2');
	next();
	})
	app.run(function(){
	    console.log('over');
	});