### js引入
```
<!DOCTYPE html>
<html lang="zh>
<head>
    <meta charest="UTF-8">
    <title>JS书写形式</title>
    <!-- 外部引入格式 -->
    <script crc="test.js"></script>
    <script>
        <!-- 也可以写在head标签里面,用script标签 -->
    </script>
</head>
<body>
<!-- 也可以写在所有标签之后 -->
    <script>
       if(confirm('你是中国人吗?')){
			alert('你好')
		}else{
			alert('不会外语')
		}*/
		// prompt('请输入你的年龄:')

		document.write('<p>不烦学院</p>'); 
    </script>
</body>
</html>
```
***
### Js变量
```
var a = 10;
<!-- 推荐方式 -->
<!-- 用var元素声明变量a,并赋值10 -->
// 注意的是 ,变量需要先声明,才能使用
	console.log(c); // 报错
// 变量名 命名规则
	// 字母 数字 _ $ 
	// 不能以数字开头
	// 严格区分大小写
	// 不能使用关键字,保留字
	// 驼峰命名
	// 见名知意
```
***
### 数据类型
```
1:基本数据类型
    Number类型：整数和浮点数(小数)
    String类型：字符串
    Boolean布朗类型：也叫布尔值；返回值只有true和false
    undefined类型：只有一个值 undefined
        当一个变量声明了，但是没有被赋值，它就是一个undefined
    null：空对象
2:复杂数据类型
    array：数组
    object：对象 也可以用key value的形式
    function：函数
```
***
### 数据类型的判断
```
<script>
    var age = 29;
    var sex = true;
    var like = ['篮球','足球'];
    var child = {
        name:'张';
        age:2;
    }
    function foo(){

    }
    //typeof 可以判断数据类型
    console.log(typeof age); // number
    console.log(typeof sex); // boolean
    console.log(typeof like); // object
    console.log(typeof child); // object
    console.log(typeof foo); // function
</script>
```
***
### 数据类型转换
```
1：转换成number类型
    parseInt() 转换为整数
		// 转换规则：从第一个非空白字符（空格、换行、  tab）开始转换，直到遇到一个非数字字符为止。
    parseFloat() 转换成浮点数
		从第一个非空白字符（空格、换行、tab）开始转换，直到遇到一个非数字字符为止
		遇到的第一个小数点有效，第二个小数点就无效了
2: 转换为boolean 类型
		数字 --> 布尔。除了0和NaN，其余的都是true。
		字符串 ---> 布尔。除了空串，其余的都是true。
		null和undefined都会转换为false。
	    对象也会转换为true。
3：转换为string类型
        number==> string + 拼接的作用
```
***
### 比较运算符
```
    > 大于
    < 小于
    >= 大于等于
    <= 小于等于
    == 等于 (只比较数值，不比较类型，比较之前会进行隐式转换)
    === 绝对等于 (类型和数值都要相等才可)
    != 不等于 与等于相反
    !== 绝对不等于 于绝对等于相反
    语法：表达式1 运算符 表达式2
    如果关系成立返回true 否则返回false
    console.log('23' == 23); // true
    console.log('23' === 23); // false
```
***
### 算术运算符
```
    + 加 (除了加法运算之外，还有拼接字符串的功能)
    - 减
    * 乘
    / 除
    % 取余数
```
***
### Date对象
```
<script>
var date = new Date();
//Thu Oct 25 2018 09:23:11 GMT+0800  格林威治时间 东8时(北京时间)
// 创建一个构造函数(对象)的示例对象
var year = date.getFullYear();
// 调用对象 date 的年份
var mouth = date.getMouth()+1; // 0~11
// 调用对象 date 的月份，下标是从0开始的所以+1
var day = date.getDate();
// 调用对象 date 的天数  变量名冲突，后面会覆盖前面的属性
var hour = date.getHours();
// 调用对象 date 的小时
var min = date.getMinutes();
// 调用对象 date 的分钟
var sec = date.getSeconds();
// 调用对象 date 的秒数
// 程序语言中时间的最小单位是毫秒  1s = 1000ms
var mm = date.getMilliseconds();
// 调用对象 date 的毫秒数

// 时间戳  + 连接符是所有编程语言中最常见的操作
// 新建一个变量用来接收新的时间
var nowTime = year + '年' + month + '月' + day + '日' + hour + ':' + min + ':' + sec + ':' + mm;
console.log('当前时间为：' + nowTime);
</script>
```
***
### Math
```
// Math 不需要new 是一个静态方法
    Math.ceil(x.y); // 天花板函数(小数) 向上取整
    Math.floor(x.y); // 地板函数(小数) 向下取整
    Math.max(x,y,z); // 比较大小取最大值
    Math.min(x,y,z); // 比较大小去最小值
    Math.random(); // 取随机值,范围0~1,伪随机
    Math.floor(Math.random()*个数+最小值); // 取任意范围的随机值
    Math.floor(Math.random()*16+5); // 5~20的随机值,数字5,6,7,...,20 16个数值,最小值5
    Math.round(); // 四舍五入  在某些情况下回存在舍入误差
    Math.round(3.99999999999999999); // 4
```
***
### 逻辑运算符
```
    &&  并且  满足一个条件并且满足第二个条件才会执行
    ||  或者  满足一个条件或者满足第二个条件才会执行
    !   非    不满足条件
    console.log(a < b > c); // 比较运算符不能连写
    console.log(a < b&&b > c); // 正确写法
