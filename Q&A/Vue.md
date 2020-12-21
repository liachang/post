[TOC]

## Q：v-if 和v-show

## A:

```
v-if与v-show都可以动态控制dom元素显示隐藏
v-if显示隐藏是将dom元素整个添加或删除，而v-show隐藏则是为该元素添加css--display:none，dom元素还在。
v-if是动态的向DOM树内添加或者删除DOM元素，v-show是通过设置DOM元素的display样式属性控制显隐
编译条件：v-if是惰性的，如果初始条件为假，则什么也不做；只有在条件第一次变为真时才开始局部编译（编译被缓存？编译被缓存后，然后再切换的时候进行局部卸载); v-show是在任何条件下（首次条件是否为真）都被编译，然后被缓存，而且DOM元素保留
性能消耗：v-if有更高的切换消耗；v-show有更高的初始渲染消耗
使用场景：v-if适合运营条件不大可能改变；v-show适合频繁切换
```

## Q：MVC和MVVM

## A:

```
model-view-controller
Model（模型）：数据保存
View（视图）：数据显示、用户界面。
Controller（控制器）：业务逻辑
```

MVC：

![](http://www.ruanyifeng.com/blogimg/asset/2015/bg2015020105.png)

```
View 传送指令到 Controller
Controller 完成业务逻辑后，要求 Model 改变状态
Model 将新的数据发送到 View，用户得到反馈
所有通信都是单向的。
```

MVVM

![](http://www.ruanyifeng.com/blogimg/asset/2015/bg2015020110.png)

```
各部分之间的通信，都是双向的。
View 与 Model 不发生联系，都通过 Presenter 传递。
View 非常薄，不部署任何业务逻辑，称为"被动视图"（Passive View），即没有任何主动性，而 Presenter非常厚，所有逻辑都部署在那里。
```

## Q：简述Vue的响应式原理（数据双向绑定原理）

## A:

```
在MVVM中，M(model)---代表JavaScript  Objects，V(view)---DOM也就是UI，VM(ViewModel)----代表Vue实例对象（在该对象中有Directives和DOM Listeners）

在vue.js里面只需要改变数据，Vue.js通过Directives指令去对DOM做封装，当数据发生变化，会通知指令去修改对应的DOM，数据驱动DOM的变化，DOM是数据的一种自然的映射。vue.js还会对View操作做一些监听（DOM Listener），当我们修改视图的时候，vue.js监听到这些变化，从而改变数据。这样就形成了数据的双向绑定。

如new Vue一个实例对象a，其中有一个属性a.b，那么在实例化的过程中，通过Object.defineProperty()会对a.b添加getter和setter，同时Vue.js会对模板做编译，解析生成一个指令对象（这里是v-text指令），每个指令对象都会关联一个Watcher,当对a.b求值的时候，就会触发它的getter，当修改a.b的值的时候，就会触发它的setter，同时会通知被关联的Watcher，然后Watcher就会再次对a.b求值，计算对比新旧值，当值改变了，Watcher就会通知到指令，调用指令的update()方法，由于指令是对DOM的封装，所以就会调用DOM的原生方法去更新视图，这样就完成了数据改变到视图更新的一个自动过程

实现数据双向绑定的方法：

数据劫持结合发布者-订阅者模式（vue.js）
vue.js采用数据劫持结合发布者-订阅者的方式，通过Object.defineProperty()来劫持各个属性的setter，getter，在数据变动时，发布消息给订阅者，触发相应的监听回调。


具体步骤如下：
     1. 当你把一个普通的 JavaScript 对象传入 Vue 实例作为 data 选项，监听器 Observer：将遍历此对象所有的 property，并使用 Object.defineProperty 把这些 property 全部转为 getter/setter。这些 getter/setter 对用户来说是不可见的，但是在内部它们让 Vue 能够追踪依赖，在 property 被访问和修改时通知变更。（数据劫持）
     
     2. 解析器 Compile：解析 Vue 模板指令，将模板中的变量都替换成数据，然后初始化渲染页面视图，并将每个指令对应的节点绑定更新函数，添加监听数据的订阅者，一旦数据有变动，收到通知，调用更新函数进行数据更新。
     3. 接着，Watcher订阅者是Observer和Compile之间通信的桥梁，主要负责：
         1）在自身实例化时，往属性订阅器（Dep）里面添加自己
         2）自身必须有一个update()方法
         3）待属性变动，dep.notice()通知时，就调用自身的update()方法，并触发Compile中绑定的回调
         订阅者 Watcher：Watcher 订阅者是 Observer 和 Compile 之间通信的桥梁 ，主要的任务是订阅 Observer 中的属性值变化的消息，当收到属性值变化的消息时，触发解析器 Compile 中对应的更新函数。
	订阅器 Dep：用来收集订阅者 Watcher，当劫持到数据变更的时候，通知订阅者watcher进行update.
     4. 最后，viewmodel(vue实例对象)作为数据绑定的入口，整合Observer、Compile、Watcher三者，通过Observer来监听自己的model数据变化，通过Compile来解析编译模板指令，最终利用Watcher搭起Observer和Compile之间的通信桥梁，达到数据变化 (ViewModel)-》视图更新(view)；视图变化(view)-》数据(ViewModel)变更的双向绑定效果。
```

## Q：Vue3.x响应式数据原理

## A:

```
用Proxy替代Object.defineProperty
```

优劣：

```
Proxy可以监听对象而非属性
Proxy可以监听数组的变化，有多种拦截方法。
Proxy返回新对象，可以只操作新对象，而Object。defineProperty只能遍历对象属性直接修改。
O.dP好处：兼容性。
```

## Q：Vue的生命周期

## A:

```
Vue 实例从开始创建、初始化数据、编译模板、挂载Dom和渲染、更新和渲染、卸载等一系列过程，这是 Vue 的生命周期
```

```
vue的生命周期里边有八个生命周期钩子函数分别是
beforeCreat() 创建前
created（）创建
beforeMount()挂载前
mounted（）挂载
beforeupdate（）更改前
updated（）更改
beforeDestroy()销毁前
destroyed（）销毁
```

