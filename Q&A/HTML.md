## Q:HTML5的新增内容
## A:

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



## Q：行内元素和块级元素的区别

## A:     

```
行内元素在一条直线上排列，默认宽度与内容有关，块级元素占据一行，默认宽度为父元素，
块级可以包含行内和块级，行内不能包含块级
盒模型属性上，
行内元素一般来说设置width/height无效,margin\padding上下无效
行内元素img,input,span,块级元素div,form,h1,ol,ul,p
display:inline\block
```



## Q：替换元素和不可替换元素

## A：

```
input 和 img 可以设置宽高，因为是替换元素
替换元素 就是浏览器根据元素的标签和属性，来决定元素的具体显示内容。
例如：
<img> 根据 src 属性来读取图片信息并显示出来
<input> 根据标签的 type 属性来决定是显示输入框，还是单选按钮。
替换元素有：<img>、<input>、<textarea>、<select>、<object>。
HTML 大多数元素都是不可替换的，即其内容直接展现给浏览器。
例如：
<p> 直接全部展示
```

## Q：DOCTYPE 的作用是什么？

## A：

```
<!DOCTYPE> 声明一般位于文档的第一行，它的作用主要是告诉浏览器以什么样的模式来解析文档。一般指定了之后会以标准模式来进行文档解析，否则就以兼容模式进行解析。
在标准模式下，浏览器的解析规则都是按照最新的标准进行解析的。而在兼容模式下，浏览器会以向后兼容的方式来模拟老式浏览器的行为，以保证一些老的网站的正确访问。 
```

## Q：SGML 、 HTML 、XML 和 XHTML 的区别？

## A：

```
SGML 是标准通用标记语言，是一种定义电子文档结构和描述其内容的国际标准语言，是所有电子文档标记语言的起源。
HTML 是超文本标记语言，主要是用于规定怎么显示网页。
XML 是可扩展标记语言是未来网页语言的发展方向，XML 和 HTML 的最大区别就在于 XML 的标签是可以自己创建的，数量无限多， 而 HTML 的标签都是固定的而且数量有限。
XHTML 也是现在基本上所有网页都在用的标记语言，他其实和 HTML 没什么本质的区别，标签都一样，用法也都一样，就是比 HTML 更严格，比如标签必须都用小写，标签都必须有闭合标签等。
```

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

## Q：

## A：