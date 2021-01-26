## margin塌陷和margin合并



### margin塌陷：

```
父子嵌套元素在垂直方向的margin,父子元素是结合在一起的,他们两个的margin会取其中最大的值.
正常情况下,父级元素应该相对浏览器进行定位,子级相对父级定位.
但由于margin的塌陷,父级相对浏览器定位.而子级没有相对父级定位,子级相对父级,就像坍塌了一样.
```

```
解决办法:
1.为父盒子设置border，为外层添加border后父子盒子就不是真正意义上的贴合。
2.bfc
```



### margin合并：

```
两个兄弟结构的元素在垂直方向上的margin是合并的

标准文档流中，两个盒子，分别有上下外边距，竖直方向的margin不叠加，只取较大的值作为margin。
```



## 清除浮动





## BFC

#### 概念

```
Formatting context(格式化上下文) 
它是页面中的一块渲染区域，并且有一套渲染规则，它决定了其子元素将如何定位，以及和其他元素的关系和相互作用。
```

```
BFC 即 Block Formatting Contexts (块级格式化上下文)
具有 BFC 特性的元素可以看作是隔离了的独立容器，容器里面的元素不会在布局上影响到外面的元素。
```

```
首先这不是 CSS 的 bug，我们可以理解为一种规范，如果想要避免外边距的重叠，可以将其放在不同的 BFC 容器中。
```

#### 条件

```
触发bfc
方法:
body 根元素
浮动元素：float 除 none 以外的值
绝对定位元素：position (absolute、fixed)
display 为 inline-block、table-cells、flex
overflow 除了 visible 以外的值 (hidden、auto、scroll)
```



#### 应用

```
防止margin折叠
```

```
BFC 可以包含浮动的元素（清除浮动）
```

```
阻止未浮动元素被浮动元素覆盖
```

