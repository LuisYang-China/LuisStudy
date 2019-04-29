### 表单
+ 表单的作用：收集用户输入，发送或者是提交给服务器
+ 输入：内容
    + 文本：普通可见文本，密码文本
    + 多选框
    + 下拉框
+ 提交：提交按钮
    + http协议：超文本传输协议，主要保证客户和服务器的通讯
+ 表单模式:
    + 请求-应答：浏览器主动发起请求，服务器接收到之后自身左相应的处理，结果返回浏览器
    + 浏览器会根据结果展示出来
+ GIT：默认方式，内容会显示在网址里面
+ POST：内容会显示在后台里面
> 下面是一段代码：
```
 <!--注册页面-->
        <form action="" method="POST"> <!--网址，输入后会跳转相应的页面-->
            用户名：<input type="text" name="usr"><br>
            密码：<input type="password" name="pas"><br>
            <!--单选框-->
            性别：<input type="radio" name="sex" value="male">男
                <input type="radio" name="sex" value="female">女<br>
            <!--复选框-->
            兴趣：<input type="checkbox" name="ckb" value="dushu">读书
                <input type="checkbox" name="ckb" value="dalanqiu">打篮球
                <input type="checkbox" name="ckb" value="tizuqiu">踢足球
                <input type="checkbox" name="ckb" value="huahua">画画<br>
            城市：<select name="city">
                <option value="sh">上海</option>
                <option value="bj">北京</option>
                <option value="sz">深圳</option>
                <option value="gz">广州</option>
            </select><br>
            <!--提交按钮-->
            <input type="submit">
        </form>
```

### 布局
+ 什么是布局
    + 一个完整的一个完整的项目：拿到设计稿；按功能分为小块；按照设计稿的设计排列起来；把具体的内容填充到小块里面
    + 布局：按功能分为小块，并把它排列好
+ 页面布局的属性：
    + div+css
    + table
    + frameset:管理后台
+ iframe：页面框架
    + 在本身的页面里面再嵌套一个页面
> div布局
```
<!--div属性布局--> <!--div的作用就是一个容器，用来装网页的内容--> <!--内容可以放：文字；图片；视频等等-->
        <div style="background:yellow;width:100%;height:200px"><h1>导航</h1></div>
        <div style="background:red;width:20%;float:left;height:300px;"><h1>菜单</h1></div>
        <div style="background:blue;width:80%;float:left;height:300px;"><h1>内容</h1></div>
```
> table属性布局
```
<table border="1" width="100%" height="500px">
            <tr>
                <td colspan="2" style="background:yellow"><h1>导航</h1></td>
            </tr>
            <tr>
                <td width="20%" style="background:red"><h1>菜单</h1></td>
                <td width="80%" style="background:blue"><h1>内容</h1></td>
            </tr>
        </table>  
```

### html的嵌套规则
+ 块元素：独立成一行，可以设置宽高,默认值100%
    + 文字类块元素标签：p h1~h6等等
    + 容器类块元素标签：div table tr td th form ul li ol dl dt dd等等
+ 行元素：不独立成一行，不可设置宽高，默认值是根据内容来决定
    + 行元素标签：a img input strong em del span等等
+ 特殊字符：文字等等内容
    + 特殊字符标签：br &nbsp；等等
+ 嵌套规则：
     + 块元素可以嵌套行元素
     + 行元素可以嵌套行元素
     + 行元素不可以嵌套块元素
     + 文字类元素不可以嵌套块元素

