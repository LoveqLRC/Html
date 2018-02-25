# 清除浮动的影响

	<!DOCTYPE html>
	<html lang="en">
	<head>
	    <meta charset="UTF-8">
	    <title>Title</title>
	    <style type="text/css">
	        * {
	            margin: 0;
	            padding: 0;
	        }
	
	        /*每个li都左浮动*/
	        li {
	            float: left;
	            width: 90px;
	            height: 40px;
	            background-color: gold;
	            text-align: center;
	        }
	    </style>
	</head>
	<body>
	<div class="html">
	    <ul>
	        <li>Html</li>
	        <li>CSS</li>
	        <li>JS</li>
	        <li>Html5</li>
	    </ul>
	</div>
	
	<div class="android">
	    <ul>
	        <li>Retrofit</li>
	        <li>Okhttp</li>
	        <li>RxJava</li>
	        <li>Gson</li>
	    </ul>
	</div>
	
	</body>
	</html>


预期的结果是:
![](https://raw.githubusercontent.com/LoveqLRC/Html/master/com.loveqrc/css%E5%9F%BA%E7%A1%80/%E6%B5%AE%E5%8A%A8/img/%E9%A2%84%E6%9C%9F%E7%9A%84%E6%A0%B7%E5%AD%90.png)

实际的结果是:
![](https://raw.githubusercontent.com/LoveqLRC/Html/master/com.loveqrc/css%E5%9F%BA%E7%A1%80/%E6%B5%AE%E5%8A%A8/img/%E6%B5%AE%E5%8A%A8%E7%9A%84%E5%BD%B1%E5%93%8D.png)


## 给浮动元素的祖先加高度
只有有高度的盒子，才能关注浮动。只要浮动在一个有高度的盒子中，那么这个浮动就不会影响后面的浮动元素。

	 div.html {
            height: 50px;
            border: 1px solid #000;
        }


## clear:both
clear：的意思是清除，both：指的是左右浮动都要清除。所以clear:both指的是清除其他元素对我的影响。

        div.android {
            clear: both;
            /*margin失效*/
            margin-top: 10px;
        }

但是clear:both 有一个缺陷，就是margin失效。

## 增加一堵墙

### 隔墙法

	<div>
	    <ul>
	        <li>Html</li>
	        <li>CSS</li>
	        <li>JS</li>
	        <li>Html5</li>
	    </ul>
	</div>
	<!--隔墙-->
	<div class="cl h10"></div>
	<div>
	    <ul>
	        <li>Retrofit</li>
	        <li>Okhttp</li>
	        <li>RxJava</li>
	        <li>Gson</li>
	    </ul>
	</div>



        .cl {
            clear: both;
        }

        .h10 {
            height: 10px;
        }


### 内墙法

	<div>
	    <ul>
	        <li>Html</li>
	        <li>CSS</li>
	        <li>JS</li>
	        <li>Html5</li>
	    </ul>
	    <div class="cl h10"></div>
	</div>
	
	
	<div>
	    <ul>
	        <li>Retrofit</li>
	        <li>Okhttp</li>
	        <li>RxJava</li>
	        <li>Gson</li>
	    </ul>
	</div>

内墙法的本质是给没有高度的父亲撑出高度。

## overflow:hidden
overflow:hidden的原意是清除溢出到盒子外面的文字。但在浮动中，一个父亲不能被自己浮动的儿子，撑出高度。但是，只要给父亲加上overflow:hidden; 那么，父亲就能被儿子撑出高了。

	  .html {
	            overflow: hidden;
	            margin-bottom: 10px;
	            _zoom: 1; /*IE6 兼容*/
	
	        }




