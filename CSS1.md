### css
+ css:层叠样式表，英文名：Casecading Style Sheets
+ html+css：页面的内容
    + html：页面的结构
    + css：页面的样式
+ JavaScript：页面的行为

### 标签的属性
> 示例：削苹果
```
<削 颜色="红" 大小="大" 种类="红富士" 形状="好">苹果</削>
```
+ 随着html条件越来越多，对应的属性也越来越多，这样就会引发出一些问题
    + 浏览器越来越麻烦
    + 对开发人员：代码越来越多，看起来很复杂，很难维护

### css标准
> 示例：削苹果
```
<削 颜色="红" 大小="大" 种类="红富士" 形状="好">苹果</削>
``` 
> 可表示为：
```
 <!--归类到style样式属性里-->
<削 style=" 
    颜色：红
    大小：大
    种类：红富士
    形状：好"> 苹果 </削>
```
+ 属性都归类到style样式属性里就解决了浏览器越来越麻烦的问题
    + 只需要改动css属性里的内容，html就可以不用动
    + 或者只需要改动html属性的内容，css也不用动，两种属性做到了分离状态
+ 也可以通过选择器的形式：让样式属性和标签产生某种联系，也可以达到简化代码的效果
> 可表示为：
```
 削 {
     颜色：红
     大小：大
     种类：红富士
     形状：好
 }
 <削>苹果</削>
```
+ 建立一个选择器就解决了代码复杂，很难维护的问题
+ 为了增强代码的可复用性；又形成了一种新的形式:
    + 通过建立两个文档；html文档内只放标签；css文档内只放样式
> 具体表现形式为：
```
 <html lang="zh">
<head>
    <meta charset="UTF-8">
    <title>示例</title>
</head>
<body>
    <div style="color:red;width:100px;height:100px;background:yellow;">苹果1</div>
    <div style="color:red;width:100px;height:100px;background:yellow;">苹果2</div>
    <div style="color:red;width:100px;height:100px;background:yellow;">苹果3</div>
    <div style="color:red;width:100px;height:100px;background:yellow;">苹果4</div>
</body>
</html>
```
> 可用标签选择器简化为：
```
<html lang="zh">
<head>
    <meta charset="UTF-8">
    <title>示例</title>
    <style>
        div{color:red;
        width:100px;
        height:100px;
        background:yellow;
        }
    </style>
</head>
<body>
    <div>苹果1</div>
    <div>苹果2</div>
    <div>苹果3</div>
    <div>苹果4</div>
</body>
</html>
```
> 可用css和html两个文档表示为：
````
<html lang="zh">
<head>
    <meta charset="UTF-8">
    <title>示例</title>
    <link rel="stylesheet" href="1.css">
</head>
<body>
    <div>苹果1</div>
    <div>苹果2</div>
    <div>苹果3</div>
    <div>苹果4</div>
</body>
</html>
```
> 1.css文件里的内容为：
```
div{color:red;
        width:100px;
        height:100px;
        background:yellow;
}
```
