JSON: **J**ava**S**cript **O**bject **N**otation(JavaScript 对象表示法)

### Json和XML的比较

```
JSON 与 XML 的相同之处：
易于理解。
有层次的结构
可以被大多数编程语言使用

JSON 与 XML 的不同之处：
JSON 不需要结束标签
JSON 更加简短
JSON 读写速度更快
JSON 可以使用数组

最大的不同是：

针对 AJAX 应用，JSON 比 XML 数据加载更快，而且更简单：
XML 比 JSON 更难解析。
使用 XML
需要使用 XML 解析器来解析
获取 XML 文档
使用 XML DOM 迭代循环文档
接数据解析出来复制给变量

使用 JSON
获取 JSON 字符串
JSON.Parse 解析 JSON 字符串
JSON 可以使用标准的 JavaScript 函数来解析。
JSON.parse(): 将一个 JSON 字符串转换为 JavaScript 对象。
JSON.stringify(): 于将 JavaScript 值转换为 JSON 字符串。

```

### jsonp

Jsonp(JSON with Padding) 是 json 的一种"使用模式"，可以让网页从别的域名（网站）那获取资料，即跨域读取数据。