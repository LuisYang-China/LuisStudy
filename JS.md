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
```
***
### if...else语句
```
<script>
    // 判断一些条件
    if(){
        // 如果条件成立 执行操作
    }else{
        // 否则(不成立) 执行另一种操作
    }
    // 不论条件成不成立 都执行alert操作
    alert();
</script>
```
***
### 
```

    // 用户输入成绩，
    // 如果成绩大于等于85，那么提示优秀；
    // 否则如果成绩大于等于70，那么提示良好；
    // 否则如果成绩60~69，那么提示及格；
    // 否则，不及格
<script>
    var sc = prompt('请输入您的成绩!');
    // 开始判断
    if(sc >= 85){
        alert('优秀');
    }else if(sc >= 70){
        alert('良好');
    }else if(sc >= 60){
        alert('及格!');
    }else{
        alert('不及格!');
    }
    // 不论哪种结果 都弹出这句话
    alert('谢谢查询,祝您生活愉快!');
</script>
```
***
### 三元运算符
```
<script>
    // 条件成立 ? '结果1':'结果2'
    // 例
    alert(sex?'男生':'女生');
    // 如果是男生,执行第一个,如果不是,执行第二个
</script>
```
***
### for循环
```
    //循环1~100
<script>
    // 声明一个i 初始值是0
    // i ++  循环的步长,每次+ 1
    // i <= 100 终止的条件
    for(var i = 0;i <= 100;i ++){
        console.log(i);
    }
    //写循环 要避免死循环 还有无效循环
</script>
```
***
### switch语句
```
<script>
    var fruit = prompt('请输入水果');
    // 类别较少的时候使用  好处 代码很清晰
    switch(fruit){
        // case '输入值':
        case'苹果':
            alert('苹果很好吃');
            break; // 结束当前命令 下面的不再执行
        case'香蕉':
            alert('香蕉很甜');
            break;
        case'梨':
            alert('梨很脆');
            break;
        // 输入的值不存在 就执行
        default:
            alert('没吃过');
            break;
    }
</script>
```
***
### while语句
```
<script>
    // 循环 0~100;
    // num ++ 循环的步长 每次 + 1
    // 不写步长的话 就会无限循环初始值
    var num = 0;
    white(num <= 100){
        console.log(num);
        num ++;
    }
```
***
### do...while语句
```
<script>
    //do...while语句在执行时，会先执行循环体：
    // 循环体执行完毕以后，在对while后的条件表达式进行
    // 判断：如果结果为true，则继续执行循环体，执行完毕继续判断以此类推，如果结果为false，则终止循环。
    // 区别
    // 功能类似
    // while是先判断后执行，而do...while是先执行后判断。
    // 即使条件不满足，do...while可以保证循环体至少执行一次，而while不能
    var num = 0;
    do{
        console.log(num);
        num++;
    }while(num > 0);
    // 后面的比较直都需要规定一个范围 避免无限循环
</script>
```
***
### break 跳出循环
```
<script>
    // 从1-99中找到一个能(+5+7)能被33整除的数
    // 在找到第一个满足的条件后 没必要进行额外的运算 这时候就可以终止循环
    for(var i = 1;i < 100;i ++){
        if((i+5+7)%33 === 0){
            console.log(i); // 找到了一个数值
            //找到了 跳出循环
            break;
        }
    }
    // 有多个for循环的时候 for 循环嵌套
    // break 只能退出当前的for循环
    // 循环打印20遍1~5
    // 程序打印的时候都是从0开始打印的 也可以设置初始值为 1
    for(var i = 1;i <= 20;i ++){
        console.log(i); // 先打印1~20  显示这是第几遍
        for(var j = 1;j <= 5;j ++){
            console.log(j); //打印1~5 
            if(j === 5){
                break; 
                // 当j = 5的时候跳出,结束当前for循环,
                // 返回最外层的for,再循换一遍
            }
        }
    }
</script>
```
***
### continue 跳出当前循环 不影响之后的循环
```
<script>
    // 需求:找到0-100中所有能被3整除或者能被7整除的数
    for(var = 0;i <= 100;i ++){
        if(i % 3 === 0){
            console.log(i); // 能被3整除的数
            // 既然能被3 整除 符合条件 就不用再对他进行能不能被7 整除的操作了
            continue; // 跳出当前循环 不影响之后的循环
        }
        if(i%7 === 0){
            console.log(i); // 能被7整除的数
        }
    }
</script>
```
***
### 数组
```
<script>
    // 数组通常表示某一类数据的集合
    // 获取数组内的元素要通过下标来查找
    // 下标:数组每一个元素都有它对应的下标,下标从0开始
    // 通过下标我们可以查找,修改数组当中的元素
    var nameArr = [1,2,3,4];
    // 通过数组查找元素
    console.log(nameArr[0]; // 数组中下标为0 的元素 1
    console.log(nameArr[1]); // 2
    console.log(nameArr[2]); // 3
    console.log(nameArr[3]); // 4
    // 通过下标修改元素
    nameArr[0] = 5; // 把数组中下标为0 的元素修改为5
    console.log(nameArr); // [5,2,3,4]
    nameArr[4] = 6; // 数组中没有下标为4的元素 这是就等于重新添加了一个元素
    console.log(nameArr); // [5,2,3,4,6];

    // length属性 元素的长度 元素里面元素的个数  从1 开始
    console.log(nameArr.length); // 5 
    var nameArr2 = [];
    console.log(nameArr2.length); // 0
    // 空数组长度为0
</script>
```
***
### 遍历数组
```
<script>
    
