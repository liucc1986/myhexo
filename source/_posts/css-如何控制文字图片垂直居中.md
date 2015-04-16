title: "css 如何控制文字图片垂直居中"
date: 2012-09-14 22:14:26
tags: [css,垂直居中]
categories: 随笔
description: 文字图片垂直居中
toc: true

---
##文字图片垂直居中问题

###固定高度容器中，单行文字垂直居中

设置行高

	.box{
		height:50px;
		line-height:50px
	}
###固定容器高度，或者未知容器高度，多行文字垂直居中

    .box{
    		display: table-cell;
    		width: 400px;
    		height: 400px;
    		vertical-align: middle;
    		background:red;
    		text-align: center;
    	}

###兼容IE怎么办？
不管

##附本例测试代码
	
	<!DOCTYPE html>
	<html>
	<head>
	<meta charset="utf-8">
	<meta name="author" content="liucc" />
	<title>文字垂直居中</title>
	<meta name="description" content="">
	<meta name="keywords" content="">
	
	<style>
		.box{
			display: table-cell;
			width: 400px;
			height: 400px;
			vertical-align: middle;
			background:red;
			text-align: center;
		}
		
		
	</style>
	<script>
	window.onload=function(){
	
	}
	</script>
	</head>
	<body>
		<div class="box">
			<img src="https://www.baidu.com/img/bd_logo1.png" alt="">
			<!-- <p>图片也如此<br>
	
	收房<br>
	f
			</p> -->
		</div>
	
	</body>
	</html>