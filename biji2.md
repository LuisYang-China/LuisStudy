### html图片引入
+ 图片格式分为：
    + jpg格式：有损压缩，会影响画质，图片小，不支持透明通道
    + png格式：无损压缩，不影响画质，图片大，支持透明通道
    + gif格式：动图
+ 图片引入方式
    + 网络图片：通过网络直接复制图片地址直接导入的路径
> 如

```
<img src="http://i1.mifile.cn/a4/xmad_15538455213855_QATqB.jpg">
```

    + 本地图片：
        + 绝对路径：从盘符开始算起的路径
> 如

```
<img src="D:\课堂作业\qiuqiu.jpg" alt="我的小猫" title="喵。。">
```

        + 相对路径：从当前符开始算起的路径
> 如

```
<img src="qiuqiu.jpg" alt="我的小猫" title="喵。。。">
``` 

        + 图片跟文件夹一个路径的时候表示为：

```
<img src="../课堂练习2/qiuqiu2.jpg" alt="我的小猫" title="喵。。。。"> <!--../代表上级目录-->
```

### a标签
+ a标签内可以放文字，图片，动图等元素
> 如

```
<a href="http://www.baidu.com" target="_blank">超级链接</a> <!--target="_blank"属性：在新窗口打开-->
```

+ a标签的href属性可以添加网址，页面等元素
+ a标签也可以当作锚点使用

```
<a href="#">返回最上级
```

### 有序列表和无序列表
+ 无序列表
    +内容列表，ul+li，无顺序关系
>如

```
<ul>
    <li>无需列表1</li> <!--li{无序列表$}*5-->
    <li>无需列表2</li>
    <li>无需列表3</li>
    <li>无需列表4</li>
    <li>无需列表5</li>
</ul>
```

    + 有序列表
        +内容列表，ol+li，有顺序关系
> 如

```
<ol>
    <li>有序列表1</li>
    <li>有序列表2</li>
    <li>有序列表3</li>
    <li>有序列表4</li>
    <li>有序列表5</li>
</ol>
```

    +自定义列表
        +内容标题+内容组成的列表，dl+dt+dd
> 如

```
<dl><!--标题-->
    <dt><!--目录-->
        <dd>自定义列表1</dd> <!--dd开头首行缩进-->
        <dd>自定义列表2</dd>
        <dd>自定义列表3</dd>
        <dd>自定义列表4</dd>
        <dd>自定义列表5</dd>
    </dt>
<dl>
```

### 表格
+ 若干行：tr
+ 若干格：
    + 标题：th
    + 内容：td
+ colspan：单元格可横跨的列数
+ rowspan：单元格可横跨的行数
> 如

```
<table border="1"> <!--border：边框,后面边框属性1~10--> <!--table:表格-->
 <tr>
    <th>部门</th> <!--标题-->
    <th>姓名</th>
    <th>性别</th>
    <th>工资</th>
</tr>
<tr>
    <td>开发组</td> <!--内容-->
    <td>小文</td>
    <td>男</td>
    <td>1w</td>
</tr>
<tr>
    <td>开发组</td>
    <td>露露</td>
    <td>女</td>
    <td>1w</td>
</tr>
<tr>
    <td>开发组</td>
    <td>小明</td>
    <td>男</td>
    <td>1w</td>
</tr>
</table>
```

+ 可以使用colspan和rowspan属性合并单元格为

```
<table border="1">
<tr>
    <th>部门</th>
    <th>姓名</th>
    <th>性别</th>
    <th>工资</th>
</tr>
<tr>
    <td rowspan="4">开发组</td> <!--rowspan：单元格可横跨的行数-->
    <td>小文</td>
    <td>男</td>
    <td>1W</td>
</tr>
<tr>
    <td>露露</td>
    <td>女</td>
    <td>1W</td>
</tr>
<tr>
    <td>小明</td>
    <td>男</td>
    <td>1W</td>
</tr>
<tr>
    <td colspan="2">工资合计：</td> <!--colspan：单元格可横跨的列数-->
    <td>3W</td>
</tr>
</table>
```