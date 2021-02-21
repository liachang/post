#### 路由思路

通过hash值的改变，展示不同的组件

监听 window 的 onhashchange 事件，location.hash.slice(1)获取到的最新的 hash 值

#### Vue Router的特性：

支持嵌套路由
支持路由参数
支持编程式路由
支持命名路由

*支持路由导航守卫*
*支持路由过渡动画特效*
*支持路由懒加载*
*支持路由滚动行为*



#### 使用：

```
<router-link to="/xx"></router-link>
<router-view></router-view>  占位，路由对应组件的展示位置
const router= new VueRouter({ 创建路由实例对象
	routes:[
	{path:'' ,component:}
	{path:'' ,component:}
	]
})
const vm = new Vue({
el:'#app'
data:{}
route:router
})



重定向
path:'/',redirect:'/xxx'
```

#### 子级路由

```
children数组
routes;[
{path:'/aa',component: xxx, children'[
{path:'/aa/bb',component:xxx}
]}
]
```

#### 动态路由匹配（路由传参）

方式一：

```
<router-link to="/xx/1"></router-link>
```



```
传：
routes:[
{path:'/xx/:id',component:}
]
接
{{$route.params.id}}
```

方式二：

```
props:['xx']
{{xx}}
```

方式三：对象

```
props:['id','uname','age]
```

方式四：写成函数

```
routes:[
{path:/xx/:id,component:xx,props: route=>({xxx:xxx})}
]
```

#### 命名路由

```
<router-link to="{name:xxx, params:{}}">
routes:[
{name:xxx
path:xxx}
]
```

#### 编程路由

```
通过事件改变hash
this.$router.push()
this.$router.go()
```

