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
    var age = [23,43,64,54,46,17,32];
    // 数组里最后一个元素的下标就是数组长度-1  age.length - 1
    // for循环遍历数组,就是查找到里边所有的元素 ,筛选出需要的元素
    //查到出当前数组中大于30 的数
    // 通过下标查找 下标长度是数组长度- 1 
    for(var i = 0;i < length;i ++){
        if(age(i) > 30){
            console.log(age[i]); // 43,64,54,46,32
        }
    }

    // for...in 也可以实现数组的遍历
    var key = age.length -1;
    // key 是数组age的下标
    for(var key in age){
        console.log(key); // 0 1 2 3 4 5 6
        console.log(age[key]); // 跟下标对应的元素值
    }
</script>
```
***
### 数组方法
```
    // 合并数组 xx.concat() 并不影响原数组
    var arr1 = [2,3,4];
    var arr2 = [5,6,7];
    // 设置一个新的变量接收新合并的值
    // 操作不影响原数组的时候 需要一个新的变量接收合并完成的数组
    var arr3 = arr2.concat(arr1);
    console.log(arr3); // [5,6,7,2,3,4];
    console.log(arr2); // [5,6,7] 并没有影响原数组

    // 字符串转换成数组
    // arr.split('分隔符','指定生成数组的长度');
    var name = '张三,李四,王五,赵六';
    var name2 = name.split(',',3);
    console.log(name2); // [张三,李四,王五]
    var sentence = 'Hello World';
    var sentence2 = sentence.split('o',2);
    // 分隔符也可以是字符串的元素
    console.log(sentence2); // [Hell, W] 以o字母分隔

    // 数组转换成字符串
    // arr.join('连接符号');参数不写 默认用逗号连接
    var name3 = ['张三','李四','王五'];
    var name4 = name3.join('|');
    console.log(name4); // '张三 | 李四 | 王五'

    // 添加数组元素
    // push() 从数组最后添加一个元素 改变了原数组
    var num = [2,3,4];
    var num5 = num.push(5);
    console.log(num5); // 4 返回新数组的长度
    console.log(num); // [2,3,4,5]
    // unshift() 从数组前面添加一个元素 改变原数组
    var num6 = num.unshift(7);
    console.log(num6); // 5 返回新数组的长度
    console.log(num); // [7,2,3,4,5]

    // 删除数组元素
    // pop() 从数组最后删除最后一个元素 改变原数组
    var num1 = [2,3,4,5,6,7];
    var num2 = num1.pop();
    console.log(num2); // [7] 返回删除的元素
    console.log(num1); // [2,3,4,5,6]
    // shift() 从数组前面删除一个元素 改变原数组
    var num3 = num1.shift();
    console.log(num3); // [2] 返回删除的元素
    console.log(num1);[3,4,5,6]
</script>
```
***
### 数组求平均值
```
<srcipt>
    var arr = [32,41,1,40,12,5];
    // 先计算数组元素的和 再获取数组元素个数 求平均值
    var num = 0;
    for(var i = 0;i < arr.length;i ++){
        // 所有数组元素的和
        sum = sum + arr[i]
    }
    console.log(sum); // 数组元素的和
    // 数组元素的和除以数组的长度(数组元素的个数)
    var avg = sum / arr.length;
    console.log(avg); // 平均值
</srcipt>
```
***
### 冒泡排序
```
<script>
    var arr = [23,45,26,34,47,25,17,32];
    // for 控制比较几轮 没有第0轮 所以i = 1
    for(var i = 1;i < arr.lenght;i ++){
        for(var j = 0;j < arr.length-i;j ++){
            // 里面的for找到本轮里最大的数
            // 因为第二轮一经找到了第一轮当中对大的数字
            // 所以就不用再比较它 所以j < arr.length-i
            // 对 j 里面的元素作比较
            // 如果 j 的第一个元素比第二个元素大的时候
            if(arr[j] > arr[j+1]){
                // 换位置
                var temp = arr[j];
                arr[j] = arr[j+1];
                arr[j+1] = temp;
            }
        }
        console.log(arr); // 每一次比较的结果
        // [23,26,34,45,25,17,32,47]
        // [23,26,34,25,17,32,45,47]
        // [23,26,25,17,32,34,45,47]
        // [23,25,17,26,32,34,45,47]
        // [23,17,25,26,32,34,45,47]
        // [17,23,25,26,32,34,45,47]
        // [17,23,25,26,32,34,45,47]
    }
    console.log(arr); // 最后排序好的结果
    // [17,23,25,26,32,34,45,47]
</script>
```
***
### 圆的周长和面积
```
<script>
    // 圆周率3.1415926 在编程里面用 Math.PI 表示
    // 圆的周长
    var r = 4;
    function zc(r){
        return 2*Math.PI*r;
    }
    console.log(zc(r)); // 圆的周长
    function area(r){
        return Math.PI*r*r;
    }
    console.log(area(r)); // 圆的面积
</script>
```
***
### 比较数值
```
<script>
    function getMax(a,b){
        // 用三元运算符比较
        return a >= b?a:b;
    }
    console.log(getMax(3,4)); // 4

    // 比较多个数值
    function getMax2(a,b,c){
        return getMax(getMax(a,b),c);
    }
    console.log(getMax2(3,4,5)); // 5
</script>
```
***
### 求数组当中的最大值和最小值
```
<script>
    var arr = [34,56,23,76,32];
    function getMax(arr){
        var maxIndex = 0;
        for(var i = 1;i < arr.length;i ++){
            // 当下标为 i 的值大于 maxIndex 的时候
            // 把值赋给 maxIndex
            if(arr[maxIndex] < arr[i]){
                maxIndex = i;
            }
        }
        // 都比较之后剩下的数值就是数组里面最大的值
        return arr[maxIndex];
    }
    console.log(getMax(arr));
</script>
```
***
### 反转数组
```
<script>
    var arr = ['a','b','c','d','e'];
    // 最终的值为 ['e','d','c','b','a'];
    // 可以采用倒叙的方法
    function reverse(arr){
        var newArr = [];
        获取arr的下标
        for(var i = arr.length-1;i >= 0;i --){
            // 从后面插入 arr[i] 相对应的值
            newArr.push(arr[i]);
        }
        return newArr
    }
    console.log(reverse(arr));

    // 如果长度为6 
    // 数字的下标可以写成对应的形式 0 5;1 4;2 3
    // 也就是说 i  arr.length- 1- i
    function reverse2(arr){
        for(var i = 0;i < Math.floor(arr.length/2);i ++){
            // 参考冒泡排序写法
            var index = arr.length -1 -i
            var temp = arr[i];
            arr[i]  = arr[index];
            arr[index] = temp;
        }
        return arr;
    }
    console.log(reverse2(arr));
```
***
### 阶乘
```
    // 求 5 的阶乘
    // 5! = 5*4*3*2*1
    function getFactorial(num){
        var jc = 1;
        // num 跟 jc 乘过的结果会返回 jc 然后跟下一个值相乘
        for(var i = 1;i <= num;i ++){
            jc = jc * i;
        }
        return jc;
    }
    console.log(getFactorial(5));

    // 递归思想  解法2
    // 5! = 4! * 5
    // 4! = 3! * 4
    // 3! = 2! * 3 ...
    function jc(num){
        // 递归的跳出条件
        if(num === 1){
            return 1;
        }
        return jc(num - 1)*num;
    }
    console.log(num);
    // 假如 num = 5;
    // 返回的是 jc(4) * 5
    // 下轮 jc(4) 执行 返回 jc(3) * 4
    // 下轮 jc(3) 执行 返回 jc(2) * 3
    // 下轮 jc(2) 执行 返回 jc(1) * 2
    // 下轮 jc(1) 执行 返回 1 
    // jc(4) * 5 ===> 1*2*3*4*5 === 5！
    // 注意 递归必须有跳出条件
</script>
```
***
### 求阶乘和
```
<script>
    // 累加相乘的值
    function jch(num){
        var sum = 0;
        for(var i = 1;i <= num;i ++){
            sum = sum + getFactorial(i);
        }
        return sum;
    }
    // 算出每次相乘的值
    function getFactorial(num){
        var jc = 1;
        for(var i = 1;i <= num;i ++){
            jc = jc * i;
        }
        return jc;
    }
    console.log(jch(5));
</script>
```
***
### 判断质数
```
<script>
    // 质数只能被它自己或 1 整除
    function isPrime(num){
        // 假设 是一个质数
        var isZhi = true;
        // 2 是最小的质数
        for(var i = 2;i < num;i ++){
            if(num % i === 0){
                isZhi = false;
            }
        }
        // 三元运算符 辨证一下
        return isZhi?'是一个质数':'不是一个质数';
    }
    console.log(isPrime(6));
</script>
```
***
### 不死神兔
```
<script>
    // 求斐波那契(宇宙的真理！)数列Fibonacci中的第n个数是多少？  
    // 有一对兔子，从出生起后第3个月起每个月都生一对兔子，
    // 小兔子长到第三个月后每个月又生一对兔子，
    // 假如兔子都不死，问第二十个月的兔子对数为多少？ 不死神兔
    // 1 1 2 3 5 8 13 21... 
    // 规律 第三个月开始 下个月兔子数量都等于前两个月之和
    function fb(n){
        // 跳出条件
        if(n === 1||n === 2){
            return 1;
        }
        retuen fb(n - 1)+ fb(n - 2);
    }  
    console.log(fb(7));
</script>
```
***
### 求一年当中的第几天
```
<script>
    // 输入某年某月某日，判断这一天是这一年的第几天？（闰年）
    // （四年一闰，百年不闰，四百年在闰）
    // 只有在闰年的时候366天  在2月29天多一天
    // 其余的时间2月都是28
    // 1.是否是闰年
    // 2.每个月多少天
    // 3.Date提供了一个构造函数 
    // 可以接受一个yyyy-MM-dd HH:mm:ss类型的字符串 可以转换为date对象
    var totalDay = 0;
    var date = new Date('2015-02-28');
    console.log(date);
    // 获取年份
    var year = date.getFullYear();
    // 获取月份
    var mouth = date.getMonth()+1;
    // 获取日
    var day = date.getDate();
    var mouthArr = [31,28,31,30,31,30,31,31,30,31,30,31];
    for(var i = 0;i < mouth -1;i ++){
        totalDay = totalDay + monthArr[i];
    }
    // 加上当月天数
    totalDay = totalDay + day;
    // 判读是否为闰年
    if(isRun(year)&&mouth > 2){
        totalDay = totalDay + 1;
    }
    console.log(totalDay);
    function isRun(year){
        if((year % 4 === 0&&year % 100 !== 0)||year % 400 === 0){
            return true;
        }
        return false;
    }
</script>
```
***
### 对象
```
<script>
    var obj = {
        name:'张三',
        age:'20',
        say:function(){
            alert('我是张三')
        },
        child:{
            name:'小明';
            age:'3',
        }
    }
    // 属性(特征) 方法(行为/动态)
    // 封装信息
    // 对象属性值 任意的数据类型 属性是函数 我们称之为对象的方法

    // 调用对象的方法
    obj.say();
    // 获取对象属性
    obj.name;

    // 对象的分类
    // 内置对象 Date Math Number
    // 宿主对象 由JS的运行环境提供的对象 目前来讲主要是指由浏览器提供的对象
    // 如 BOM DOM
    // 开发者自己定义的对象
</script>
```
***
### 创建对象
```
    // 通过顶级对象Object new
    var obj = new Object;
    // 创建了一个空对象

    // 为 obj追加 name属性
    obj.name = '张三';
    obj.age = 20;
    // 修改name属性
    obj.name = '李四';
    // 为obj 追加方法
    obj.say = function(){
        alert('我是李四');
    }
    console.log(obj);

    // 字面量创建
    var obj = {
        name:'张三',
        age:20,
        say:function(){
            alert('我是张三');
        },
        child:{
            name:'小明',
            age:3;
        },
    }
    // 为obj追加属性和方法
    // 在创建的时候 可以直接指定对象中的属性和方法

    // 自定义构造函数
    function Person(){
        // this是一个指针
        // 构造函数当中的this指向 new出来的示例对象
        this.name = '张三';
        this.age = '20';
        this.child = {
            name:'小明',
            age:3,
        };
        this.say = function(){
            alert(this.name);
        }
    }
    var obj3 = new Person;
    console.log(obj3);
    obj3.say();
    // 如果不通过new实例对象 那么this指向调用者
    // 谁调用this就指向谁
```
***
### JSON对象
```
<script>
    var obj = {
        a:'Hello',
        b:'World',
    };
    // 这是一个对象
    var json = '{"a": "Hello","b": "world"}';
    // 这是一个json字符串 本质是一个字符串 可以进行网络传输

    var movieJson = {
        "title": "西虹市首富",
        "directors": "闫非",
        "year": "2018",
    }
    // 这是一个json对象 依然是对象 不能进行网络传输
    // 向后台传输数据 需要把对象转换为json字符串
    var movieStr = JSON.stringify(movieJson);
    // 也可以把普通对象转换成json字符串
    var str = JSON.stringify(obj);
```
***
### 对象的遍历
```
<stript>
    // for in 用于对象（json对象也可以)的遍历
    var movieJson = {
        "title":"西虹市首富",
        "directors":"闫非",
        "year":"2018",
    }
    // key 指遍历 对象的下标
    for(var key in movieJson){
        console.log(key);
        // key 是变量 所以需要用obj[key]的方式获取对象属性
        console.log(movieJson[key]);
        // 非常重要！xx.abc abc是变量的话 就必须通过xx[abc]的方式获取相对应的值
    }
```
***
### 数组高级API
```
<script>
    // 合并 concat()
    // 添加 unshift() / push()
    // 删除 shift() / pop()

    // 数组转换成字符串
    // arr.toString
    var num = [2,3,4,5,6];
    // 把数组转换为字符串 默认用逗号隔开
    console.log(num.toString);

    // reverse 反转数组
    num.reverse(); // 会改变原数组 返回改变后的数组
    console.log(num);

    //给数组排序，返回排序后的数组。如何排序看参数
    // 无参：按照数组元素的首字符对应的Unicode编码值从小到大排列数组元素。
    // 带参：必须为函数（回调函数--callback）。函数中带有两个参数，
    // 代表数组中的前后元素。如果计算后（a-b），返回值为负数，a排b前面。等于0不动
    // 返回值为正数，a排b后面
    var num2 = [1,2,34,35,23];
    num2.sort(); // 改变原数组
    num2.sort(function(a,b){
        return a-b;
    });
    console.log(num2);

    // indexOf()、lastIndexOf()   //如果没找到返回-1
    // 返回对应数值在数组中的下标
    var name = ['张三','李四','王五','马六'];
    console.log(name.indexOf('李四')); // 1
    console.log(name.indexOf('马六')); // 3
    var name = ['张三','李四','王五','王五','马六'];
    // 从后往前查找对应元素
    console.log(lastIndexOf('王五')); // 3
    // 从后往前查找 找到第一个 返回相对应的下标
    console.log(name.indexOf('小明')); // -1
    // 如果查找不到 返回-1
</script>
```
***
### String方法
```
<script>
    var str = 'how are you? im fine.'
    // 获取字符串长度
    sonsole.log(str.length); // 21
    // charAt() 获取相应位置的字符
    // 空格也占字符长度位置
    console.log(str.charAt(5)); // r
    // charCodeAt() 方法可返回指定位置字符的 Unicode 编码
    console.log(str.charCodeAt(5)); // r 114

    // indexOf() / lastIndexOf()
    // 返回字符在字符串中的位置
    // 从前查找
    console.log(str.indexOf('e')); // 7
    // 从后查找
    console.log(str.lastIndexOf('e')); // 20

    // concat() 连接字符串
    var str2 = 'and you?';
    console.log(str.concat(str2));
    // 'how are you? im fine.and you?'

    // slice() 提取字符串的某个部分 并以新的字符串返回被提取的部分
    console.log(str.slice(0,9)); // how are y
    console.log(str.slice(0)); // 不写结束值就默认提取整个字符串
    console.log(str.slice(2,6)); // 'w ar'

    // substr(起始位置,[取的个数]);
    // 截取字符串 返回截取的字符串
    console.log(str.substr(0)); // 不写取的个数 截取整个字符串
    console.log(str.substr(2,6));// w are

    // 转换大小写
    console.log(str.toUpperCase()); // HOW ARE YOU? IM FINE. // 不会转变原数组
    sonsole.log(str.toLowerCase()); // how are you? im fine.
</script>
```


    
