Ajax 相当于浏览器发送请求与接收响应的代理人，以实现在不影响用户浏览页面的情况下，局部更新页面数据，从而提高用户体验。

#### 实现步骤

```
var xml = new XMLHTTPRequest()	创建对象
xml.open('get','url')   请求方式和地址
xml.send(params)			发送请求
xml.onload = function(){
console.log(xml.responseText)
}
```

#### 数据处理

``` 
JSON.parse()  字符串=》对象
```

#### 请求参数

```
get: 写进xml.open的url里
post: xml.setRequestHeader('Content-Type', 'application/x-www-form-urlencoded');
json格式的参数
xhr.setRequestHeader('Content-Type', 'application/json');
xhr.send(JSON.stringify({name: 'lisi', age:50}));
```

#### 状态码

```
xml.readyState
xml.onreadystatechange
0：请求未初始化(还没有调用open())
1：请求已经建立，但是还没有发送(还没有调用send())
2：请求已经发送
3：请求正在处理中，通常响应中已经有部分数据可以用了
4：响应已经完成，可以获取并使用服务器的响应了
```

#### 缓存问题

提供不同参数进行请求

#### 函数封装

```
ajax({
type:
url：
data:
success:
error:
})
```

