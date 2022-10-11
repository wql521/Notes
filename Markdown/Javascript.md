# JavaScript基本语法

## 定义变量

使用var 关键字来声明变量，如果省略 var关键字，那么该变量默认成为全局变量

```javascript
var x = 1;
```

一条语句的结束以分号结束.

```javascript
var x = 2; 
var y = 1;
if(X > y){
            x = 3;
            y = 2;
}
```

语句块是一组语句的集合,使用{...}形成一个块 block。例如，下面的代码先做了一个判断,如果判断成立，将执行{….}中的所有语句.

JavaScript是弱类型的编程语言，**声明变量的时候都是使用关键字var**，没有int、char之说，为变量赋值时会自动判断类型并进行转换。变量名是大小写英文、数字、“$”和“_”的组合，且不能用数字开头。变量名也不能是JavaScript的关键字，如 if、while等。申明一个变量用var语句，比如: var s_007 = '007'。

## 数据类型

### Number类型（number）

包含整数和浮点数

### 字符串类型（string）

字符串是以单引号或双引号括起来的任意文本，比如'abc',"xyz"等。

### 布尔值类型（boolean）

一个布尔值只有true、false两种值。

### undefined类型（undefined）

只有一个取值，就是undefined，表示没有值的意思

### null类型（null）

只有一个取值，就是null，表示空的意思

### 数组类型

数组是一组按顺序排列的集合,集合的每个值称为元素。JavaScript 的数组可以包括任意数据类型，示例如下: var array = [1,2,3.14, 'Hello', null, true]。上述数组包含6个元素。数组用[]表示，元素之间用“,”分隔。另一种创建数组的方法是通过Array()函数实现，示例如下: var array = new Array(1,2,3)。数组的元素可以通过索引来访问,索引的起始值为0。

### 对象类型（object）

 javaScript的对象是一组由键-值组成的无序集合，类似Python中的字典。示例如下:var person = {name: 'qiye',age: 24,tags: ['python', 'web' , 'hacker'J.city: 'Beijing',man:true} 。JavaScript 对象的键都是字符串类型，值可以是任意数据类型。要获取一个对象的属性，我们用“对象变量.属性名”的方式，如person. name。

## 运算符和操作符

### 算术运算符

#### +加法运算

只有符号两边都是数字的时候，才会进行加法运算
只要符号任意一边是字符串，就会进行字符串的拼接

#### -减法

会执行减法运算
会自动把两边都转换成数字进行运算

#### *乘法
会执行乘法运算
会自动把两边都转换成数字进行运算
#### / 除法
会执行除法运算
会自动的两边都转换成数字进行运算

#### % 求余
会执行取余运算
会自动把两边都转换成数字进行运算

### 赋值运算

#### =

就是把 `=` 右边的值 赋值给 `=` 左边的变量名

```javascript
var num = 100；
```

#### +=

```javascript
    var age = 18;
    a += 10;
    console.log(a) // 28
```

`a += 10` 等价于 `a = a + 10`

#### -=

```javascript
    var a = 10;
    a -= 10;
    console.log(a); //=> 0
```

a -= 10` 等价于 `a = a - 10

#### *=

```javascript
    var a = 10;
    a *= 10;
    console.log(a); //=> 100
```

`a /= 10` 等价于 `a = a / 10`

#### %=

```javascript
    var a = 10;
    a %= 10;
    console.log(a); //=> 0
```

`a %= 10` 等价于 `a = a % 10`

### 关系运算符

#### ==

比较符号两边的值是否相等，不管数据类型
1 == '1' 
两个值是一样的，所以得到true
#### === 全等

比较符号两边的值和数据类型是否相等
1 ===  '1'
两个值虽然一样，但是因为因为值得数据类型不一样，所以为false
#### !=

比较符号 两边的值是否 不等
1 != '1'
因为两边的值是相等的，所以在比较的他们不等的时候得到false
#### !== 不全等

比较符号两边的值和类型是否不等
1 != '1' true
因为量的数据类型不一样，所以得到true

#### >=

比较左边的值是否 大于或等于 右边的值
1 >= 1 true
1 >= 0 true
1 >= 2 false
#### <=

比较左边的值是否 小于或等于 右边的值
1 <= 2 true
1 <= 1 true
1 <= 0 false

#### >

比较左边的值是否 大于 右边的值
1 > 0 true
1 > 1 false
1 > 2 false
#### <

比较左边的值是否 小于 右边的值
1 < 2 true
1 < 1 false
1 < 0 false
### 逻辑运算符

#### &&
进行 且 的运算
符号左边必须为 true 并且右边也是 true，才会返回 true
只要有一边不是 true，那么就会返回 false
true && true true
true && false false
false && true false
false && false false

#### ||
进行 或 的运算
符号的左边为 true 或者右边为 true，都会返回 true
只有两边都是 false 的时候才会返回 false
true || true true
true || false true
false || true true
false || false false

#### !

进行 取反 运算
本身是 true 的，会变成 false
本身是 false 的，会变成 true
!true false
!false true

### 自增自减运算（一元运算符）

#### ++

- 进行自增运算
- 分成两种，**前置`++`** 和 **后置`++`**
- 前置++，会先把值自动 +1，在返回

```javascript
var a = 10;
console.log(++a);
// 会返回 11，并且把 a 的值变成 11

var num = 10;
num++
console.log(num)
// 会返回 11，并且把 a 的值变成 11
```

- 后置`++`，会先把值返回，在自动`+1`

```javascript
var a = 10;
console.log(a++);
// 会返回 10，然后把 a 的值变成 11
```

#### -

- 进行自减运算
- 分成两种，**前置–** 和 **后置–**
- 和 `++` 运算符道理一样

## 条件判断

if(){...}else{...}进行判断,例如

```javascript
var role = 20;
if(age >= 18){
    alert ( 'adult ' ) ;} 
else {
    alert ( 'teenager ' ) ;
}
```

## 循环

分for循环和while循环

for循环---计算1到100相加之和

```javascript
var x = 0;
var i;
for (i=1; i<=100 ; i++){
x = x + i;
}
```

for循环用来遍历数组, for循环还有一个变体是for...in循环，它可以把一个对象的所有属性依次循环出来,示例如下:

```javascript
var person = {
name: 'aiye',
age: 20，
city : 'Beijing'
} ;
for ( var key in person ) {
    alert (key) ; //'name ' , 'age ' , 'city '
}
```

while循环,分为while(){...},循环和do{ ...}while()

## 函数

在 JavaScript中，定义函数使用function关键字，使用方式如下

```javascript
function add (x,y) {
    return x+y;
}
```

上述add()函数的定义如下:
·function指出这是一个函数定义;

·add是函数的名称。
·(x,y)括号内列出函数的参数，多个参数以“,”分隔。
·{...}之间的代码是函数体，可以包含若干语句,甚至可以没有任何语句。调用函数时，按顺序传入参数即可: add(10,9);//返回19。
由于JavaScript 允许传入任意个参数而不影响调用，因此传入的参数比定义的参数多也没有问题,虽然函数内部并不需要这些参数: add(10,9,'blablabla'); //返回19。
传入的参数比定义的少也没有问题:add();//返回 NaN。此时add(x,y)函数的参数x和y收到的值为undefined，计算结果为NaN。

## 控制输出

### 1. 输出到页面：document.write()

### 2. 弹窗框显示：alert()

### 3. 控制台输出：console.log()

## 判断数据类型的关键字

### isNaN 关键字

isNAN可以判断一个变量是不是数

```javascript
// 如果变量是一个数字
var n1 = 100;
console.log(isNaN(n1)); //=> false

// 如果变量不是一个数字
var s1 = 'Jack'
console.log(isNaN(s1)); //=> true
```

### typeof 关键字

JavaScript有分数据类型，那么我们有时候需要知道我们存储的数据是什么类型的数据，
使用 typeof 关键字来进行判断
**语法：** typeof 变量

```javascript
/* 多种类型的变量 */
var age = 18; 
var name=" "; 
var isFun = true; 
var a;

console.log(typeof age);    //number
console.log(typeof name);   //string
console.log(typeof a);      //undefined
console.log(typeof isFun);  //boolean
```

## 数据类型的转换

在JavaScript的基本数据类型中，字符串、数值以及其他类型之间是可以相互转换的，而这种转换又可以分为两种。一种是在进行算数是默认会执行的 自动转换，其二就是 强制转换

数据类型之间的强制转换：

### 1.Number（变量）

==将其他的数据类型转化为数值类型==
可以把一个变量强制转化为数值类型
可以转换成小数，胡保留小数
可以转换布尔值
遇到不可转换的都会返回NAN

### 2.parseInt（变量）

==将其他的数据类型转化为数值类型==
从第一位开始检查，是数字就转换，直到一个不是数字内容
开头不是数值，那么久直接转换为NAN
**不认识小数点，只能保留小数点**

### 3.parseFloat（变量）

==将其他的数据类型转化为数值类型==
从第一个开始检查，是数字就转换，直到一个不是数字的内容
开头就不是数字，那么直接返回NAN
**认识一次小数点**

### 4.变量.toString()

==将其他的数据类型转化为字符串类型==
有一些数据类型不能使用toString()方法，比如undefined 和null

### 5.String（变量）

==将其他的数据类型转化为字符串类型==
所有数据类型都可以

### 6.Boolean(变量)

==将其他数据类型转换为布尔类型==
在js中，只有’’,0,null,undefined,NaN，这些为false

# JavaScript和Html联系

## 行内式js代码

直接在标签上写js代码，需要依靠事件（行为）来触发

```javascript
<!-- 写在 a 标签的 href 属性上 -->
<a href="javascript:alert('我是一个弹出层');">点击一下试试</a>
<!-- 写在其他元素上 -->
<div οnclick="alert('我是一个弹出层')">点一下试试看</div>

<!-- 
	注：onclick 是一个事件（点击事件），当点击元素的时候执行后面的 js 代码
-->
```

## 内嵌式js代码

在HTML页面中创建script标签，并且在script标签中直接编写JavaScript代码即可（js代码会在页面打开的时候直接触发执行）

```javascript
<!-- 在 html 页面书写一个 script 标签，标签内部书写 js 代码 -->
<script type="text/javascript">
	alert('我是一个弹出层')
</script>

<!-- 
	注：script 标签可以放在 head 里面也可以放在 body 里面
-->
```

## 外链式js代码

在HTML页面中创建一个script标签，把JavaScript代码单独保存在 .js后缀的文件中，然后通过设置script标签的src属性来引入外部的js文件

```javascript
// 我是 index.js 文件
alert('我是一个弹出层')
```

```html
<!-- 我是一个 html 文件 -->

<!-- 通过 script 标签的 src 属性，把写好的 js 文件引入页面 -->
<script src="index.js"></script>

<!-- 一个页面可以引入多个 js 文件 -->
<script src="index1.js"></script>
<script src="index2.js"></script>
<script src="index3.js"></script>
```

