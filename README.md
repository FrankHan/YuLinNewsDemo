﻿MUI尝过的坑

1：自带的各种标签的 样式权重过高，重写不方便（和BootStrap比较来说，BootStrap更加灵活）<br>
2：链接跳转。常规的a标签 加href是无法跳转的，浏览器有效，但是在手机上运行是无效的
   需要添加mui的定义的点击事件。分两种
(1)：页面已存在的跳转标签
```javascript
   <script>
			document.getElementById('user-guide').addEventListener('tap', function() {
				//打开关于页面
				var newsid=$(this).find(".news-id").html();
				mui.openWindow({
					url: 'use-guide.html',
					id: 'use-guide'
				});
			});
		</script>
```
(2):页面不存在的跳转标签（还可以在链接跳转过程中 添加传递的参数）
```javascript
<script>
			mui("body").on('tap',"#detail-news", function() {
				//打开关于页面
				var newsid=$(this).find(".news-id").html();
				console.log("newsid");
				mui.openWindow({
					url: 'detail-news.html?'+newsid,
					id: 'detail-news'
				});
			});
		</script>
```


接受页面的处理：
```javascript
var newsid = window.location.href.split('?')[1];
```

3：页面过长，滑动没有效果
关键类：mui-scroll-wrapper
添加一个js就可以实现 页面滑动
```javascript
mui('.mui-scroll-wrapper').scroll({
	deceleration: 0.0005 //flick 减速系数，系数越大，滚动速度越慢，滚动距离越小，默认值0.0006
});
```
4：第三方  分享实现

在HBuilder中新创建新webapp项目 勾选 带登陆和设置的模板

里面包含 
第三方登陆<br>
分享<br>
图案锁屏<br>
5：关于模态框
模态框尽量放在根节点的子目录下（不要放在嵌套层），防止最外层的遮罩层的级别过高，覆盖模态框，导致点击事件无法触发响应<br>
扫码下载<br>
![ͼʾ 1](https://i.niupic.com/images/2016/12/13/BrQjud.png)<br>
[APP下载地址](http://fir.im/nbx8)  <br>
![ͼʾ 1](https://i.niupic.com/images/2016/12/12/Z4pu9p.jpg)
![ͼʾ 2](https://i.niupic.com/images/2016/12/12/Flttxd.jpg)
![ͼʾ 3](https://i.niupic.com/images/2016/12/12/L8krcb.jpg)
![ͼʾ 4](https://i.niupic.com/images/2016/12/12/abuwXk.jpg)
![ͼʾ 5](https://i.niupic.com/images/2016/12/12/gn9gXG.jpg)
