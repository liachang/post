## why

	当用户一次点击屏幕之后，浏览器并不能立刻判断用户是要进行双击缩放，还是想要进行单击操作。因此，iOS Safari 就等待 300 毫秒，以判断用户是否再次点击了屏幕。 于是，300 毫秒延迟就这么诞生了。

## how

	安装fastclick库 解决点击响应延时 0.3s 问题
	npm Install fastclick --save
	
	在main.js中引入，并绑定到body
	import FastClick from 'fastclick'
	FastClick.attach(document.body);