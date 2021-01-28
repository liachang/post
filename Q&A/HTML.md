## Q:HTML5的新增内容
## A:

<details>
1.语义化标签

![](https://s3.ax1x.com/2020/11/23/DYNPpQ.png)

2.多媒体标签

```
<audio>
<video>
<canvas>
```

3.input新属性和表单新元素

```
datalist,keygun,output
```

</details>

## Q：行内元素和块级元素的区别

## A:     

<details>

```
行内元素在一条直线上排列，默认宽度与内容有关，块级元素占据一行，默认宽度为父元素，
块级可以包含行内和块级，行内不能包含块级
盒模型属性上，
行内元素一般来说设置width/height无效,margin\padding上下无效
行内元素img,input,span,块级元素div,form,h1,ol,ul,p
display:inline\block
```

</details>

## Q：替换元素和不可替换元素

## A：

<details>

```
input 和 img 可以设置宽高，因为是替换元素
替换元素 就是浏览器根据元素的标签和属性，来决定元素的具体显示内容。
例如：
<img> 根据 src 属性来读取图片信息并显示出来
<input> 根据标签的 type 属性来决定是显示输入框，还是单选按钮。
替换元素有：<img>、<input>
HTML 大多数元素都是不可替换的，即其内容直接展现给浏览器。
例如：
<p> 直接全部展示
```

</details>

## Q：DOCTYPE 的作用是什么？

## A：

<details>

```
<!DOCTYPE> 声明一般位于文档的第一行，它的作用主要是告诉浏览器以什么样的模式来解析文档。一般指定了之后会以标准模式来进行文档解析，否则就以兼容模式进行解析。
在标准模式下，浏览器的解析规则都是按照最新的标准进行解析的。而在兼容模式下，浏览器会以向后兼容的方式来模拟老式浏览器的行为，以保证一些老的网站的正确访问。 
```

</details>

## Q：SGML 、 HTML 、XML 和 XHTML 的区别？

## A：

<details>

```
SGML 是标准通用标记语言，是一种定义电子文档结构和描述其内容的国际标准语言，是所有电子文档标记语言的起源。
HTML 是超文本标记语言，主要是用于规定怎么显示网页。
XML 是可扩展标记语言是未来网页语言的发展方向，XML 和 HTML 的最大区别就在于 XML 的标签是可以自己创建的，数量无限多， 而 HTML 的标签都是固定的而且数量有限。
XHTML 也是现在基本上所有网页都在用的标记语言，他其实和 HTML 没什么本质的区别，标签都一样，用法也都一样，就是比 HTML 更严格，比如标签必须都用小写，属性值必须加引号，html元素嵌套正确，标签都必须有闭合标签等。
```

</details>

## Q：meta viewport 是做什么的？怎么写?

## A：

<details>

```
移动端浏览器通常都在一个比屏幕更宽的虚拟窗口中渲染页面，这个虚拟窗口就是viewport，目的是正常展示没有做移动端适配的网页，可以让他们完整的展现给用户。我们有时用移动设备访问桌面版网页就会看到一个横向滚动条，这里可显示区域的宽度就是viewport的宽度。

<meta name="viewport" content="width=device-width, initial-scale=1, maximum-scale=1">
该meta标签的作用是让当前viewport的宽度等于设备的宽度，同时不允许用户手动缩放。maximum-scale=1.0, user-scalable=0

meta viewport 的6个属性：
width	设置layout viewport 的宽度，为一个正整数，或字符串”width-device”
initial-scale	设置页面的初始缩放值，为一个数字，可以带小数
minimum-scale	允许用户的最小缩放值，为一个数字，可以带小数
maximum-scale	允许用户的最大缩放值，为一个数字，可以带小数
user-scalable	是否允许用户进行缩放，值为”no”或”yes”, no 代表不允许，yes代表允许
```

</details>

## Q：页面导入样式时，使用 link 和 @import 有什么区别？

## A：

<details>

```
从属关系区别。@import是CSS提供的语法规则，只有导入样式表的作用；link是HTML提供的标签，不仅可以加载CSS文件，还可以定义RSS、rel连接属性、引入网站图标等。
加载顺序区别。加载页面时，link标签引入的CSS文件被同时加载；而@import引入的CSS文件将在页面加载完毕后被加载。
兼容性区别。@import时CSS 2.1才有的语法，故只可在IE5+才能识别；link标签作为HTML标签，不存在兼容性问题。
DOM可控性区别。可以通过JS操作DOM，插入link标签来改变样式；由于DOM方法是基于文档的，无法使用@import的方法插入样式。
```

</details>

## Q：HTML5为什么只需要写 <!DOCTYPE HTML>？

## A：

<details>

```
HTML5不基于SGML（Standard Generalized Markup Language 标准通用标记语言），因此不需要对DTD（DTD 文档类型定义）进行引用，但是需要DOCTYPE来规范浏览器行为。

HTML4.01基于SGML，所以需要引用DTD。才能告知浏览器文档所使用的文档类型
```

</details>

## Q：无样式内容闪烁（FOUC）Flash of Unstyle Content

## A：

<details>

```
@import导入CSS文件会等到文档加载完后再加载CSS样式表。因此，在页面DOM加载完成到CSS导入完成之间会有一段时间页面上的内容是没有样式的。

解决方法：使用link标签加载CSS样式文件。因为link是顺序加载的，这样页面会等到CSS下载完之后再下载HTML文件，这样先布局好，就不会出现FOUC问题。
```

</details>

## Q： 介绍一下你对浏览器内核的理解？

## A：

<details>

```
主要分成两部分：渲染引擎(Layout Engine或Rendering Engine)和JS引擎。

渲染引擎：负责取得网页的内容（HTML、XML、图像等等）、整理讯息（例如加入CSS等），以及计算网页的显示方式，然后会输出至显示器或打印机。浏览器的内核的不同对于网页的语法解释会有不同，所以渲染的效果也不相同。
JS引擎：解析和执行javascript来实现网页的动态效果。
```

```
IE Trident
Safari Chrome Webkit
Opera Blink
```

</details>

## Q： HTML5的新特性

## A：

<details>

```
语义标签、音视频、canvas绘图、
```

增强型表单

```
input属性：
color、date、month、week、email、url
表单元素：
datalist、progress
表单属性：
placeholder、required、autofocus、
```

```
地理定位
geolocation对象
getCurrentPosition()
拖放API drag、drop
Web Worker
```

Web Storage

```
Localstorage
sessionstorage
```

参考：[HTML5新特性汇总](https://blog.csdn.net/weixin_39676449/article/details/85122337)

</details>

## Q：HTMl5移除元素

## A：

<details>

```
纯表现的元素：basefont big center font s strike tt u
性能较差元素：frame frameset noframes
```

</details>

## Q：如何区分html和html5

## A：

<details>

```
通过doctype区分
根据新特性区分
```

</details>

## Q：HTML的语义化

## A：

<details>

```
去掉或丢失样式的时候能够让页面呈现出清晰的结构。
有利于SEO和搜索引擎建立良好沟通，有助于爬虫抓取更多的信息
便于团队开发和维护
```

</details>

## Q：HTML5的文件离线储存怎么使用，工作原理是什么？

## A：

<details>

```
在线情况下，浏览器发现HTML头部有manifest属性，它会请求manifest文件，如果是第一次访问，那么浏览器就会根据manifest文件的内容下载相应的资源，并进行离线存储。如果已经访问过并且资源已经离线存储了，那么浏览器就会使用离线的资源加载页面。然后浏览器会对比新的manifest文件与旧的manifest文件，如果文件没有发生改变，就不会做任何操作，如果文件改变了，那么就会重新下载文件中的资源，并且进行离线存储。
<html manifest='cache.manifest'>
```

</details>

## Q：cookies，sessionStorage和localStorage的区别？

## A：

<details>

```
共同点：都是保存在浏览器端，且是同源的。
区别：
cookies是为了标识用户身份而存储在用户本地终端上的数据，始终在同源http请求中携带，即cookies在浏览器和服务器间来回传递，而sessionstorage和localstorage不会自动把数据发给服务器，仅在本地保存。
存储大小的限制不同。cookie保存的数据很小，不能超过4k，而sessionstorage和localstorage保存的数据大，可达到5M。
数据的有效期不同。cookie在设置的cookie过期时间之前一直有效，即使窗口或者浏览器关闭。sessionstorage仅在浏览器窗口关闭之前有效。localstorage始终有效，窗口和浏览器关闭也一直保存，用作长久数据保存。
作用域不同。cookie在所有的同源窗口都是共享；sessionstorage不在不同的浏览器共享，即使同一页面；localstorage在所有同源窗口都是共享
```

</details>

## Q：iframe

## A：

<details>

```
好处：
iframe 元素会创建包含另外一个文档的内联框架（即行内框架）。
如果有多个网页引用iframe，那么你只需要修改iframe的内容，就可以实现调用的每一个页面内容的更改，方便快捷。
网页如果为了统一风格，头部和版本都是一样的，就可以写成一个页面，用iframe来嵌套，可以增加代码的可重用。
如果遇到加载缓慢的第三方内容如图标和广告，这些问题可以由iframe来解决。
缺点：
搜索引擎的爬虫程序无法解读这种页面
框架结构中出现各种滚动条
iframe页面会增加服务器的http请求
```

</details>

## Q：Label

## A：

<details>

```
label标签用来定义表单控件间的关系,当用户选择该标签时，浏览器会自动将焦点转到和标签相关的表单控件上。label 中有两个属性是非常有用的, FOR和ACCESSKEY。
```

</details>

## Q：table

## A：

<details>

```
tr,th,td,thead,tbody,
不用table、iframe的原因：
因为浏览器页面渲染的时候是从上至下的，而table 和 iframe 这两种元素会改变这样渲染规则，他们是要等待自己元素内的内容加载完才整体渲染。用户体验会很不友好。
```

</details>

## Q：html对SEO的优化

## A：

<details>


```
meta标签: title\description\keywords
logo ：h1标签、a链接连接到首页以及alt
h1-h6标签：浏览器会自动地在标题的前后添加空行。请确保将HTML heading标签只用于标题。不要仅仅是为了产生粗体或大号文本而使用标题，因为搜索引擎使用标题为你的网页的结构和内容标志索引。
添加robots.txt，搭建网站与搜索引擎对话的桥梁
页面结构清晰
```

</details>

## Q：WebSocket

## A：

```
WebSocket 是 HTML5 开始提供的一种在单个 TCP 连接上进行全双工通讯的协议。
```

## Q：Web标准

## A：

```
结构层、表现层、行为层
```

## Q：补充标签

## A：

```
<hr> 水平线
<base target='_blank'/> 设置整体链接的打开状态
<tabel>表格
<th><tr><td><caption><rowspan><colspan>
<thead><tfoot><tbody>
表单
<input type\value\name\checked>
<label><textarea><select>
表单域
<form action method name>
xxx
</form>
```

## Q：浏览器

## A：

```
浏览器分为渲染引擎和js引擎
渲染引擎用于解析html,css，俗称内核，如blink,webkit
js引擎用于解析js，如v8
```



