### CSS属性
+ 颜色：RGB色彩模式
    + R：红色，red
    + G：绿色，green
    + B：蓝色，blue
    + 颜色由浅至深：0~255个色号
+ css属性里表示为：
    + color:rgb(255,0,0)  表示红色
    + clolr:rgb(100%,0%,0%) 也可以用%来表示
+ 色彩的表达模式可以为三种：
    + rgb(255,0,0)
    + 名称：red,green,blue
    + 十六进制表示法：#ff0000 = #f00表示 (255,0,0)
        + 十六进进制：1~9 A B C D E F

### CSS选择器
+ 选择器：在大括号之前的属性就是选择器
+ 选择器的作用：通过选择器可以找到对应的html文件的元素，并且把选择器后面的样式传递给元素
+ 选择器可以分为4类
    + 基本选择器
    + 组合选择器
    + 属性选择器
    + 伪元素选择器
+ 基本选择器包含4种选择模式：
+ *通配符选择器：针对所有的标签都可以把 *号后面的样式传递给html文件内的元素
```
* {
    color:rgb(0,0,255);
}
```
+ 标签选择器 ：针对对应的标签可以把括号后面的样式传递给html文件内相对应的元素
```
div {
    color:rgb(0,0,255);
}
```
+ id选择器：针对某一个标签可以设置名称，表示方式为< a id="id" >再把括号后面的样式属性传递给对应的html文件内的元素，选择器和标签属性之间用空格隔开，书写的时候要以#+id名称的形式书写
```
#id{
    color:rgb(0,0,255);
}
```
+ class选择器：针对某一个标签可以设置名称，表示方式为< a class="mingcheng" >再把括号后面的样式属性传递给相对应的html文件内的元素
class选择器不具有唯一性：可以同时设置几个名称，表示方式为< a class="mingcheng1 mingcheng2 mingcheng3 >表示，名称之间用空格隔开，书写时以 .+id名称的形式书写
```
.class {
        color:rgb(0,0,255);
}
```

### 编程思想
+ 跟ID相关的属性就具有唯一性，相当于人的身份证号码
    + 唯一性的意义
        + 有且仅有一个id属性
        + id跟id的名称不一样

    + 在CSS中每个元素只能有一个id；但是几个元素也可以共享一个id
    + 在实际应用中，元素id不能相同
+ CSS使用class选择器更加方便快捷
+ Js使用id选择器更加方便快捷

### CSS生效的原理
+ 优先原则
    + 后解析的内容会覆盖掉之前解析的内容
+ 继承原则
    + html嵌套里面的标签会拥有外部标签的某些样式，子元素可以继承父元素的某些样式
+ 优先原则：选择器
+ 在同一个选择器里，文件执行是从上往下来进行解析的
```
#ziti {
    color:red

    color:white
}

    此时浏览器字体显示为白色：white
    <div id="ziti">div1</div>
    color:white
```
+ 在同一类型的选择器里，文件执行是从上往下来进行解析的
```
#color {
    background:red
}
#color {
    background:green
}

    此时浏览器背景显示为绿色：green
    <div id="color">div1</div>
    bgckground:green
```
+ 用class选择器来进行解析，产生的效果是一样的
```
.bj1 {
    background:yellow
}
.bj2 {
    background:blue
}

    此时浏览器背景为蓝色：blue
    <div class="bg1 bg2">div2</div>
    background:blue
```
+ 在不同类型的浏览器里，根据不同的优先级来进行解析
    + 先解析低优先级的选择器，再解析高优先级的选择器
    + 四大基本选择器从低到高排列方式为：* < div < class < id
```
#ys {
    background:yellow
}
.bj3 {
    background:green
}

    此时浏览器背景根据优先级选择器显示为黄色：yellow
    <div id="ys" class="bj3">div</div>
    background:yellow
```
+ 外部样式和内部样式合并在一起解析
    + 先解析外部样式，之后再解析内部样式
```
外部样式：css文件里的样式
.ys {
    background:black;
    font-size:30px;
}
内部样式：写在style标签内的样式
<style>
    .ys1 {
        bgckground:rgb(127,155,173)
    }
</style>

    根据规则先解析外部样式，再解析内部样式：
    此时浏览器背景颜色为：rgb(127, 155, 173)
    字体大小为：30px
    <div class="ys1 ys2">div4</div>
    background-color:rgb(127,155,173)
    font-size:30px
```
+ 内敛样式：只有内部样式和外部样式解析完之后，再解析内敛样式
```
#bj4 {
    background-color:rgb(150,150,150);
    font-size:80px;
}
内敛样式:写在标签后面的样式
<div id="bj4" style="font-size:100px">div5</div>

    根据规则先解析内部样式和外部样式，之后再解析内敛样式：
    此时浏览器背景颜色为：rgb(150,150,150)
    字体大小为：100px
    <div id="bj4" style="font-size:100px">div5</div>
    background-color:rgb(150,150,150)
    font-size:100px
```
+ 加了!important字段的，最后执行
```
#bj5 {
    background-color:rgb(92, 76, 76);
    font-size:80px;
}
.ys3 {
    background-color:rgb(113, 155, 113)!important;
}
内敛样式：
<div id="bj5" class="ys3" style="font-size:100px">div6</div>

根据规则先解析外部样式和内部样式，之后再解析内敛样式
    加了importont字段的标签内容最后解析：
    此时浏览器的背景颜色为：rgb(113, 155, 113)
    字体大小为：100px
    <div id="bj5" class="ys3" style="font-size:100px">div6</div>
    background-color:rgb(113, 155, 113)
    font-size:100px
```
### CSS继承原则
+ 跟文字跟文字；文本相关的样式可以被继承，其他的样式不能被继承
```
#txt {
    color:yellow;
    border:1px solid black;
}
     文本属性都可以被下面的子标签继承
    此时浏览器字体颜色为黄色：yellow
    此时浏览器背景为：黑色1px边框
    <div id="txt">div7
            <p>p1</p>
            <div>div8
                <p>p2</p>
            </div>
    </div>
    color:yellow;
    border:1px solid black;
```
+ 块级元素宽度不被设置，则会继承最接近的父元素的宽；高是由块级元素的内容决定
```
#kg {
    width:100px;
    height:200px;
    border:1px solid black;
}
#kg2 {
    height:100px;
    border:5px solid yellow;
}
    
    块级元素的宽不被设置，会自动继承最近父元素的宽
    此时外边框的宽为：100px
    <div id="kg">div9
            <p>p3</p>
            <div id="kg2">div0
                <p>p4</p>
            </div>
        </div>
    </div>
    width:100px
```

### CSS组合选择器
+ 组合选择器：把基本选择器通过特殊的符号串联在一起，用来表达一些特定的意义
    + 分组选择器
    + 嵌套选择器
    + 子选择器
    + 相邻同级选择器
+ 分组选择器：把两个或多个选择器相同的属性可以合并到一起，属性跟属性之间用,隔开，如：div,p,li,ul
```
.back1 {
    background:green;
    color:white;
}
.back2 {
    background:green;
    color:white;
    font-size:50px;
}
    可合并为：
    div,p {
        background:green;
        color:white;
    }
    p {
        font-size:50px;
    }
    此时页面显示的内容跟分开设置div和p标签的属性是一样的，p1不但具有p标签的属性，同时也具有div标签的属性
```
+ 嵌套选择器：把两个相同的属性可以合并到一起，用空格隔开，如：div p 
    + p标签的父级以上包含父级（只要嵌套在div属性里面）标签的话，就可以生效，反之则无效（没有div或p标签的属性值）
    + 只有p标签会包含div属性，div本身没有任何属性

+ 子选择器：把两个相同的属性可以合并到一起，用 > 隔开，如：div > p
    +  p标签的父级是div标签的话，属性才可以生效，反之则无效（没有div或p标签的属性值）
    
+ 相邻同级选择器：把两个相同的属性可以合并到一起，用 + 隔开，如：div + p 
    + 跟div标签同一级别的p标签或者是p标签里面有div标签，属性才可以生效，反之则无效（没有div或p标签的属性值）
