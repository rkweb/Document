# 前端公用文档 #
common.min.js 封装了前端项目常用方法，此文档仅适用于**移动端**页面。

## 文档介绍 ##
common.min.js 封装的功能包括：

1. loading方法；
2. 分享代码；
3. 常用UA检测；
3. 监测代码（不需要自己区分汽车或非汽车项目）；
4. 手机横屏时，提示用户请竖屏浏览;
5. 移动端页面在PC打开时，只显示专题二维码，用户需手机扫码查看； 
7. 获取链接中指定的参数。

## 文档使用说明 ##
对外提供了**netease**对象，下面有几个可以使用的公用方法

**首先引用common.min.js，引入到`<body></body>`标签内，作为第一个引入的js文件，如下**

	<!DOCTYPE html>
    <html>
    	<head>
    	...
    	</head>
    	<body>
    	...
    	<script src="http://test.go.163.com/go/2015/public/common/js/common.min.js"></script>
    	</body>
    </html>

----------

### loading 接口使用说明 ###

1. loading 依赖html代码如下(将此段复制到body中)
	
		<!--loading-->
		<div class="netease-loader">
	    	<section>
	        	<article>
	            	<span class="load_type"></span>
	            	<span class="load_data"></span>
	            	<span class="load_text"></span>
	        	</article>
	    	</section>
		</div>
	
2. 加载css文件和js文件：loading.css和common.min.js

    	<!DOCTYPE html>
    	<html>
    		<head>
    		...
    		<link rel="stylesheet" href="http://go.163.com/2015/public/common/loading/loading.css">
    		</head>
    		<body>
    		...
			<script src="http://test.go.163.com/go/2015/public/common/js/common.min.js"></script>
    		<script src="http://img2.126.net/ntesrich/ad/zepto.min.js"></script> <!--引用zepto或jquery-->
    		</body>
    	</html>

3. 添加如下代码

    	<script>
			var imgArr=[
        		//将需要loading的图片放到此数组
    		];
			//callback:loading结束后的回调函数
    		netease.loading(imgArr,callback);
    	</script>


----------

### 分享 接口使用说明 ###
添加如下代码

	<script>
        var shareData={
            MsgImg:'',  //分享图片
            link:'',    //分享链接
            title:'',   //分享标题
            desc:'',    //分享描述
            fText:'',    //分享朋友圈
            callback:function(){
                share_survey(true);
            }
        };
        NeteaseShareInit();
      	document.getElementById("shareBtn").onclick = function() {
            NeteaseShare(function(){
            	// 微信分享提示
            },false);
        }
    </script>


----------


### UA检测 使用说明 ###
添加如下所需代码

	<script>
    	netease.ua.mobile //是否为移动终端
    	netease.ua.pc //是否为pc终端
    	netease.ua.ios //是否为ios终端
    	netease.ua.android  //是否为android终端
    	netease.ua.weixin  //是否为微信客户端
    	netease.ua.newsapp  //是否为网易新闻客户端
    	netease.ua.yixin  //是否为易信客户端
    	netease.ua.weibo //是否为微博客户端
    	netease.ua.yunyuedu //云阅读客户端
	</script>

----------

### 监测代码 使用说明 ###
引用common.min.js即可，无需添加其他代码，**不区分汽车和常规专题**

----------

### 手机横屏时，提示用户请竖屏浏览 ###
此功能为默认功能，如需更改，添加如下代码

    //如需屏蔽掉手机横屏 自己页面声明变量
    //window.landscape_tip = false;

----------

### 移动端页面在PC打开，只显示专题二维码 ###
此功能为默认功能，如需更改，添加如下代码

    //如需屏蔽掉pc二维码, 自己在页面加如下代码
    if(document.getElementById("pc_code")){document.getElementById("pc_code").style.display = 'none';}

----------

### 获取链接参数 使用说明 ###
添加如下代码

    <script>
    	netease.getPara("传入参数name");
    </script>