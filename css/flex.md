

```
flex 是 flexible Box 的缩写，意为"弹性布局"，用来为盒状模型提供最大的灵活性，任何一个容器都可以指定为 flex 布局。
当我们为父盒子设为 flex 布局以后，子元素的 float、clear 和 vertical-align 属性将失效。
flex container  flex item
```

```
display: flex
```

```
容器的属性：
flex-direction: row/column/row-reverse  项目排列的方向，设定主轴和副轴，默认从左到右
justify-content: flex-start\space-around(平分空间)\space-between(两边贴边再平分)    设置主轴上子元素的排列方式
flex-wrap: wrap/nowrap  决定换行
align-items：flex-start flex-end center  定义在侧轴上的对齐方式，用于当行
align-content: 用于多行

项目的属性：
flex:1  让所有弹性盒模型对象的子元素都有相同的长度，且忽略它们内部的内容
align-self：定义自己相对于侧轴的排列方式
order: int 项目排列顺序
```

