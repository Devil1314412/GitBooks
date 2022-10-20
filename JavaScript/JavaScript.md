# JavaScript

## 一、初识JavaScript

### 1. JS

#### 行内式JS

```js
<input type="button" value="点我试试" onclick="alert('Hello')"/>
```

#### 内嵌JS

```js
<script>
    alert('Hello');
</script>
```

#### 外部JS文件

```js
<script src="my.js"></script>
```

### 2. JS输入输出语句

>alert(msg)      浏览器弹出警示框
>console.log(msg)    浏览器控制台打印输出信息
>prompt(info)    浏览器弹出输入框，用户可以输入

### 3. 变量

#### 声明变量

```js
var age;	//声明一个名称为age的变量
```

#### 变量的初始化

```js
var age = 18;	//声明变量同时赋值为18
```

## 二、数据类型

### 1. 简单数据类型

#### 简单数据类型

> （ Number | Boolean | String | Undefined | Null )
>
> 存放在栈里面，里面直接开辟一个空间存放的是值

八进制 `var num1 = 010;`  数字前面加 `0`

十六进制`var num2 = 0x9;` 数字前面加`0x`

##### 字符串类型 string  	

> 推荐使用单引号，嵌套时  内双外单  或  外双内单

##### 字符串转义字符

`\n` 	换行符				`\\` 	斜杠\					`\'`	'单引号

`\"` 	"双引号		  	`\t` 	tab缩进				`\b` 	空格

##### 字符串长度 length

```js
var str = 'my name is Lean'
console.log(str.length);  //显示15
```

##### 字符串拼接

> 字符串 + 任何类型 = 拼接之后的字符串  （数值相加，字符相连）

```js
var age = 18;
console.log('我永远' + age + '岁');  //我永远18岁
```

##### 布尔型 bollean

> true 和 false

##### 未定义数据类型 undefined

##### 空值 null

### 2. 复杂数据类型

#### 复杂数据类型

>首先在栈里面存放地址 十六进制表示 然后这个地址指向堆里面的数据
>
>在存储时变量中存储的仅仅是地址(引用），因此叫做引用数据类型
>
>简单说 : 通过new关键字创建的对象都是复杂数据类型（系统对象、自定义对象），如Object、Array、Date等

### 3. 获取变量数据类型

#### 获取检测变量的数据类型

`typeof`可用来获取检测变量的数据类型

```js
var num = 10;
console.log(typoef num);  //number
```

#### 字面量

> 数字字面量：`8, 9, 10`
>
> 字符串字面量：`'今天晴转多云'`
>
> 布尔字面量：`true、false`

### 4. 数据类型转换

使用`表单`、`prompt`获取过来的数据默认是字符串类型的，此时就不能直接简单的进行加法运算，而需要转换变量的数据类型，就是把一种数据类型的变量转换成另外一种数据类型。

#### 转换为字符串

加号拼接字符串	`num + ' '`

#### 转换为数字型(重点)

> parseInt(string) 函数	将 string 类型转成`整数数值型` 	parseInt('78')
>
> parsetFloat(string) 函数	将 string 类型转成`浮点数数值型` 	parsetFloat('78.21')
>
> Number() 强制转换函数	将 string 类型转换为`数值型`	Number('12')
>
> js 隐式转换 (- * /)	利用`算术运算`隐式转换为数值型		'12' - 0

#### 转换为布尔型

Boolean() 函数		其它类型转成布尔值		Boolean('true');

代表空、否定的值会被转化为 false

## 三、JavaScript 运算符

### 1. 算术运算符（+  -  *  /  %）

### 2. 递增和递减运算符（++  --）

> 前置递增运算符		++num 	  num = num + 1		先加1后反值
>
> 后置递增运算符		num++		num = num + 1		先反值后加1

### 3. 比较运算符（>   <   >=   <=   ==   !=   ===   !==）

判等号默认转型为数字类型，全等要求值和数据类型都一致

### 4. 逻辑运算符（&&  ||  !）

短路运算（逻辑中断）

```js
console.log(123 && 456);  //456           如果第一个表达式的值为真，则返回表达式2
console.log(0 && 456);  //0                如果第一个表达式的值为假，则返回表达式1
console.log(123 || 456);  //123             如果第一个表达式为真，则返回表达式1
console.log(0 || 456);  //456               如果第一个表达式为假，则返回表达式2
```

### 5. 赋值运算符(=  +=  -=  *=  /=  %=)

```js
num = num + 2;  //num += 2
```

### 6. 运算符优先级

![算术符优先级 ](./static/images/%E7%AE%97%E6%9C%AF%E7%AC%A6%E4%BC%98%E5%85%88%E7%BA%A7%20.png)

## 四、流程控制

### 1. 顺序流程控制

按照代码的先后顺序，依次执行

### 2. 分支流程控制

#### if else 语句

```js
<script>
    var year = prompt('请输入您想要查询的年份：');
    year1 = !(year % 4);
    year2 = !(year % 100);
    year3 = !(year % 400);
    if (year1 && year2 || year3) {
    if (year % 4 == 0 && year % 100 != 0 || year % 400 ==0) {
        alert('这一年是闰年');
    } else {
        alert('这一年是平年')
    }
</script>
```

#### if else if 语句

```js
<script>
var score = prompt('请输入分数：');
    if (score >= 90) {
        alert('A');
    } else if (score >= 80) {
        alert('B')
    } else if (score >= 70) {
        alert('C')
    } else if (score >= 60) {
        alert('D')
    } else {
        alert('E')
    }
</script>
```

#### switch 语句

```js
switch(表达式) {
        case value1:
            执行语句1;
            break;
        case value2:
            执行语句2;
            break;
        ...
        default:
            执行最后的语句;
}
```
#### 三元表达式

条件表达式 ? 表达式1 : 表达式2;

> 如果条件表达式结果为真 则 返回表达式1的值 如果条件表达式结果为假 则返回表达式2的值

```js
<script>
    var num = prompt('请输入0~59之间的一个数字:');
    var num1 = num < 10 ? '0' + num : num;
    alert(num1);
</script>
```

### 3. 循环流程控制

#### for 循环

```js
for(初始化变量; 条件表达式; 操作表达式) {
            //循环体
}
```

```js
<script>
//  1~100之间所有偶数和奇数的和
    var even = 0;
    var odd = 0;
    for (var i = 1;i <= 100;i++) {
        if (i%2 == 0) {
            even = even + i;
        } else {
            odd = odd + i;
        }
    }
    console.log('1~100之间所有的偶数和是' + even);
    console.log('1~100之间所有的奇数和是' + odd);
</script>
```

#### 双重 for 循环

```js
for (外层的初始化变量;外层的条件表达式;外层的操作表达式) {
       for (里层的初始化变量;里层的条件表达式;里层的操作表达式) {
                    // 执行语句;
        }
}
```

```js
<script> 
//  9*9乘法表
    var str = '';
    for (var i = 1;i <= 9; i++) {       //外层循环控制行数
        for (var j = 1; j <= i ; j++) {     //每一行公式的个数正好和行数一致，j<=i
            str += j + 'x' + i + '=' + i * j + '\t';    // str = str + j + 'x' + i + '=' + i * j + '\t';
        }
        str = str + '\n'
    }
    console.log(str);
</script>
```

#### while 循环

```js
while (条件表达式) {
    //  循环体代码;
}
```

#### do...while 循环

```js
do {
        //  循环体
} while (条件表达式)
```

```js
<script>
//  1~100之间所有整数的和
    var sum = 0;
    var i = 0;
    do {
        sum += i;
        i++;
    } while (i <= 100);
    console.log(sum);
</script>
```

### 4. continue 和 break

> continue关键字跳出本次循环，继续下一次循环
> break关键字跳出整个循环，结束循环

## 五、数组

### 1. 利用 new 创建数组

```js
var arr = new Array();		//创建一个新的空数组
```

### 2. 利用数组字面量创建数组

使用数组字面量方式创建空的数组

```js
var 数组名 = [];
```

使用数组字面量方式创建带初始值的数组

```js
var 数组名 = ['小白','小黑','大黄','瑞奇'];
```

### 3. 遍历数组

把数组的元素从头到尾访问一次（用循环）

```js
//  找出数组[2,6,1,77,54,32,3]中的最大值
    var arr =[2,6,1,77,54,32,3];
    var max = arr[0]
    for (var i = 0; i < arr.length; i++) {
        if (arr[i] > max) {
            max = arr[i];
        }
    }
    console.log('该数组中的最大值是：' + max);
```

### 4. 数组的长度

>  数组名.length

### 5. 新增数组元素

> 修改length长度

```js
//  新增数组元素  修改length长度
    var arr = ['red','yellow','blue'];
    console.log(arr.length);
    arr.length = 5;  //修改数组长度为5
    console.log(arr);
    console.log(arr[4]);  // undefined
```

>  修改索引号

```js
//  新增数组 修改索引号  追加数组元素
    var arr1 = ['red','yellow','blue'];
    arr1[3] = 'black';
    console.log(arr1);
    arr1[4]  = 'dark';
    console.log(arr1);
    arr1[1] = 'green';
    console.log(arr1);
```

## 六、JS函数

函数就是封装了一段可以被重复执行调用的代码块，目的就是可以让大量代码重复使用

### 1. 声明函数

```js
function 函数名() {            //function 声明函数的关键字  全部小写
                //  函数体     //函数是做某件事情，函数名一般是动词
            }                 //函数不调用自己不执行
```

### 2. 调用函数

```js
  函数名();                  //调用函数的时候不要忘记加小括号
```

```js
//  利用函数计算1~100之间的累加和
    //  封装函数
    function getSum() {
        var sum = 0;
        for (var i = 1; i <= 100; i++) {
            sum = sum + i;
        }
        console.log(sum);
    }
    
    //  调用函数
    getSum();
```

### 3. 形参和实参

```js
function 函数名(形参1,形参2...) {          //  形式上的参数
        //  函数体
    }
    函数名(实参1,实参2...);                    //  实际的参数
```

```js
//  形参和实参，求任意两个数之间的和
    function getSumm(num1, num2) {
        var sum = 0;
        for (var i = num1; i <= num2; i++) {
            sum = sum + i;
        }
        console.log(sum)
    }
	getSumm(5, 10);
```

### 4. return 语句

不仅可以退出循环，还能够返回 return 语句中的值，同时还可以结束当前函数体内的代码

```js
function 函数名() {
       return 需要返回的结果;
}
   函数名();
```

```js
//  求任意两个数的和
    function getSums(num1, num2) {
        return num1 + num2;
    }
    console.log(getSums(1, 2));
```

### 5.arguments 的使用

arguments 对象存储了传递的所有实参

```js
function fn() {
        console.log(arguments);  //  Arguments(3) [1, 2, 3]
        console.log(arguments.length);  //  3
        console.log(arguments[2]);  //  3
        // 可以按照数组的方式遍历arguments
        for (var i = 0; i < arguments.length; i++) {
            console.log(arguments[i]);      //  1   2   3
        }
    }
    fn(1,2,3);
```

```js
//  利用函数求任意个数的最大值
    function getMax() {
        var max = arguments[0];
        for (var i = 1; i < arguments.length; i++) {
            if (arguments[i] > max) {
                max = arguments[i];
            }
        }
        return max;
    }
    console.log(getMax(1,2,3,4));
    console.log(getMax(134,23,455,345,1,223));
```

### 6. 函数的相互调用

```js
//  函数可以相互调用
    function fn1() {
        console.log(111);
        fn2();
        console.log('fn1');
    }
    function fn2() {
        console.log(222);
        console.log('fn2');
    }
    fn1();
```

### 7. 函数中的两种声明方式

利用函数关键字自定义函数（命名函数）

```js
function fn() {
        
}
fn();
```

函数表达式（匿名函数）

```js
var 变量名 = function() {
    
};
变量名();
```

## 七、JS对象

### 1. 创建对象

#### 字面量创建对象

```js
var obj = {};
```

```js
//1.利用对象字面量创建对象 {}
    var obj = {
        uname: '某某',
        age: 18,
        sex: '男',
        sayHi: function () {
            console.log('Hi');
        }
    }
    //(1)里面的属性或者方法采取键值对的形式      键  属性名 ： 值  属性值
    //(2)多个属性或者方法中间用逗号隔开
    //(3)方法冒号后面跟的是一个匿名函数
    //2.使用对象
    //（1）调用对象的属性  采取  对象名.属性名  中间的小点可以理解为 的
    console.log(obj.uname);
    //（2）调用属性还有一种方法   对象名['属性名']
    console.log(obj['age']);
    //（3）调用对象的方法 sayHi      对象名.方法名()
    obj.sayHi();
```

#### new Object 创建对象

```js
var obj = new Object();
```

```js
//1.利用 new Object 创建对象
    var ibj = new Object();
    ibj.uname = '某某';
    ibj.age = 18;
    ibj.sex = '男';
    ibj.sayHi = function () {
        console.log('Hi');
    }
    //(1)利用等号赋值的方法  添加对象的属性和方法
    //（2）每个属性和方法之间用分号结束
    console.log(ibj.uname);
    console.log(ibj.age);
    ibj.sayHi();
```

#### 构造函数创建对象

构造函数就是把对象里面一些相同的属性和方法抽象出来封装到函数里面

```js
function  构造函数名() {
 		this.属性 = 值;
		this.方法 = function () {}
	}
	new 构造函数名();		//调用
```

##### new 关键字执行过程

> 1.new 构造函数可以在内存中创建一个空的对象
> 2.this 就会指向刚才创建的空对象
> 3.执行构造函数里面的代码 给这个空对象添加属性和方法
> 4.返回这个对象

```js
//1.利用构造函数创建对象
    //  创建四大天王的对象  相同的属性：名字  年龄  性别    相同的方法：唱歌
    //构造函数
    function Star(uname, age, sex) {
        this.name = uname;
        this.age = age;
        this.sex = sex;
        this.sing = function (song) {
            console.log(song);
        }
    }
    //对象
    var ldh = new Star('刘某某', 18, '男');  //  调用函数返回的值是一个对象
    // console.log(typeof ldh);
    console.log(ldh.name);
    console.log(ldh['age']);
    ldh.sing('巴拉');
    var zxy = new Star('张某某', 19, '男');
    console.log(zxy.name);
    console.log(zxy['sex']);
    zxy.sing('春兰');
    //(1)构造函数名字首字母要大写
    //(2)构造函数不需要 return 就可以返回结果
    //(3)调用构造函数  必须使用new
    //(4)只要  new Star() 调用函数就创造
    //(5)属性和方法的前面一定要添加  this
```

### 2. 遍历对象

for...in 语句，用于对数组或者对象的属性进行循环操作

```js
for(变量 in 对象) {}
```

```js
// 遍历对象
    var obj = {
        name: 'pink老师',
        age: 18,
        sex: '男',
        fn:function () {}
    }
    console.log(obj.name);
    console.log(obj.age);
    console.log(obj.sex);
    //for in 遍历对象
    //for(变量 in 对象) {
    // }
    for (var k in obj) {
        console.log(k); // k 变量 输出 得到的是 属性名
        console.log(obj[k]);  // obj[k]得到的是 属性值
    }
    // 使用 for in 里面的变量 一般用 k 或者 key
```

#### 统计遍历对象案例

```js
//判断一个字符串'ascdfgesaxxzsdefqasa'中出现次数最多的字符，并统计其次数
    var str = 'ascdfgesaxxzsdefqasa';
    var o = {};
    for (var i = 0; i < str.length; i++) {
        var chars = str.charAt(i);      //chars是字符串的每一个字符
        //有一个对象 判断是否有该属性  对象['属性名']
        if (o[chars]) {     //o[chars]得到的是属性值
            o[chars]++;
        } else {
            o[chars] = 1;       //这个字符之前没有出现过则赋值1
        }
    }
    console.log(o);
    //遍历对象
    var max = 0;
    var ch = '';
    for (var k in o) {
        //k 得到的是 属性名
        //o[k] 得到的是 属性值
        if (o[k] > max) {
            max = o[k];
            ch = k;
        }
    }
    console.log(max);
    console.log('最多的字符是：' + ch);
```

### 3. Math对象

```js
console.log(Math.max(1,22,42));		//42
```

> Math.PI          //圆周率
> Math.floor()        //向下取整
> Math.ceil()         //向上取整
> Math.round()        //四舍五入  就近取整
> Math.abs()          //绝对值
> Math.max() / Math.min()         //求最大值和最小值
> 随机数方法       Math.random()       返回一个随机的小数       0 =< x < 1

```js
// 若想要得到两个数之间的随机整数 并且 包含这两个整数
   // Math.floor(Math.random() * (max - min + 1)) + min;
   function getRandom(min,max) {
       return Math.floor(Math.random() * (max - min + 1)) + min;    //公式
   }
   console.log(getRandom(1,10));
 
   //随机点名
   var arr = ['张三','李四','赵钱','孙武','刘侯'];
   console.log(arr[getRandom(0,arr.length - 1)]);
```

### 4. 日期对象

```js
var now = new Date();
console.log(now);
```

> getFullYear()       //获取当年
> getMonth()          //获取当月（0-11）
> getDate()           //获取当天日期
> getDay()            //获取星期几（周日0 到周六6）
> getHours()          //获取当前小时
> getMinutes()        //获取当前分钟
> getSeconds()        //获取当前秒
> 获得Date总的毫秒数     通过 valueOf() getTime()

```js
 //毫秒数转换成天、时、分、秒     转换公式
    //d = parseInt(总秒数 / 60 / 60 / 24);   //计算天数
    //h = parseInt(总秒数 / 60 / 60 % 24);   //计算小时
    //m = parseInt(总秒数 / 60 % 60);   //计算分数
    //s = parseInt(总秒数 % 60);   //计算当前秒数
    function countDown(time) {
        var nowTime = +new Date();  // 返回的是当前时间总的毫秒数
        var inputTime = +new Date(time);    // 返回的是用户输入时间总的毫秒数
        var times = (inputTime - nowTime) / 1000;    //time是剩余时间的秒数
        var d = parseInt(times / 60 / 60 / 24); // 天
        var h = parseInt(times / 60 / 60 % 24); // 时
        var m = parseInt(times / 60 % 60);  // 分
        var s = parseInt(times % 60);   // 秒
        return d + '天' + h + '时' + m + '分' + s + '秒';
    }
    console.log(countDown('2022-9-22 20:41:29'));
    var date1 = new Date();
    console.log(date1);
```

### 5. 数组对象

创建数组对象  `var arr = [ ];`  或  `var arr = new Array( );`

检测是否为数组`arr instanceof Array` 或 `Array.isArray(参数值);`

```js
// 检测是否为数组
    //（1）instanceof 运算符 可以用来检测是否为数组
    var arr = [];
    var obj = {};
    console.log(arr instanceof Array);
    console.log(obj instanceof Array);
    //(2)Array.isArray(参数)
    console.log(Array.isArray(arr));
    console.log(Array.isArray(obj));
```

> 添加删除数组元素的方法
> push(参数1...)        末尾添加一个或多个元素，注意修改原数组     并返回新的长度
> pop()            删除数组最后一个元素，把数组长度减1 无参数、修改原数组       返回它删除的元素的值
> unshift(参数1...)     向数组的开头添加一个或更多元素，注意修改原数组     并返回新的长度
> shift()         删除数组的第一个元素，数组长度减1 无参数、修改原数组     并返回第一个元素的值

```js
//添加删除数组元素的方法
    //1.push() 在数组的末尾 添加一个或者多个数组元素
    var arr = [1,2,3];
    arr.push(4,'bala');     //返回值是新数组的长度
    console.log(arr);
    //2.unshift() 在数组的开头 添加一个或者多个数组
    arr.unshift('red',5);       //返回值是新数组的长度
    console.log(arr);
    //3.pop() 可以删除数组的最后一个元素
    arr.pop();      //不跟参数      返回值是删除的那个元素
    console.log(arr);
    //4.shift() 可以删除数组第一个元素
    arr.shift();        //不跟参数      返回值是删除的那个元素
    console.log(arr);
```

翻转数组 `reverse( )` 		例如：`arr.reverse( );` 

```js
var arr1 = ['red','pink','green'];
    arr1.reverse();
    console.log(arr1);
```

冒泡排序 `sort( )` 		例如：`arr.sort(function(a,b) { return a - b; });`

```js
var arr2 = [12,6,4,25,7,1];
    arr2.sort(function (a,b) {
        return a - b;  //升序的顺序排列        b - a 则为降序的顺序排列
    });
    console.log(arr2);
```

返回数组索引号 `indexOf( )` 和 `lastIndexOf( )` 

```js
//它只返回第一个满足条件的索引号     如果在数组中找不到元素则返回 -1
    var arr3 = ['red','pink','blue','green','purple'];
    console.log(arr3.indexOf('green'));
    console.log(arr3.lastIndexOf('green'));
```

数组转换为字符串

`toString( )` 把数组转换为字符串，逗号分隔每一项

`join('分隔符')` 把数组中的所有元素转换为一个字符串

```js
//1.toString() 将数组转换为字符串
    var arr4 = [1,2,3,4];
    console.log(arr4.toString()); //1,2,3
    //2.join('分隔符')
    var arr5 = ['green',2,34,4];
    console.log(arr5.join('-'));    //green-2-34-4
```

> concat()    连接两个或多个数组 不影响原数组        返回一个新的数组
> slice()     数组截取slice(begin,end)            返回被截取项目的新数组
> splice()    数组删除splice(第几个开始，要删除个数)     返回被删除项目的新数组，这个会影响原数组

#### 数组去重案例

```js
//数组去重['a','d','d','s','a','x','z','s','d','x','c']
    function unique(arr) {
        var newArr = [];
        for (var i = 0; i < arr.length; i++) {
            if (newArr.indexOf(arr[i]) === -1) {
                newArr.push(arr[i]);
            }
        }
        return newArr;
    }
    var demo = unique(['a','d','d','s','a','x','z','s','d','x','c'])
    console.log(demo);
```

### 6. 字符串对象

根据字符返回位置

> indexOf('要查找的字符',开始的位置) 
>
> lastindexOf('要查找的字符',开始的位置)

```js
//查找字符串‘bcoedoalxmsopp'中所有o出现的位置及次数
    var str = "bcoedoalxmsopp";
    var index = str.indexOf('o');
    var num = 0;
    while(index !== -1) {
        console.log(index);
        num++;
        index = str.indexOf('o',index + 1);
    }
    console.log('o出现的次数是' + num);
```

根据位置返回字符

> charAt(index)           返回指定位置的字符（index索引号）     str.charAt(0)
> charCodeAt(index)       获取指定位置字符的ASCII码             str.charCodeAt(0)
> str[index]              获取指定位置处字符                   和charAt()等效

```js
//1.charAt(index) 根据位置返回字符
    var str1 = 'andy';
    console.log(str1.charAt(3));
    //遍历所有的字符
    for (var i = 0; i < str1.length; i++) {
        console.log(str1.charAt(i));
    }
    //2.charCodeAt(index) 返回相应索引号的字符ASCII值 目的： 判断用户按下了哪个键
    console.log(str1.charCodeAt(0));  //97
    //3.str[index]  H5新增的
    console.log(str[0]);  //a
```

字符串操作方法

> concat(str1,str2,str3...)   concat()方法用于连接两个或多个字符串 等效于+，+更常用
> substr(start,length)        从start位置开始（索引号），length取的个数
> slice(start,end)            从start位置开始，截取到end位置，end取不到
> substring(start,end)        与slice基本相同，但是不接受负值

```js
//1.concat('字符串1','字符串2'...)
    var str = 'andy';
    console.log(str.concat('red'));
//2.substr('街区的起始位置','截取几个字符');
    var str1 = 'asdfghj';
    console.log(str1.substr(2, 2));      //第一个2是索引号开始，第二个2是截取数量, substr已弃用

//3.替换字符 replace('被替换的字符','替换为的字符')
    var str2 = 'andycat';
    console.log(str.replace('a', 'b'));      //只会替换第一个字符
    //有一个字符串'acsdcazxvfgekmahuiag' 要求把里面所有的 o 替换为 *
    var str3 = 'acsdcazxvfgekmahuiag';
    while (str3.indexOf('a') !== -1) {
        str3 = str3.replace('a', '*');
    }
    console.log(str3);
//4.字符转换为数组 split('分隔符')        join把数组转换为字符串
    var str4 = 'red, pink, blue';
    console.log(str4.split(','));
    var str5 = 'red&pink&blue';
    console.log(str5.split('&'));       //''中的字符取决于定义中的字符
```

