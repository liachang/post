字符串

```
str.toUpperCase()
str.toLowerCase()
```

```
str.charAt(0) 返回对应坐标的字符
str.slice(start,end) 返回选定元素的数组，end可选，不改变原数组
```

```
parseInt(str,radix)
radix为要解析的数字的基数
将字符串解析为数字
```



```
str.split(separator,howmany) 
将字符串转为数组，相当于Array.join()的反操作
separator: 从参数指定的地方分割  如“ ”， hi lihua -> hi,lihua
若为"",则将每个字符都进行分割
howmanny: 返回数组的最大长度
```

数组

```
Array.reverse()
array.length
```

```
const map1 = Array.map((item)=>{})
返回一个由 数组中每个元素都调用一个给定函数后的结果 组成的数组
```

```
array.from(str)
从一个有length属性或可迭代的对象返回一个数组
```

展开语法(...)

```
可以在函数调用/数组构造时, 将数组表达式或者string在语法层面展开；还可以在构造字面量对象时, 将对象表达式按key-value的方式展开。
```

