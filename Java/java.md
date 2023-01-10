# Java

## Hello World

```java
public class helloworld {
  //main方法,表示程序的主入口
    public static void main(String[] args) {
      //输出语句,把小括号里面的内容进行输出打印
        System.out.println("Hello World!");
    }
}
```

> 编译: javac是JDK提供的编译工具,激昂Java文件编译成class文件**需要带后缀**
>
> 运行: 运行代码,运行编译后的class文件**不带后缀**

## 基础

### 注释

**单行注释: `//注释信息`**

**多行注释: `/*注释信息*/ `**

文档注释: `/**注释信息*/`

### 关键字

> **关键字**:被java赋予特定含义的英文单词
>
> **关键字的字母全部小写**

  #### class

**class**:用于(创建/定义)一个类,后面跟随类名.

> 类是java最基本的组成单元

### 字面量

| 字面量类型 |                说明                 |         例子          |
| :--------: | :---------------------------------: | :-------------------: |
|  整数类型  |          不带小数点的数字           |        666,-88        |
|  小数类型  |           带小数点的数字            |         13.14         |
| 字符串类型 |        用双引号括起来的内容         |     "hello world"     |
|  字符类型  | 用单引号括起来的内容,内容只能有一个 |        'A','0'        |
|  布尔类型  |           布尔值,表示真假           | 只有两个值:true,false |
|   空类型   |          一个特殊的值,空值          |       值是:null       |
|            |                                     |                       |

```java
public class ValueDemo1 {
    public static void main(String[] args) {
      //整数
        System.out.println(666);
      	System.out.println(-666);
      //小数
      	System.out.println(1.3);
      	System.out.println(-1.4);
      //字符串
      	System.out.println("尘世烟雨客");
      //字符
        System.out.println('男');
      //布尔
        System.out.println(true);
      	System.out.println(false);
      //空
      //null不能直接打印
      
    }
}
```

#### 特殊字符

##### \t 制表符

在打印的时候,把前面字符串的长度补齐大8,或者8的整数倍.最少补一个空格,最多补8个空格.

```java
public class helloworld {
  public static void main(String[] args){
    System.out.println("name"+'\t'+"age");
    System.out.println("Tom"+'\t'+"23");
  }
}
```

> 输出结果: 
>
> ```
> name    age
> Tom     23
> ```

 ##### \n

##### \r

### 变量

> 在程序的执行过程中,其值有可能发生改变的量(数据)

#### 变量的定义格式

**数据类型 变量名 = 数据值;**

> 数据类型:为空间·中存储的数据,加入类型限制(整数,小数,....)

| 数据类型 | 关键字 |
| :------: | :----: |
|   整数   |  int   |
|  浮点数  | double |
|          |        |

```java
public class VarableDemo{
  //主入口
  public static void main(String[] args){
    //定义变量
    int a = 10;
    System.out.println(a);
  }
}
```

#### 变量的计算

```java
public class VarableDemo{
  //主入口
  public static void main(String[] args){
    //定义变量
    int a = 10;
    int b = 20;
    System.out.println(a+b);
  }
}
```



#### 修改变量的值

```java
public class VarableDemo{
  //主入口
  public static void main(String[] args){
    //定义变量
    int a = 10;
    System.out.println(a);//10
    //修改变量的值
    a = 20;
    System.out.println(a);//20 
  }
}
```

#### 变量的注意事项

> 1. 只能存一个值
> 2. 变量名不允许重复定义
> 3. 一条语句可以定义多个变量,**用逗号分隔**
> 4. 变量在使用之前一定要进行赋值(**初始化变量**)
> 5. 变量的作用域范围

#### 变量的练习

```java
public class Variabletest{
  //主入口
  public static void main(String[] args){
    //一开始没有乘客
    int a = 0;
    //第一站:上去一名乘客
    a=a+1;
    //第二站:上去两名乘客,下来一名乘客
    a=a+2-1;
    //第三站:上去两名乘客,下来一名乘客
    a=a+2-1;
    //第四站:下来一名乘客
    a=a-1;
    //第五站:上去一名乘客
    a=a+1;
    //请问:终点站,车上还有几名乘客?
    System.out.println(a);
  }
}
```

## 数据类型

### 基本数据类型

> 数据是存储在自己的空间中
>
> 特点:赋值给其他变量,也是赋的真实的值

| 数据类型 | 关键字  |           取值范围            |
| :------: | :-----: | :---------------------------: |
|   整数   |  byte   |           -128~127            |
|          |  short  |         -32768~32767          |
|          |   int   |    -2147483648~2147483647     |
|          |  long   |           (19位数)            |
|  浮点数  |  float  |  -3.401298e-38~3.402823e+38   |
|          | double  | -4.9000000e-324~1.797693e+308 |
|   字符   |  char   |            0-65535            |
|   布尔   | boolean |          true,false           |
|          |         |                               |

> **定义long类型的变量**,在数据值的后面需要加一个**L**作为后缀(L可以大写也可以小写)
>
> **定义float类型的变量**在数据值的后面需要加一个**F**作为后缀(大小写都可以)
>
> 整数和小数取值范围大小关系:
>
> double>float>long>int>short>byte

#### 小练习

```java
public class Variabletest{
  public static void main(String[] args){
    //定义变量记录姓名
    String name = "尘世烟雨";
    //定义变量记录年龄
    int age = 18;
    //定义变量记录性别
    char gender = '男';
    //定义变量记录身高
    double height = 180.1;
    //定义变量记录是否单身
    //true为单身 flase为不单身
    boolean flag = true;
    
    //打印
    System.out.println(name);
    System.out.println(age);
    System.out.println(gender);
    System.out.println(height);
    System.out.println(flag);
    
  }
}
```





### 引用数据类型

> 数据值是存储在其他空间中
>
> 自己空间中存储的是地址值
>
> 特点: 赋值给其他变量,赋的**地址值**
>
> 使用其他空间的数据

### 标识符

> 标识符: 给类、方法、变量等起的名字

1. 由数字、字母、下划线和美元符组成
2. 不能以数字开头
3. 不能是关键字
4. 区分大小写

## 键盘录入

**Scanner类,可以接收键盘输入的数字**

步骤一:导包

`import java.util.Scanner;`

> 导包的动作必须出现在**类定义的上边**

步骤二:创建对象

```java
Scanner sc = new Scanner(System.in);
//上面这个格式里面,只有sc是变量名,可以变,其他都不允许改变.
```

步骤三:接收数据

```java
int i = sc.nextInt();
//上面这个格式里面,只有i是变量名,可以变,其他不允许改变.
```

### 例子

```java
//1.导包,找到Scanner这个类在哪
//写在类定义的上面
import java.util.Scanner;

public class ScannerDemo{
  public static void main(String[] args){
    //2.创建对象,表示现在准备用Scanner这个类
    Scanner sc = new Scanner(System.in);
    System.out.println("请输入整数:");
    //3.接收数据
    //变量i记录了键盘录入的数据
    int i = sc.nextInt();
    
    //打印输出
    System.out.println(i);
  }
}
```

## 运算符

### 运算符和表达式

#### 运算符

> 对字面量或者变量进行操作的符号

#### 表达式

> 用**运算符**把字面量或者变量连接起来,**符合java语法的式子**就可以称为表达式.
>
> 不同运算符连接的表达式体现的是不同类型的表达式

### 算术运算符

| 符号 | 作用 |
| :--: | :--: |
|  +   |  加  |
|  -   |  减  |
|  *   |  乘  |
|  /   |  除  |
|  %   | 取余 |
|      |      |

> **加减乘**
>
> 1.如果小数参与计算,结果有可能不精确
>
> 例子:
>
> 3+2  结果5
>
> 5-1  结果4
>
> 7*9  结果63
>
> 1.1+1.1  结果2.2
>
> 1.1+1.01  结果2.1100000000003
>
> **除/**
>
> **1.整数参与计算,结果只能得到整数**
>
> 2.小数参与计算,结果有可能是不精确的
>
> 例子:
>
> 10/2  结果5
>
> **10/3  结果3**
>
> 10.0/3  结果3.33333....

#### 例子

```java
import java.util.Scanner;
public class test{
  public static void main(String[] args){
    //键盘输入一个三位数,获取其中的个位,十位,百位
    
    //1.键盘输入
    Scanner sc = new Scanner(System.in);
    System.out.println("请输入一个三位数:");
    int number = sc.nextInt();
    
    //获取个位,十位,百位
    //个位  数字 % 10
    //十位  数字 /10 % 10
    //百位  数字 /100 % 10
    int ge = number % 10;
    int shi = number / 10 % 10;
    int bai = number / 100 % 10;
    
    //打印输出
    System.out.println(ge);
    System.out.println(shi);
    System.out.println(bai);
  }
}
```

**数字进行运算时,数据类型不一样不能运算,需要转成一样的,才能运算**

#### 隐式转换

把一个取值范围小的数值,转换成取值范围大的数据

```java
int a = 10;
double b = a;
```

##### 隐式转换的两种提升规则

1.取值范围小的,和取值范围大的进行运算,小的会先提升为大的,再进行运算.

2.**byte、short、char**三种类型的数据在运算的时候,都会先提升为int,然后再进行运算

>整数和小数取值范围大小关系:
>
>double>float>long>int>short>byte

 #### 强制转换

1.如果把一个**取值范围大**的数值,赋值给**取值范围小**的变量.不允许直接赋值,需要强制转换.

2.格式: **目标数据类型 变量名 = (目标数据类型)被强制的数据;**

```java
double a = 123;
int b = (int)a;
```

#### 字符串的“+”操作

1.当“+”操作中出现字符串时,这个“+”是字符串连接符,而不是算术运算符.会将前后的数据进行**拼接**,并产生一个新的字符串.

> "123"+123
>
> 结果:
>
> "123123"

2.连接进行“+”操作时,**从左到右逐个执行**

>1+99+"尘世烟雨"
>
>结果:
>
>"100尘世烟雨"

```java
int age = 18;
System.out.println("我的年龄是"+age+'岁'); //"我的年龄是18岁"
System.out.println("我的年龄是"+"age"+'岁'); //"我的年龄是age岁"
```

#### 字符的+操作

> 当**字符+字符或者字符+数字**时,会把字符通过ASCII码表查询到对应的数字再进行计算

#### 自增自减运算符

| 符号 | 作用 |    说明     |
| :--: | :--: | :---------: |
|  ++  |  加  | 变量的值加1 |
|  --  |  减  | 变量的值减1 |
|      |      |             |

> ++和--既可以放在变量的前边,也可以放在变量的后边

```java
int a = 10;
a++;
System.out.println(a);//11
++a;
System.out.println(a);//12
a--;
System.out.println(a);//11
--a;
System.out.println(a);//10
```

##### 参与计算

1.先用后加

```java
int a = 10;
int b = a++;//先把a变量的值拿出来用,赋值给b,然后再进行自增
System.out.println(b);//10
```

2.先加后用

```java
int a = 10;
int b = ++a;//先把a进行自增,然后再把自增后的结果赋值给b变量
System.out.println(b);//11
```

### 赋值运算符

| 符号 |    作用    |          说明          |
| :--: | :--------: | :--------------------: |
|  =   |    赋值    | int a = 10;将10赋值给a |
|  +=  |  加后赋值  |      将a+b的值给a      |
|  -=  |  减后赋值  |      将a-b的值给a      |
|  *=  |  乘后赋值  |      将a*b的值给a      |
|  /=  |  除后赋值  |     将a除b的商给a      |
|  %=  | 取余后赋值 |    将a除b的余数给a     |
|      |            |                        |

> +=、-=、*=、/=、%=赋值隐藏了一个强制类型转换
>
> ```java
> int a = 10;
> int b = 20;
> a += b; //等同于a=(int)(a+b)
> 
> short s = 1;
> s += 1; //等同于s=(short)(s+1)
> ```
>
> **赋值后的数据类型同左边一样**

### 关系运算符

| 符号 |                         说明                         |
| :--: | :--------------------------------------------------: |
|  ==  |  a==b,判断a和b的值是否相等,成立为true,不成立为false  |
|  !=  | a!=b,判断a和b的值是否不相等,成立为true,不成立为false |
|  >   |     a>b,判断a是否大于b,成立为true,不成立为false      |
|  >=  |   a>=b,判断a是否大于等于b,成立为true,不成立为false   |
|  <   |     a<b,判断a是否小于b,成立为true,不成立为false      |
|  <=  |   a<=b,判断a是否小于等于b,成立为true,不成立为false   |
|      |                                                      |

> 关系运算符的结果都是boolean类型

#### 练习

```java
import java.util.Scanner;
  public class test{
    public static void main(String[] args){
      /*键盘输入两个整数
        分别表示你和对象的时髦度(在0-10范围内)
        如果你的时髦度大于你对象的时髦度,表示相亲成功
        成功为true,失败为false*/
      Scanner sc = new Scanner(System.in);
      System.out.println("请输入你的时髦度:");
      int myfashion = sc.nextInt();
      System.out.println("请输入对象的时髦度:");
      int girlfashion = sc.nextInt();
      
      boolean result = myfashion > girlfashion;
      
      System.out.println(result);
    }
  }
```

### 逻辑运算符

| 符号 |    作用    |            说明            |
| :--: | :--------: | :------------------------: |
|  &   | 逻辑与(且) | 并且,两边都为真,结果才是真 |
|  \|  |   逻辑或   | 或者,两边都为假,结果才为假 |
|  ^   |  逻辑异或  |   相同为false,不同为true   |
|  !   |   逻辑非   |            取反            |
|      |            |                            |

> & **两边都要满足**
>
> | **两边满足一个**

#### 短路逻辑运算符

> 例子-登陆:
>
> &会判断两次,判断用户名是否正确和判断密码是否正确,如果用户名错误依然还会继续判断密码
>
> &&与上面区别:如果用户名判断错误,不会继续判断密码
>
> 例子-相亲(成功需要有房子或者车子)
>
> | 如果有房子,还会继续去判断是否有车子
>
> || 如果有房子,不需要继续去看车子

| 符号 | 作用   | 说明                        |
| ---- | ------ | --------------------------- |
| &&   | 短路与 | 结果和&相同,但是短路效果    |
| \|\| | 短路或 | 结果和\|相同,但是有短路效果 |
|      |        |                             |

> |,&  无论左边true,false,右边都要执行.
>
> ||,&&  如果**左边能确定整个表达式的结果**,**右边不执行**

##### &&

左边为false,右边不管是真还是假,整个表达式的结果一定是false

##### ||

左边为true,右边不管是真还是假,整个表达式的结果一定是true

```java
import java.util.Scanner;
  public class test{
    public static void main(String[] args){
      /*键盘录入两个整数
        如果其中一个数是6,最终结果输出为true
        如果两个数相加是6的倍数,最终输出结果为true*/
      
      //1.键盘录入两个整数
      Scanner sc = new Scanner(System.in);
      System.out.println("请输入第一个整数");
      int number1 = sc.nextInt();
      System.out.println("请输入第二个整数");
      int number2 = sc.nextInt();
      
      //2.number1==6 || number2==6||(number1+number2)%6==0满足其中一个输出为true
      boolean result = number1==6 || number2==6 ||(number1+number2)%6==0;
      System.out.println(result);
    }
  }
```

### 三元运算符

#### 格式

**关系表达式 ? 表达式1:表达式2**

> 关系表达式成立则运行表达式1,否则运行表达式2

```java
import java.util.Scanner;
  public class maxDemo{
    public static void main(String[] args){
      //键盘录入两个整数,获取最大值
      //判断两个整数是否相同,相同输出字符串相同
      
      //1.键盘录入两个整数
      Scanner sc = new Scanner(System.in);
      System.out.println("请输入第一个整数");
      int number1 = sc.nextInt();
      System.out.println("请输入第二个整数");
      int number2 = sc.nextInt();
      
      //2.使用三元表达式获取最大值
      //关系表达式 ? 表达式1:表达式2
      //整个三元表达式的结果必须被使用
      int max = number1>number2 ? number1:number2;
      System.out.println(max);
      
      //3.判断是否相同
      String result = number1==number2 ? "相同":"不同";
      System.out.println(result);
    }
  }
```

## 流程控制语句

### 顺序结构

数序结构语句是java程序默认的执行流程,按照代码的先后顺序,从上到下依次执行

### 分支结构

#### if语句

##### 第一种格式:

```java
if (关系表达式) {
  语句体;
}
```

> 如果对一个布尔类型的变量进行判断,不要用==号,直接把变量名写在小括号即可

##### 第二种格式:

```java
if (关系表达式) {
  语句体1;
} else {
  语句体2;
}
```

##### 第三种格式

```java
if (关系表达式1) {
  语句体1;
} else if (关系表达式2) {
  语句体2;
} else if (关系表达式3) {
  语句体3;
}
.....
 	else {
    语句体n+1;
  }
```

####  switch语句

```java
switch(表达式){
  case 值1:
    语句体1;
    break;
  case 值2:
    语句体2;
    break;
    ...
  default:
    语句体n+1;
    break;
    
}
```

> **执行流程:**
>
> 1. 首先计算表达式的**值**
> 2. 依次和case后面的值进行比较,如果有对应的值,就会执行相应的语句,在执行的过程中,遇到break就会结束.
> 3. 如果没有发现break,那么程序就会继续执行下一个case语句体,一直遇到break或者打括号为止.
> 4. 如果所有的case后面的值和表达式的值都不匹配,就会执行default里面的语句体,然后结束整个switch语句.

> **注意⚠️**
>
> 1. case后面的值只能是**字面量**,不能是变量
> 2. case给出的值不允许重复
> 3. case:后面跟的是要和表达式进行比较的值(被匹配的值,取值为byte,short,int,char,枚举,String)

```java
public class switchDemo{
   public static void main(String[] args){
      //兰州拉面、武汉热干面、北京炸酱面、陕西油泼面
     //1.定义变量,记录想要吃的面条
     String noodle = "兰州拉面";
     
     //2.将上面记录的变量利用switch语句进行匹配
     switch(noodle){
       case "兰州拉面":
         System.out.println("吃兰州拉面");
         break;
       case "武汉热干面":
         System.out.println("吃武汉热干面");
         break;
       case "北京炸酱面":
         System.out.println("吃北京炸酱面");
         break;
       case "陕西油泼面":
         System.out.println("吃陕西油泼面");
         break;
       default:
         System.out.println("吃泡面");
         break;
     }
      
   }
}
```



##### 新格式

```java
public class numberDemo{
  public static void main(String[] args){
    int number = 1;
    switch (number){
        case 1 -> {
          System.out.println('一');
        }
        case 2 -> {
          System.out.println('二');
        }
        case 3 -> {
          System.out.println('三');
        }
        default -> {
          System.out.println("没有选项");
      }
    }
  }
}
```

**case语句后面的打括号里如果只有一条语句,打括号可以删除**

##### case穿透

```java
import java.util.Scanner
public class numberDemo{
  public static void main(String[] args){
    /*键盘录入星期数,输出工作日、休息日
      (1-5)工作日,(6-7)休息日*/
    //1.键盘录入星期数
    Scanner sc = new Scanner(System.in);
    System.out.println("请录入一个整数表示星期:");
    int week = sc.nextInt();
    //2.利用switch语句表示选择
    switch(week){
      case 1,2,3,4,5 -> System.out.println("工作日");
      case 6,7 -> System.out.println("休息日");
      default -> System.out.println("没有这个星期");
    }
    
  }
}
```

### 循环结构

#### for循环

```java
for (初始化语句;条件判断语句;条件控制语句){
  循环体语句;
}
```

> **执行流程:**
>
> 1. 执行初始化语句
> 2. 执行条件判断语句,看其结果是true还是false. 如果是false,循环结束.如果是true,执行循环体语句.
> 3. 执行条件控制语句
> 4. 回到 2 继续执行条件判断语句

> 注意⚠️
>
> 1. 初始化语句只执行一次
> 2. 判断语句为true,循环继续
> 3. 判断语句为false.循环结束

```java
public class forDemo {
    public static void main(String[] args) {
        for (int i = 1;i <= 10;i++) {
        //打印10次hello world
            System.out.println("hello world");
        }
    }
}

```

##### 练习

```java
public class forDemo {
    public static void main(String[] args) {
        /*for (初始化语句;条件判断语句;条件控制语句){
                循环体语句;
          }*/
        //打印输出1-5
        for (int i = 1;i <= 5;i++) {
            System.out.println(i);
        }
        System.out.println("---------------");
        //打印输出5-1
        for (int x = 5;x >= 1;x--){
            System.out.println(x);
        }
    }
}
```

##### 累加

```java
public class addDemo {
    public static void main(String[] args) {
        //求1-5的和

        //分析
        //1.循环1-5里面的每一个数字
        //开始条件:1
        //结束条件:5
        int sum = 0; //用来进行累加
        for (int i = 1;i <= 5;i++){
            System.out.println(i);
            sum += i;
        }
        //打印累加结果
        System.out.println(sum);
    }
}
```

```java
public class addDemo2 {
    public static void main(String[] args) {
      //求1-100之间的偶数和
      //定义结果变量
      int sum = 0;
      //1.获取1-100之间的每个数
      for (int i = 1;i <= 100;i++){
        //2.累加求和(先判断,在求和)
        if (i % 2 ==0){
          sum += i;
        }
      }
      System.out.println(sum)
        
    }
}
```

```java
import java.util.Scanner;

public class test8 {
    public static void main(String[] args) {
        /*键盘录入两个整数，表示一个范围
        * 统计这个范围里既能被3整除，又能被5整除的数字有多少？*/

        //1.键盘录入两个整数
        Scanner sc = new Scanner(System.in);
        System.out.println("请输入一个数字表示范围的开始");
        int start = sc.nextInt();
        System.out.println("请输入一个数字表示范围的结束");
        int end = sc.nextInt();
        //定义一个变量记录个数
        int count = 0;
        //2.利用循环获取范围里的每一个整数
        //开始是start
        //结束是end
        for (int i = start;i <=end;i++){
            //3.对每个数字进行判断
            if (i % 3 ==0 && i % 5 ==0){
                count++;
            }
        }
        //打印输出结果
        System.out.println("既能被3整除，又能被5整除的数字有"+count+'个');
    }
}

```

#### while循环

##### 格式

```java
初始化语句;
while(条件判断语句){
  循环体语句;
  条件控制语句;
}
```

```java
public class whileDemo1 {
    public static void main(String[] args) {
        //利用while循环打印1-100
        /*
        * 初始化语句;
          while(条件判断语句){
              循环体语句;
              条件控制语句;
        * }
        * */
        //开始条件1
        //结束条件100
        int i = 1;
        while (i <= 100){
            System.out.println(i);
            i++;
        }
    }
}
```

#### 给循环起标识符

给循环起个标识符，对**指定循环**进行操作.

```java
public static void main(String[] args) {
        loop: while (true) { //给循环起个标识符，让break跳出while循环
            System.out.println("----------欢迎来到学生管理系统----------");
            System.out.println("1.添加学生");
            System.out.println("2.删除学生");
            System.out.println("3.修改学生");
            System.out.println("4.查询学生");
            System.out.println("5.退出");
            System.out.print("请输入您的选择:");
            Scanner sc = new Scanner(System.in);
            String choose = sc.next();
            switch (choose){
                case "1" -> System.out.println("添加学生");
                case "2" -> System.out.println("删除学生");
                case "3" -> System.out.println("修改学生");
                case "4" -> System.out.println("查询学生");
                case "5" -> {
                    System.out.println("退出");
                    break loop; //单个break只会跳出switc循环，break+标识符可以跳出指定循环
                }
                default -> System.out.println("没有这个选项");
            }
        }
    }
```



#### for循环和while循环的对比

>相同点:运行规则一样
>
>不同点:
>
>for循环中,控制循环的变量,因为归属for循环的语法结构中,在for循环结束后,就不能再次被访问到
>
>while循环中,控制循环的变量,对于while循环来说不归属其语法结构中,在while循环结束后,该变量还可以继续使用
>
>**习惯区别**
>
>for循环中: 知道**循环次数或者循环的范围**
>
>while循环中; 不知道循环次数和范围,只知道**循环的结束条件**

```java
public class whileDemo2 {
    public static void main(String[] args) {
        //珠穆朗玛峰（8844.43米=8844430毫米),假如有一张足够大的纸，它的厚度是0.1毫米，需要折叠多少次可以达到珠穆朗玛峰的高度
        //定义一个变量记录次数
        int count = 0;
        //记录开始厚度
        double i = 0.1;
        //记录山峰高度
        double heigth = 8844430;
        while (i <= heigth){
            count++;
            //折叠纸张
            i *= 2;
            System.out.println(i);
        }
        System.out.println("折叠次数："+count);
    }
}
```

#### do...while循环

#### 格式

```java
初始化语句;
do{
  循环体语句;
  条件控制语句;
}while(条件判断语句);
```

> 先执行后判断

> **运行流程**
>
> 初始化语句 -> 循环体语句 -> 条件控制语句 -> 条件判断语句(ture -> 循环体语句)

### 回文数练习

```java
import java.util.Scanner;

public class Test9 {
    public static void main(String[] args) {
        /*给一个整数x，如果x是一个回文数，打印true，否则，返回false
        * 回文数：121
        * 不是回文数：123
        * 回文数是指从正序和倒序读都是一样的整数*/

        //思路：将数字倒过来跟原来的数字进行比较
        //键盘输入一个整数
        Scanner  sc = new Scanner(System.in);
        //1.输入需要判断的整数
        System.out.println("请输入需要判断的整数:");
        int number = sc.nextInt();
        //定义一个临时变量进行记录最初的值，用于最后的比较
        int temp = number;
        //定义结果变量
        int result = 0;
        //利用while循环进行判断
        while (number != 0){
            //2.从右往左依次获取每一位数字
            int ge = number % 10; //取余
            //修改输入的值
            number = number / 10; //整数参与计算,结果只能得到整数
            //将当前获取的数字进行拼接
            result = result *10 + ge;
        }
        //3.打印结果
        System.out.println(temp == result);
    }
}
```

### 求商和余数

```java
public class Test10 {
    public static void main(String[] args) {
        /*给定两个整数，被除数和除数（都是正数，不超过int范围）
        * 将两数相除，要求不使用乘法、除法和%运算符
        * 得到商和余数*/
        //分析：被除数/除数=商。。。。余数
        /*
        * int a=100;
        * int b=10;
        * 100-10=90
        * 90-10=80
        * ......
        * 10-10=0(余数)*/

        //1.定义被除数变量
        int a = 100;
        //2.定义除数变量
        int b = 14;
        //3.定义商变量，记录减的次数
        int count = 0;
        //利用while循环获取商和余数
        //只要被除数大于或等于除数，循环一直进行
        while (a >= b){
            a = a-b;
            count++;
        }
        System.out.println("商:"+count+"\n"+"余数:"+a);
    }
}
```

### 高级循环

#### 无限循环

```java
for(;;){
  System.out.println("学习");
}
```

```java
while(true){
  System.out.println("学习");
}
```

```java
do{
  System.out.println("学习");
}while(true);
```

#### 跳转控制语句

##### continue

结束本次循环，继续下次循环

```java
public class continueDemo {
    public static void main(String[] args) {
        //1.跳过某次循环
        for (int i = 1;i <= 5;i++){
            if (i == 3){
                //结束本次循环，继续下次循环
                continue;
            }
            System.out.println("吃第"+i+"个包子");
        }
    }
}
```

##### break

结束整个循环

```java
public class breakDemo {
    public static void main(String[] args) {
        //1.结束整个循环
        for (int i = 1;i <= 5;i++){
            System.out.println("吃第"+i+"个包子");
            if (i == 3){
                //结束整个循环
                break;
            }
        }
    }
}
```

### 逢7过

```java
public class Game1 {
    public static void main(String[] args) {
        //游戏：逢7过
        /*游戏规则：从任意一个数字开始报数，当你要报的数字是包含7或7的倍数时都要说过
        * 需求：使用程序在控制台打印1-100之间满足逢7过规则的数据*/
        //1.得到1-100之间的每一个数字
        for (int i = 1;i <= 100;i++){
            if (i % 10 ==7 || i /10 %10 ==7 || i % 7==0){
                System.out.println('过');
                continue;
            }
            System.out.println(i);
        }

    }
}
```

### 求平方根

```java
import java.util.Scanner;

public class Test11 {
    public static void main(String[] args) {
        /*键盘录入一个大于等于2的整数x，计算并返回x的平方根
        * 结果只保留整数部分，小数部分将被舍去*/
        //分析：
        //平方根 16的平方根4
        //10
        //1 * 1 =1 < 10
        //2 * 2 =4 < 10
        //3 * 3 =9 < 10
        //4 * 4 =16> 10
        //推断：10的平方根在3-4之间
        //从1开始循环，拿着数字的平方跟原来的数字进行比较
        //如果小于的，继续往后进行判断
        //如果大于的，前一个数字就是平方根的整数
        //1.键盘录入一个大于等于2的整数
        Scanner sc = new Scanner(System.in);
        System.out.println("请输入一个大于等于2的整数：");
        int number = sc.nextInt();
        //2.利用for循环
        //从1开始，number结束
        for (int i = 1;i <= number;i++){
            if (i*i == number){
                System.out.println(number+"的平方根的整数部分"+i);
                break;
            } else if (i*i > number) {
                System.out.println(number+"的平方根的整数部分"+(i-1));
                break;
            }
        }
    }
}
```

### 求质数

```java
import java.util.Scanner;

public class Test12 {
    public static void main(String[] args) {
        /*键盘录入一个正整数x，判断该整数是否是一个质数*/
        //质数：
        //如果一个数字只能被1和他本身整除，那么这个数字是质数，否则这个数字是合数

        //1.键盘录入一个正整数
        Scanner sc = new Scanner(System.in);
        System.out.println("请输入整数:");
        int x = sc.nextInt();

        //定义一个变量，记录能被整除的次数
        int count = 0;
        //2.利用for循环输出1-x范围内的每一个数，并且进行判断
        for (int i = 1;i <= x;i++){
            if (x % i == 0){
                count++;
            }
        }
        if (count == 2){
            System.out.println(x+"是质数");
        }else {
            System.out.println(x+"不是质数");
        }
    }
}

```

### 猜数字的游戏

#### 获取随机数

```java
//1.导包,Random这个类在哪里
import java.util.Random;
//2.创建对象,表示要开始用Random这个类了
Random r = new Random();
//3.生成随机数
int number = r.nextInt(随机数的范围);
```

> 随机数范围注意:
>
> 在小括号中，书写的是生成随机数的范围
> 这个范围一定是从0开始的
> 到这个数-1结束
> 口诀：**包头不包尾，包左不包右**

```java
import java.util.Random;
import java.util.Scanner;

public class Game2 {
    public static void main(String[] args) {
        /*程序自动生成一个1-100之间的随机数字
        * 使用程序实现猜出这个数字是多少*/

        //1.先获取一个随机数
        //范围0-10
        Random r = new Random();
        //生成随机数
        //在小括号中，书写的是生成随机数的范围
        //这个范围一定是从0开始的
        //到这个数-1结束
        //口诀：包头不包尾，包左不包右
        int number = r.nextInt(101);//0-100
        //2.猜这个数字是多少
        Scanner sc = new Scanner(System.in);
        while (true){
            System.out.println("请输入你要猜的数字:");
            int guessNumber = sc.nextInt();
            //3.判断两个数字给出不同的提示
            if (guessNumber > number){
                System.out.println("大了");
            } else if (guessNumber < number) {
                System.out.println("小了");
            }else {
                System.out.println("猜中了");
                break;
            }
        }
    }
}
```

## 数组

### 数组介绍

> 数组指的是一种容器,可以用来存储**同种数据类型**的多个值

>1. 数组容器存储的时候,需要结合隐式转换考虑
>2. 例如: int类型的数组容器(~~boolean~~、byte、short、int、~~double~~)
>3. 例如: double类型的数组容器(byte、short、int、long、float、double)
>4. 参考: double>float>long>int>short>byte
>5. 建议:容器的类型,和存储的数据类型保持一致

### 数组的定义和静态初始化

#### 数组的定义

##### 格式一

```java
数据类型[] 数组名
//例如: int[] arry
```

##### 格式二

```java
数据类型 数组名[]
//例如: int arry[]
```

#### 数组初始化

> 初始化: 就是在内存中,为数组容器开辟空间,并将数据存入容器的过程

##### 完整格式

```java
数据类型[] 数组名 = new 数据类型[]{元素1,元素2,元素3.....};
//例子: int[] arry =new int[]{1,2,3};
```

##### 简写格式

```java
数据类型[] 数组名 = {元素1,元素2,元素3....};
//例子: int[] arry = {1,2,3};
```

### 数组的地址值

#### 数组的地址值

```java
public class ArrayDemo1 {
    public static void main(String[] args) {
        //定义一个数组
        int[] array1 = {1,2,3,4};
        System.out.println(array1); //[I@2f92e0f4 //数组的地址值
    }
}
```

> 扩展:
>
> ```java
> //定义一个数组
> int[] array1 = {1,2,3,4};
> System.out.println(array1); //[I@2f92e0f4 //数组的地址值
> ```
>
> - [I@2f92e0f4
> - [ ,表示当前是一个数组
> - I ,表示当前数组里面的元素都是int类型
> - @ ,表示一个间隔符号,固定类型
> - 2f92e0f4 , 数组真正的地址值,十六进制

### 数组元素访问

#### 格式

```java
数组名[索引];
```

#### 索引

> 索引: 下标,角标
>
> 索引特点: **从0开始,逐个+1增长**,连续不间断

### 数组元素存储

#### 格式

```java
数组名[索引] = 具体数据/变量;
```

```java
int[] array1 = {1,2,3,4};
array1[0] = 100;
System.out.println(array1[0]); //100
```

> 注意:
>
> 一旦**覆盖**元素组之后,原来的数据就**不存在**了

### 数组遍历

> 将数组中所有的内容取出来,取出来之后可以(打印,求和,判断...)
>
> 注意:
>
> 遍历指的是**取出数据**的过程,不仅仅打印

#### 数组长度属性

> 在java中,关于数组的一个长度属性,length
>
> **调用方式:** `数组名.length``

```java
public class ArrayDemo1 {
    public static void main(String[] args) {
        //定义一个数组
        int[] arr = {1,2,3,4};
        //利用循环遍历
        //开始条件：0
        //结束条件：数组长度 - 1 （最大索引）

        //在java中,关于数组的一个长度属性,length
        //调用方式:数组名.length
        for (int i = 0;i <= arr.length-1;i++){
            System.out.println(arr[i]);
        }
    }
}
```

#### 变化数据练习

```java
public class ArrayDemo2 {
    public static void main(String[] args) {
        /*定义一个数组，存储1，2，3，4，5，6，7，8，9，10
        * 遍历数组得到每一个元素
        * 要求：
        * 1.如果是奇数，则将当前数据扩大两倍
        * 2.如果是偶数，则将当前数据变成二分之一*/

        //1.定义一个数组，存1，2，3，4，5，6，7，8，9，10
        int[] arr = {1,2,3,4,5,6,7,8,9,10};

        //2.遍历数组得到每一个元素
        for (int i = 0 ;i < arr.length;i++){
            //3.对每一个元素进行判断
            if (arr[i] % 2 ==0 ){
                arr[i] = arr[i] / 2;
                System.out.println(arr[i]);
            }else {
                arr[i] = arr[i] * 2;
                System.out.println(arr[i]);
            }
        }
    }
}

```

### 数组动态初始化

动态初始化: 初始化时只指定数组长度,由系统为数组分配初始值

```java
数据类型[] 数组名 = new 数据类型[数组长度]
```

> 数组默认初始化值的规律:
>
> 1. 整数类型,默认初始化值0
> 2. 小数类型,默认初始化值0.0
> 3. 字符类型,默认初始化值'/u0000' 空格
> 4. 布尔类型,默认初始化值false
> 5. 引用数据类型,默认初始化值 null

```java
public class ArrayDemo3 {
    public static void main(String[] args) {
        /*定义一个数组，用来存储班级中50个学生的姓名
        * 姓名未知，等学生报道之后，再进行添加*/
        //格式：
        //数据类型[] 数组名 = new 数据类型[数组长度]
        //在创建的时候，由我们自己指定数组长度，由虚拟机给出默认的初始化值

        String[] arr = new String[50];
        //添加学生
        arr[0] = "Lisi";
        arr[1] = "Zhangsan";
        //获取
        System.out.println(arr[0]);
        System.out.println(arr[1]);
        System.out.println(arr[2]); //打印出来的是默认初始化值null
    }
}
```

### 数组练习

```java
import java.util.Random;

public class ArrayTest2 {
    public static void main(String[] args) {
        /*生成10个1-100之间的随机数存入数组
        * 1.求出所有数据的和
        * 2.求所有数据的平均值
        * 3.统计有多少个数据比平均值小*/

        //1.创建一个动态初始化数组
        int[] arr = new int[10];
        //2.生成随机数并且导入
        Random sr = new Random();
        for (int i = 0; i <= 9; i++){
            arr[i] = sr.nextInt(100) + 1;
            System.out.println(arr[i]);
        }

        //3.求和
        int sum = 0;
        for (int x = 0;x < arr.length;x++){
            sum += arr[x];
        }
        System.out.println("所有数据的和:"+sum);

        //4.求平均值
        int avg = sum / arr.length;
        System.out.println("所有数据的平均值:"+avg);

        //5.统计有多少个数据比平均值小
        //计数器
        int count = 0;
        for (int y = 0;y < arr.length;y++){
            if (arr[y] < avg){
                count++;
            }
        }
        System.out.println("有"+count+"个数据比平均值小");

    }
}
```

#### java数组求最值

```java
public class ArrayTest1 {
    public static void main(String[] args) {
        /*求最值
        * 已知数组元素为[33，5，22，44，55]
        * 求出数组中最大值并且打印在控制台*/
        //1.定义一个数组
        int[] arr = {33,5,22,44,55};
        //4.定义一个动态变量
        int result = 0;
        //2.for循环遍历数组每一个元素
        for (int i = 0;i < arr.length;i++){
            //3.对每一个元素进行判断
            if (arr[i] > result){
                result =arr[i];
            }
        }
        System.out.println(result);
    }
}

```

#### 交换数组中的数据

```java
public class ArrayTest3 {
    public static void main(String[] args) {
        /*定义一个数组，存入1，2，3，4，5。按照要求交换索引对应的元素
        * 交换前：1，2，3，4，5
        * 交换后：5，2，3，4，1*/

        //1.定义一个数组
        int[] arr = {1,2,3,4,5};
        //2.将0索引和最大索引的值进行交换
        int temp = arr[0]; //中间变量
        arr[0] = arr[arr.length-1];
        arr[arr.length-1] = temp;

        //3.打印交换后的数组
        for (int i = 0;i < arr.length;i++){
            System.out.println(arr[i]);
        }
    }
}
```

```java
public class ArrayTest3 {
    public static void main(String[] args) {
        /*定义一个数组，存入1，2，3，4，5。按照要求交换索引对应的元素
        * 交换前：1，2，3，4，5
        * 交换后：5，4，3，2，1*/

        //1.定义一个数组
        int[] arr = {1,2,3,4,5};
        //2.利用循环去交换数据
        for (int i = 0,j = arr.length-1;i < j;i++,j--){
            //交换变量i和j指向的元素
            int temp = arr[i]; //中间变量
            arr[i] = arr[j];
            arr[j] = temp;
        }

        for (int i=0;i<arr.length;i++){
            System.out.println(arr[i]);
        }
    }
}
```

### 二维数组

#### 二维数组静态初始化

```java
//格式
数据类型[][] 数组名 = new 数据类型[][]{{元素1,元素2},{元素1,元素2}};
//简化格式
数据类型[][] 数组名 = {{元素1,元素2},{元素1,元素2}};
```

## java内存分配

### 栈

> **方法**运行时使用的内存,比如main方法运行,进入方法栈中执行

### 堆

> 存储对象或者数组,**new**来创建,都存储在堆内存

### 方法区

> 存储可以运行的class文件

## 方法

### 什么是方法

方法是程序中最小的执行单元

例如main方法

### 使用场景

重复的代码、具有独立功能的代码可以抽取到方法中

- 可以提高代码的复用性
- 可以提高代码的可维护性

### 方法的格式

#### 方法定义

把一些代码打包在一起

#### 方法调用

方法定义后并不是直接运行,需要手动调用才能执行,该过程称为方法调用

#### 格式

##### 最简单的方法定义和调用

```java
public static void 方法名(){
  方法体;
}
```

> 在main方法里面调用我们自定义的方法
>
> 方法名();

##### 带参数的方法定义和调用

```java
public static void 方法名(参数){
  
}
```

```java
public static void 方法名(参数1,参数2,参数3.....){

}
```

######  调用

```java
//单个参数: 方法名(参数);
//多个参数: 方法名(参数1,参数2,参数3.....);
```

```java
public static void method(int num1, int num2){ //形参
  int result = num1 + num2;
  System.out.println(result);
}
//main方法调用 method(10,20)//实参  //30
```

###### 形参和实参

> **形参**: 全称形式参数,是指**方法定义**中的参数
>
> **实参**: 全称实际参数,方法调用中的参数

**注意**:方法调用时,参数的数量与类型必须与方法中小括号里面的变量一一对应,否则程序报错

##### 带返回值方法的定义

```java
public static 返回值类型 方法名(参数){
  方法体;
  return 返回值;
}
```

例子:

```java
public static int getSum(int a,int b){
  int c = a + b;
  return c;
}
```

###### 调用

1.直接调用

`方法名(参数);`

2.赋值调用

`整数类型 变量名 = 方法名(参数);`

3.输出调用

`System.out.println(方法名(参数));`

### 方法的注意

- 方法不调用就不执行
- 方法与方法之间时平级关系,不能互相嵌套定义
- 方法的编写顺序和执行顺序无关
- 方法的返回类型为void,表示该方法没有返回值,没有返回值的方法可以省略return语句不写,如果要编写return,后面不能跟具体的数据.
- return语句下面,不能编写代码,因为永远执行不到,属于无效代码

### 方法的重载

同一个类中,**方法名相同**,**参数不同**的方法,与返回值无关.

参数不要同:个数不同、类型不同、顺序不同

### 方法练习

#### 遍历求最大值

##### 数组遍历

```java
public class printDemo {
    public static void main(String[] args) {
        System.out.print("abc");//只打印abc，不换行
        System.out.println("bcd");
        System.out.println(); //不打印任何数据，只能换行处理
    }
}
```

```java
public class MethodDemo2 {
    public static void main(String[] args) {
        //1.定义一个数组
        int[] arr = {11,22,33,44,55};
        printArr(arr);
    }

    /*设计一个方法用于遍历，要求遍历的结果是在一行上，例如：[11，22，33，44，55]*/
    public static void printArr(int[] arr){
        System.out.print('[');
        for (int i = 0;i < arr.length;i++){
            if (i == arr.length -1){
                System.out.print(arr[i]);
            }else{
                System.out.print(arr[i]+",");
            }
        }
        System.out.println(']');

    }

}
```

##### 数组最大值

```java
public class MethodDemo3 {
    //设计一个方法求数组最大值，并将最大值返回
    public static void main(String[] args) {
        //1.定义一个数组
        int[] arr = {1,2,3,5,7,2,3};
        //2.调用方法求最大值
        int max = maxDemo(arr);
        System.out.println(max);
    }
    public static int maxDemo(int[] arr){
        int max = arr[0];
        for (int i = 1;i < arr.length;i++){
            if (arr[i] >max){
                max = arr[i];
            }
        }
        return max;
    }

}
```

##### 判断一个数字是否在数组中存在

```java
public class MethodTest1 {
    //定义一个方法判断数组中的某一个数是否存在，并将结果返回给调用处
    public static void main(String[] args) {
        //1.定义一个数组
        int[] arr = {1,2,3,4,5,6};
        //2.调用方法判断
        boolean result = contains(arr,10);
        System.out.println(result);
    }
    public static boolean contains(int[] arr,int number){
        for (int i = 0;i < arr.length;i++){
            if (arr[i] == number){
                return true;
            }
        }
        return false;
    }
}

```

##### 拷贝数组

```java
public class MethodTest2 {
    /*定义一个方法copyOfRange(int[] arr,int from,int to)
    * 将数组arr中从索引from（包含from）开始
    * 到索引to结束（不包含to）的元素复制到新数组中
    * 将新数组返回*/
    public static void main(String[] args) {
        //1.定义个数组
        int[] arr = {1,2,3,4,5,6,7};
        //2.调用方法
        int[] copyArr = copyOfRange(arr,3,6);
        for (int i:copyArr){
            System.out.println(i);
        }
    }
    public static int[] copyOfRange(int[] arr,int from,int to){
        //1.定义新数组
        int[] newArr = new int[to-from];
        //2.拷贝到新数组
        //伪造索引
        int index = 0;
        for (int i = from;i < to;i++){
            newArr[index] = arr[i];
            index++;
        }
        //3.返回
        return newArr;
    }
}

```

### 方法的值传递

传递基本数据类型时,传递的是真实的数据,形参的改变,不影响实际参数的值

```java
public class ArgsDemo1 {
    public static void main(String[] args) {
        int number = 100;
        System.out.println("调用change方法前:"+number);
        change(number);
        System.out.println("调用change方法后:"+number);
    }
    public static void change(int number){
        number = 200;
    }
}
```

传递应用数据类型时,传递的是地址值,形参的改变,影响实际参数的值

```java
public class ArgsDemo2 {
    public static void main(String[] args) {
        int[] arr = {1,2,3};
        System.out.println("调用change方法前:"+arr[1]);
        change(arr);
        System.out.println("调用change方法后:"+arr[1]);
    }
    public static void change(int[] arr){
        arr[1] = 200;
    }
}
```

## 面向对象

### 类和对象

**类**:是对象共同特征的描述

**对象:**是真实存在的具体东西

在java中,必须先设计类,才能获得对象.

#### 定义类

```java
public class 类名{
  1.成员变量(代表属性,一般是名词)
  2.成员方法(代表行为,一般是动词)
  3.构造器 
  4.代码块
  5.内部类
}
```

#### 得到类的对象

```java
类名 对象名 = new 类名();
```

#### 使用对象

访问属性: 对象名.成员变量

访问行为: 对象名.方法名(...)

> - 类名首字母建议大写,需要见名知意
> - 一个java文件中可以定义多个class类,且只能是一个类是public修饰,而且public修饰的类名必须成为代码文件名,实际开发中建议还是一个文件定义一个class类
> - 成员变量的完善定义格式是:修饰符 数据类型 变量名称 = 初始化值; 一般无需指定初始化值,存在默认值

### 封装

对象代表什么,就得封装对应的数据,并提供数据对应的行为

### private关键字

- 是一个权限修饰符
- 可以修饰成员(成员变量和成员方法)
- 被private修饰的成员只能在**本类中才能访问**

```java
public class GirlFriend{
  private int age;
  //set赋值 //调用:类名.setAge(参数);
  public void setAge(int a){
    if(a >= 18 && a <= 50){
      age = a ;
    }else{
      System.out.println("非法数据");
    }
  }
  //get获取  //调用:类名.getAge();
  public int getAge(){
    return age;
  }
}
```

### set和get方法

针对每一个私有化的成员变量,都要提供get和set方法

set方法:给成员变量赋值,"setXXX(参数)",方法用public修饰

get方法:对外提供成员变量的值,"getXXX(参数)",方法用public修饰

### this关键字

> 代表方法调用者的地址值

#### 成员变量和局部变量

> 成员变量: 类中方法外的变量
>
> 局部变量: 方法中的变量

|     区别     |                 成员变量                  |                   局部变量                    |
| :----------: | :---------------------------------------: | :-------------------------------------------: |
| 类中位置不同 |                类中,方法外                |               方法内,方法申明上               |
| 初始化值不同 |               有默认初始化                |           没有,使用之前需要完成赋值           |
| 内存位置不同 |                  堆内存                   |                    栈内存                     |
| 生命周期不同 | 随着对象的创建而存在,随着对象的消失而消失 | 随着方法的调用而存在,随着方法的运行结束而消失 |
|    作用域    |               整个类中有效                |                当前方法中有效                 |

**就近原则**

成员变量在类里面

局部变量在方法里面

this可以区别成员变量和局部变量

```java
public class GirlFriend{
  //属性
  private int age; //0 // 成员变量
  //方法
  public void method(){
    int age = 10; //10 //局部变量
    System.out.println(age);//就近原则 //10
    System.out.println(this.age); //0
  }
}
```

### 构造方法

构造方法也叫作构造器、构造函数

作用:在创建对象的时候给成员变量进行赋值

#### 构造方法格式

```java
public class Student{
  修饰符 类名(参数){ //修饰符例如public
    方法体;
  }
}
```

> 1.方法名与类名相同,大小写也要一致
>
> 2.没有返回值类型,连void都没有
>
> 3.没有具体的返回值(不能由retrun带回结果数据)

#### 调用

```java
类名 对象名 = new 类名(参数);
```

#### 注意事项

1.如果没有定义构造方法,系统将给出一个默认的无参数构造方法

2.如果定义了构造方法,系统将不再提供默认的构造方法

3.手动书写无参数构造方法,和带全部参数的构造方法

### 标准的JavaBean类

1.类名需要见名知意

2.成员变量使用private修饰

3.提供至少两个构造方法: **无参构造方法和带参数构造方法**

4.成员方法: 提供每一个成员变量对应的setXxx()/getSxx() ;如果还有其他行为,也需要写上

## Java内存分配

- 栈
- 堆
- 方法区
- 本地方法栈
- 寄存器

>方法区: 字节码文件加载时进入的内存
>
>栈内存: 方法运行时所进入的内存,变量也是在这里
>
>堆内存: new 出来的东西会在这块内存中开辟空间并产生地址

### 一个对象的内存图

`Students s = new Students();  //s局部变量`

1. 加载class文件
2. 申明局部变量
3. 在堆内存中开辟一个空间
4. 默认初始化
5. 显示初始化
6. 构造方法初始化
7. 将堆内存中的地址值赋值给左边的局部变量

## %s 占位

> 第一部分参数: 要输出的内容%s(占位)
>
> 第二部分参数: 填充的数据
>
> ```java
> System.out.println("你好呀,%s","张三")  //你好呀,张三
> ```
>
> 

## 键盘录入

### 第一套体系

```java
nextInt(); //接收整数
nextDouble(); //接收小数
next(); //接收字符串
```

**遇到空格,制表符,回车就停止接收,这些符号后面的数据就不会接受了.**

```java
import java.util.Scanner;

public class Test13 {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.println("请输入一个字符串");//abc bcd
        String str1 = sc.next();
        System.out.println(str1);//abc
        System.out.println("请输入第二个字符串");
        String str2 = sc.next();
        System.out.println(str2);//bcd
    }
}
```

### 第二套体系

```java
nextLine(); //接收字符串
```

```java
import java.util.Scanner;

public class Test13 {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.println("请输入一个字符串");//abc bcd
        String str3 = sc.nextLine();
        System.out.println(str3);//abc bcd
        System.out.println("请输入第二个字符串");
        String str4 = sc.nextLine();
        System.out.println(str4);//
    }
}

```

**键盘录入的两套体系不能混用**

## 对象数组

### 定义

#### 动态初始化

```java
类名称[] 对象 数组名 = new 类名称[长度];
```

#### 静态初始化

```java
类名称[] 对象数组名 = new 类名称[] {对象，对象......};
```

## API

应用程序编程接口

java api : 指的就是JDK中提供的各种功能的java类

这些类将底层的实现封装了起来,不需要关心这些类如何实现,只需要学习如何使用这些类

例如:

Scanner 键盘录入

Random 随机数

**查阅帮助文档**

## String类

### String类概述

​	String 类代表字符串，Java 程序中的所有字符串文字（例如“abc”）都被实现为此类的实例。也就是说，Java 程序中所有的双引号字符串，都是 String 类的对象。String 类在 java.lang 包下，所以使用的时候不需要导包！

### String类的特点

- 字符串不可变，它们的值在创建后不能被更改
- 虽然 String 的值是不可变的，但是它们可以被共享
- 字符串效果上相当于字符数组( char[] )，但是底层原理是字节数组( byte[] )

### String类的构造方法

- 常用的构造方法

  | 方法名                      | 说明                                      |
  | --------------------------- | ----------------------------------------- |
  | public   String()           | 创建一个空白字符串对象，不含有任何内容    |
  | public   String(char[] chs) | 根据字符数组的内容，来创建字符串对象      |
  | public   String(byte[] bys) | 根据字节数组的内容，来创建字符串对象      |
  | String s =   “abc”;         | 直接赋值的方式创建字符串对象，内容就是abc |

- 示例代码

  ```java
  public class StringDemo01 {
      public static void main(String[] args) {
          //public String()：创建一个空白字符串对象，不含有任何内容
          String s1 = new String();
          System.out.println("s1:" + s1);
        
          //传递一个字符数组，根据传递的字符串内容再创建一个新的字符串对象
          String s5 = new String("你好");
          System.out.println("s5:" + s5);
  
          //public String(char[] chs)：根据字符数组的内容，来创建字符串对象
          char[] chs = {'a', 'b', 'c'};
          String s2 = new String(chs);
          System.out.println("s2:" + s2);
  
          //public String(byte[] bys)：根据字节数组的内容，来创建字符串对象
          byte[] bys = {97, 98, 99};
          String s3 = new String(bys);
          System.out.println("s3:" + s3);
  
          //String s = “abc”;	直接赋值的方式创建字符串对象，内容就是abc
          String s4 = "abc";
          System.out.println("s4:" + s4);
      }
  }
  ```

### 创建字符串对象两种方式的区别

- **通过构造方法创建**

  ​	通过 new 创建的字符串对象，每一次 new 都会申请一个内存空间，**虽然内容相同，但是地址值不同**

- **直接赋值方式创建**

  ​	以“”方式给出的字符串，系统会检查该字符串在串池中是否存在,只要字符序列相同(顺序和大小写,复用,无论在程序代码中出现几次，JVM 都只会建立一个 String 对象，并在**字符串池(StringTable)**中维护

### 字符串的比较

键盘录入的字符串是通过new方法创建的字符串对象

#### ==号的作用

- 比较**基本数据类型**：比较的是**具体的值**
- 比较**引用数据类型**：比较的是**对象地址值**

#### equals方法的作用

- 方法介绍

  ```java
  boolean equals方法(要比较的字符串)  //完全一样结果才是true,否则为false (看大小写)
  boolean equalsIgnoreCase(要比较的字符串)  //忽略大小写比较
  ```

- ```java
  //调用格式
  boolean result = 第一个字符串.equals(要比较的字符串)
  ```
  
- 示例代码

  ```java
  public class StringDemo02 {
      public static void main(String[] args) {
          //构造方法的方式得到对象
          char[] chs = {'a', 'b', 'c'};
          String s1 = new String(chs);
          String s2 = new String(chs);
  
          //直接赋值的方式得到对象
          String s3 = "abc";
          String s4 = "abc";
  
          //比较字符串对象地址是否相同
          System.out.println(s1 == s2);
          System.out.println(s1 == s3);
          System.out.println(s3 == s4);
          System.out.println("--------");
  
          //比较字符串内容是否相同
          System.out.println(s1.equals(s2));
          System.out.println(s1.equals(s3));
          System.out.println(s3.equals(s4));
      }
  }
  ```

### 用户登录案例

#### 案例需求

​	已知用户名和密码，请用程序实现模拟用户登录。总共给三次机会，登录之后，给出相应的提示

#### 代码实现

```java
public class Test1登录案例 {
    public static void main(String[] args) {
        //1.定义两个变量用来记录正确的用户名和密码
        String rightUsername = "itheima";
        String rightPassword = "1234qwer";

        //2.键盘录入用户名和密码
        //ctrl + alt + T 选择包裹方式

        for (int i = 0; i < 3; i++) {//0 1 2
            Scanner sc = new Scanner(System.in);
            System.out.println("请输入用户名");
            String username = sc.next();
            System.out.println("请输入密码");
            String password = sc.next();

            //3.判断比较
            if (username.equals(rightUsername) && password.equals(rightPassword)) {
                System.out.println("登录成功");
                //如果正确，循环结束
                break;
            } else {
                //最后一次机会
                if(i == 2){
                    System.out.println("账户" + username + "被锁定");
                }else{
                    //不是最后一次机会
                    System.out.println("用户名或密码错误，登录失败,还剩下" + (2 - i) + "次机会");//2 1 0
                }
            }
        }

    }
}

```

### 遍历字符串案例

```java
public char charAt(int index) //根据索引返回字符 //调用方法: char c = 字符串对象.charAt(int index)
public int length()  //返回字符串的长度
数组的长度: 数组名.length
字符串的长度: 字符串对象.length
```

#### 案例需求

​	键盘录入一个字符串，使用程序实现在控制台遍历该字符串

#### 直接遍历字符串

```java
public class Test2字符串直接遍历 {
    public static void main(String[] args) {
        //两个方法：
        //charAt()：会根据索引获取对应的字符
        //length(): 会返回字符串的长度


        //1.键盘录入一个字符串
        Scanner sc = new Scanner(System.in);
        System.out.println("请输入字符串");
        String str = sc.next();
        System.out.println(str);

        //2.遍历
        for (int i = 0; i < str.length(); i++) {
            //i 依次表示字符串的每一个索引
            //索引的范围：0 ~  长度-1

            //根据索引获取字符串里面的每一个字符
            //ctrl + alt + V 自动生成左边的接受变量
            char c = str.charAt(i);
            System.out.println(c);
        }
    }
}

```

### 统计字符次数案例

#### 案例需求

​	键盘录入一个字符串，统计该字符串中大写字母字符，小写字母字符，数字字符出现的次数(不考虑其他字符)

#### 代码实现

```java
public class Test4统计个数 {
    public static void main(String[] args) {
        //键盘录入一个字符串，统计大写，小写，数字出现的次数


        //1.键盘录入一个字符串
        Scanner sc = new Scanner(System.in);
        System.out.println("请输入一个字符串");
        String str = sc.next();


        //2.统计 --- 计数器count
        //此时我要统计的有3样东西，所以要定义3个计数器分别进行统计
        int bigCount = 0;
        int smallCount = 0;
        int numberCount = 0;
        //得到这个字符串里面每一个字符
        for (int i = 0; i < str.length(); i++) {
            //i 表示字符串中的索引
            //c 表示字符串中的每一个字符
            char c = str.charAt(i);

            //对c进行判断
            if (c >= 'a' && c <= 'z') {
                smallCount++;
            }else if(c >= 'A' && c <= 'Z'){
                bigCount++;
            }else if(c >= '0' && c <= '9'){
                numberCount++;
            }
        }

        //3.当循环结束之后，三个变量记录的就是对应的个数
        System.out.println("大写字符有:" + bigCount + "个");
        System.out.println("小写字符有:" + smallCount + "个");
        System.out.println("数字字符有:" + numberCount + "个");
    }
}

```

### 字符串拼接案例

#### 案例需求

​	定义一个方法，把 int 数组中的数据按照指定的格式拼接成一个字符串返回，调用该方法，

​	并在控制台输出结果。例如，数组为 int[] arr = {1,2,3}; ，执行方法后的输出结果为：[1, 2, 3]

#### 代码实现

```java
public class Test5数组拼接成字符串 {
    public static void main(String[] args) {
        //定义一个方法，把 int 数组中的数据按照指定的格式拼接成一个字符串返回，调用该方法，
        //并在控制台输出结果。例如，数组为 int[] arr = {1,2,3};
        //执行方法后的输出结果为：[1, 2, 3]


        int[] arr = {1, 2, 3, 4, 5};

        String str = arrToString(arr);
        System.out.println(str);

    }


    //作用：把一个数组变成字符串
    public static String arrToString(int[] arr) {
        String s = "";
        //拼接左括号
        s = s + "["; //此时是拿着长度为0的字符串，跟[进行拼接，产生一个新的字符串。
        //把新的字符串再赋值给s，此时变量s记录的就是新的字符串"["的地址值

        //下面我想得到数组里面的每一个元素并进行拼接
        //那么就需要遍历数组，得到每一个元素才行
        for (int i = 0; i < arr.length; i++) {
            //假设第一次循环:i = 0 获取的就是0索引上的元素
            //在拼接的时候："[" + 1 + ", " 拼接完毕之后产生一个新的字符串 "[1, "
            //第二次循环：i = 1 获取的就是1索引上的元素
            //在拼接的时候： 此时s就是第一次循环结束后拼接完毕的结果："[1, "
            //在拼接的时候："[1, " + 2 + ", " 拼接完毕之后产生一个新的字符串 "[1, 2, "
            //...
           if(i == arr.length - 1){
               //如果是最后一个元素，那么不需要拼接逗号空格
               s = s + arr[i];
           }else{
               //如果不是最后一个元素，需要拼接元素和逗号空格
               s = s + arr[i] + ", ";
           }
        }

        //等循环结束之后，再拼接最后一个右括号
        s = s + "]";

        return s;

    }


    //用来遍历数组
    public static void printArr(int[] arr) {
        System.out.print("[");
        for (int i = 0; i < arr.length; i++) {
            if (i == arr.length - 1) {
                System.out.print(arr[i]);
            } else {
                System.out.print(arr[i] + ", ");
            }
        }
        System.out.println("]");

        //[1, 2, 3, 4, 5]
        //我们现在要知道，这个最终结果是怎么来的？
        //从到右依次打印得来的。
    }
}

```

### 字符串反转案例

#### 案例需求

​	定义一个方法，实现字符串反转。键盘录入一个字符串，调用该方法后，在控制台输出结果

​	例如，键盘录入 abc，输出结果 cba

#### 代码实现

```java
public class Test6反转字符串 {
    public static void main(String[] args) {
        /*定义一个方法，实现字符串反转。键盘录入一个字符串，调用该方法后，在控制台输出结果
        例如，键盘录入 abc，输出结果 cba*/



        //1.定义一个字符串
        Scanner sc = new Scanner(System.in);
        System.out.println("请输入一个字符串");
        String str = sc.next();
        //2.定义一个方法，反转字符串
        //abc  --->  cba
        //可以把字符串倒着遍历，再拼接
        String result = reverse(str);
        System.out.println(result);


    }

    //注释：方法的作用就是反转字符串
    //把传递进来的字符串进行反转
    public static String reverse(String str){//abc
        //核心思想：倒着遍历并进行拼接就可以了
        //fori :正着遍历  forr：倒着遍历
        String s = "";
        for (int i = str.length() - 1; i >= 0; i--) {
            //i 依次表示字符串里面的每一个索引（倒着的）
            //我们就可以拿到里面的每一个字符并拼接
            s = s + str.charAt(i);
        }

        //把倒着拼接之后的结果返回即可
        return s;

    }
}

```

### 金额转换

#### 案例需求

​	把2135变成：零佰零拾零万贰仟壹佰叁拾伍元 

​	把789变成：零佰零拾零万零仟柒佰捌拾玖元

#### 代码实现

```java
package com.itheima.stringdemo;

import java.util.Scanner;

public class StringDemo9 {
    public static void main(String[] args) {
        //1.键盘录入一个金额
        Scanner sc = new Scanner(System.in);
        int money;
        while (true) {
            System.out.println("请录入一个金额");
            money = sc.nextInt();
            if (money >= 0 && money <= 9999999) {
                break;
            } else {
                System.out.println("金额无效");
            }
        }

        //定义一个变量用来表示钱的大写
        String moneyStr = "";

        //2.得到money里面的每一位数字,再转成中文
        while (true) {//2135
            //从右往左获取数据，因为右侧是数据的个位
            int ge = money % 10;
            String capitalNumber = getCapitalNumber(ge);
            //把转换之后的大写拼接到moneyStr当中
            moneyStr = capitalNumber + moneyStr;
            //第一次循环 ： "伍" + "" = "伍"
            //第二次循环 ： "叁" + "伍" = "叁伍"
            //去掉刚刚获取的数据
            money = money / 10;

            //如果数字上的每一位全部获取到了，那么money记录的就是0，此时循环结束
            if (money == 0) {
                break;
            }
        }

        //3.在前面补0，补齐7位
        int count = 7 - moneyStr.length();
        for (int i = 0; i < count; i++) {
            moneyStr = "零" + moneyStr;
        }
        System.out.println(moneyStr);//零零零贰壹叁伍

        //4.插入单位
        //定义一个数组表示单位
        String[] arr = {"佰","拾","万","仟","佰","拾","元"};
        //               零    零   零   贰   壹   叁   伍

        //遍历moneyStr，依次得到 零    零   零   贰   壹   叁   伍
        //然后把arr的单位插入进去

        String result = "";
        for (int i = 0; i < moneyStr.length(); i++) {
            char c = moneyStr.charAt(i);
            //把大写数字和单位拼接到result当中
            result = result + c + arr[i];
        }

        //5.打印最终结果
        System.out.println(result);

    }


    //定义一个方法把数字变成大写的中文
    //1 -- 壹
    public static String getCapitalNumber(int number) {
        //定义数组，让数字跟大写的中文产生一个对应关系
        String[] arr = {"零", "壹", "贰", "叁", "肆", "伍", "陆", "柒", "捌", "玖"};
        //返回结果
        return arr[number];
    }

}

```

### 手机号屏蔽

#### 字符串截取

```java
String substring(int beginindex , int endindex);
//注意:包头不包尾,包左不包右.
String substring(int beginindex);
//截取到末尾
```

需求：以字符串的形式从键盘接受一个手机号，将中间四位号码屏蔽

最终效果为：`131****9468`

代码实现：

```java
public class Test8手机号屏蔽 {
    public static void main(String[] args) {
        /*以字符串的形式从键盘接受一个手机号，将中间四位号码屏蔽
        最终效果为：131****9468*/

        //1.键盘录入一个手机号码
        Scanner sc = new Scanner(System.in);
        System.out.println("请输入手机号码");
        String phoneNumber = sc.next();//13112349408

        //2.截取手机号码中的前三位
        String star = phoneNumber.substring(0, 3);

        //3.截取手机号码中的最后四位
        //此时我用substring方法，是用1个参数的，还是两个参数的？1个参数的会更好
        //因为现在我要截取到最后，所以建议使用1个参数的。
        String end = phoneNumber.substring(7);

        //4.拼接
        String result = star + "****" + end;

        System.out.println(result);

    }
}

```

### 敏感词替换 

需求1：键盘录入一个 字符串，如果字符串中包含（TMD），则使用***替换 

```java
public class Test9敏感词替换 {
    public static void main(String[] args) {
        //1.定义一个变量表示骂人的话
        String talk = "后裔你玩什么啊，TMD";


        //2.把这句话中的敏感词进行替换
        String result = talk.replace("TMD", "***");

        //3.打印
        System.out.println(talk);
        System.out.println(result);
    }
}

```

需求2：如果要替换的敏感词比较多怎么办？

```java
public class Test10多个敏感词替换 {
    public static void main(String[] args) {
        //实际开发中，敏感词会有很多很多

        //1.先键盘录入要说的话
        Scanner sc = new Scanner(System.in);
        System.out.println("请输入要说的话");
        String talk = sc.next();//后裔你玩什么啊，TMD,GDX,ctmd,ZZ

        //2.定义一个数组用来存多个敏感词
        String[] arr = {"TMD","GDX","ctmd","ZZ","lj","FW","nt"};

        //3.把说的话中所有的敏感词都替换为***

        for (int i = 0; i < arr.length; i++) {
            //i 索引
            //arr[i] 元素 --- 敏感词
            talk = talk.replace(arr[i],"***");
        }

        //4.打印结果
        System.out.println(talk);//后裔你玩什么啊，***,***,***,***

    }
}

```

### 身份证信息查看

​	身份证的每一位都是有固定的含义：

* 1、2位：省份 
* 3、4位：城市 
* 5、6位：区县 
* 7-14位：出生年、月、日 
* 15、16位：所在地派出所 
* 17位：性别（奇数男性，偶数女性）
* 18位：个人信息码（随机产生） 

要求打印内容方式如下：

​	人物信息为：

​	出生年月日：XXXX年X月X日

​	性别为：男/女

```java
package com.itheima.stringdemo;

public class StringDemo11 {
    public static void main(String[] args) {
        //1.定义一个字符串记录身份证号码
        String id = "321281202001011234";

        //2.获取出生年月日
        String year = id.substring(6, 10);
        String month = id.substring(10, 12);
        String day = id.substring(12, 14);


        System.out.println("人物信息为：");
        System.out.println("出生年月日:" + year + "年" + month + "月" + day + "日");

        //3.获取性别
        char gender = id.charAt(16);//'3'  ---> 3
        //利用ASCII码表进行转换
        //'0' --->  48
        //'1' --->  49
        //'2' --->  50
        //'3' --->  51
        //'4' --->  52
        //'5' --->  53
        //'6' --->  54
        //'7' --->  55
        //'8' --->  56
        //'9' --->  57

       int num = gender - 48;
        if(num % 2 == 0){
            System.out.println("性别为:女");
        }else{
            System.out.println("性别为:男");
        }
    }
}
```

## StringBuilder

StringBuilder 可以看成是一个容器，创建之后里面的**内容是可变**的。

当我们在**拼接字符串和反转字符串**的时候会使用到

```java
//因为StringBuilder是Java已经写好的类
//java在底层对他做了一些特殊处理。
//打印对象不是地址值而是属性值。
```

### 构造方法

|               方法名               |                  说明                   |
| :--------------------------------: | :-------------------------------------: |
|      `public StringBuilder()`      | 创建一个空白可变字符对象,不含有任何内容 |
| `public StringBuilder(String str)` |   根据字符串的内容,来创建可变字符对象   |

```java
StringBuilder sb = new StringBuilder("abc");
```

### 成员方法

|                 方法名                  |                       说明                        |
| :-------------------------------------: | :-----------------------------------------------: |
| `public StringBuilder append(任意类型)` |              添加数据,并返回对象本身              |
|    `public StringBuilder reverse()`     |                 反转容器中的内容                  |
|          `public int length()`          |             返回长度(字符出现的个数)              |
|       `public String toString()`        | 通过toString()就可以实现StringBuilder转换为String |

### 基本使用

```java
public class StringBuilderDemo3 {
    public static void main(String[] args) {
        //1.创建对象
        StringBuilder sb = new StringBuilder("abc");

        //2.添加元素
        /*sb.append(1);
        sb.append(2.3);
        sb.append(true);*/

        //反转
        sb.reverse();

        //获取长度
        int len = sb.length();
        System.out.println(len);


        //打印
        //普及：
        //因为StringBuilder是Java已经写好的类
        //java在底层对他做了一些特殊处理。
        //打印对象不是地址值而是属性值。
        System.out.println(sb);
    }
}
```

### 链式编程

> 当我们在调用一个方法的时候,不需要用变量接收他的结果,可以继续调用其他方法

```java
public class StringBuilderDemo4 {
    public static void main(String[] args) {
        //1.创建对象
        StringBuilder sb = new StringBuilder();

        //2.添加字符串
        sb.append("aaa").append("bbb").append("ccc").append("ddd"); //链式编程

        System.out.println(sb);//aaabbbcccddd

        //3.再把StringBuilder变回字符串
        String str = sb.toString();
        System.out.println(str);//aaabbbcccddd

    }
}
```

### 练习1：对称字符串 

需求：

​	键盘接受一个字符串，程序判断出该字符串是否是对称字符串，并在控制台打印是或不是

  	对称字符串：123321、111
  	
  	非对称字符串：123123

代码示例：

```java
public class StringBuilderDemo6 {
    //使用StringBuilder的场景：
    //1.字符串的拼接
    //2.字符串的反转

    public static void main(String[] args) {
        //1.键盘录入一个字符串
        Scanner sc = new Scanner(System.in);
        System.out.println("请输入一个字符串");
        String str = sc.next();

        //2.反转键盘录入的字符串
        String result = new StringBuilder().append(str).reverse().toString();

        //3.比较
        if(str.equals(result)){
            System.out.println("当前字符串是对称字符串");
        }else{
            System.out.println("当前字符串不是对称字符串");
        }

    }
}

```



### 练习2：拼接字符串 

需求：定义一个方法，把 int 数组中的数据按照指定的格式拼接成一个字符串返回。

​          调用该方法，并在控制台输出结果。

​          例如：数组为int[] arr = {1,2,3}; 

​          执行方法后的输出结果为：[1, 2, 3]

代码示例:

```java
package com.itheima.stringbuilderdemo;

public class StringBuilderDemo7 {
    public static void main(String[] args) {
        //1.定义数组
        int[] arr = {1,2,3};

        //2.调用方法把数组变成字符串
        String str = arrToString(arr);

        System.out.println(str);

    }


    public static String arrToString(int[] arr){
        StringBuilder sb = new StringBuilder();
        sb.append("[");

        for (int i = 0; i < arr.length; i++) {
            if(i == arr.length - 1){
                sb.append(arr[i]);
            }else{
                sb.append(arr[i]).append(", ");
            }
        }
        sb.append("]");

        return sb.toString();
    }
}

```

## StringJoiner

* StringJoiner跟StringBuilder一样，也可以看成是一个容器，创建之后里面的内容是可变的。
* 作用：提高字符串的操作效率，而且代码编写特别简洁，但是目前市场上很少有人用。 
* JDK8出现的

### 构造方法

| 方法名                                            | 说明                                                         |
| ------------------------------------------------- | ------------------------------------------------------------ |
| `public StringJoiner(间隔符号)`                   | 创建一个StringJoiner对象,指定拼接时的间隔符号                |
| `public StringJoiner(间隔符号,开始符号,结束符号)` | 创建一个StringJoiner对象,指定拼接时的间隔符号,开始符号,结束符号 |

### 成员方法

| 方法名                                | 说明                                       |
| ------------------------------------- | ------------------------------------------ |
| `public StringJoiner add(添加的内容)` | 添加数据,并返回对象本身                    |
| `public int length()`                 | 返回长度(字符出现的个数)                   |
| `public String toString()`            | 返回一个字符串(改字符串就是拼接之后的结果) |

### 基本使用

```java
//1.创建一个对象，并指定中间的间隔符号
StringJoiner sj = new StringJoiner("---");
//2.添加元素
sj.add("aaa").add("bbb").add("ccc");
//3.打印结果
System.out.println(sj);//aaa---bbb---ccc
```

```java
//1.创建对象
StringJoiner sj = new StringJoiner(", ","[","]");
//2.添加元素
sj.add("aaa").add("bbb").add("ccc");
int len = sj.length();
System.out.println(len);//15
//3.打印
System.out.println(sj);//[aaa, bbb, ccc]
String str = sj.toString();
System.out.println(str);//[aaa, bbb, ccc]
```

## 关于字符串的扩展

1. 字符串存储的内存原理

   String s = “abc”；直接赋值

   特点：

   ​	此时字符串abc是存在字符串常量池中的。

   ​	先检查字符串常量池中有没有字符串abc，如果有，不会创建新的，而是直接复用。如果没有abc，才会创建一个新的。

   所以，直接赋值的方式，代码简单，而且节约内存。

2. new出来的字符串

   看到new关键字，一定是在堆里面开辟了一个小空间。

   String s1 = new String（“abc”）；

   String s2 = “abc”；

   s1记录的是new出来的，在堆里面的地址值。

   s2是直接赋值的，所以记录的是字符串常量池中的地址值。

3. ==号比较的到底是什么？

   如果比较的是基本数据类型：比的是具体的数值是否相等。

   如果比较的是引用数据类型：比的是地址值是否相等。

   结论：==只能用于比较基本数据类型。不能比较引用数据类型。

4. 字符串拼接的底层原理

   拼接的时候没有变量,都是字符串

   触发字符串的优化机制

   在编译的时候就已经是最终的结果了     

## 集合

1. 集合长度可变
2. 可以存引用数据类型,**基本数据类型需要包装类**

### 包装类

| byte    | Byte      |
| ------- | --------- |
| short   | Short     |
| char    | Character |
| int     | Integer   |
| long    | Long      |
| float   | Float     |
| double  | Double    |
| boolean | Boolean   |



### ArrayList

泛型: 限定集合中存储数据的类型<E>

**<>中写入需要存储的数据类型,不能是基本数据类型**

- 打印对象不是地址值,而是集合中存储的数据内容
- 在展示的时候会拿两个[]把所有的数据进行包裹展示

```java
import java.util.ArrayList;

public class ArrayDemo1 {
    public static void main(String[] args) {
        //1.创建集合对象
        ArrayList<String> list = new ArrayList<>();
    }
}
```

#### 成员方法

|      |         方法名         |                说明                 |
| :--: | :--------------------: | :---------------------------------: |
|  增  |   `boolean add(E e)`   |   添加元素,返回值表示是否添加成功   |
|  删  | `boolean remove(E e)`  |   删除指定元素,返回值是否删除成功   |
|      | `E remove(int index)`  |  删除指定索引的元素,返回被删除元素  |
|  改  | `E set(int index,E e)` | 修改指定索引下的元素,返回原来的元素 |
|  查  |   `E get(int index)`   |         获取指定索引的元素          |
|      |      `int size()`      |  集合的长度,也就是集合中元素的个数  |

```java
import java.util.ArrayList;

public class ArrayDemo1 {
    public static void main(String[] args) {
        //1.创建集合对象
        ArrayList<String> list = new ArrayList<>();
        System.out.println(list);
        //2.添加数据
        list.add("aaa");
        list.add("bbb");
        list.add("ccc");
        list.add("eee");
        System.out.println("---增---");
        System.out.println(list); //[aaa, bbb, ccc, eee]
        //2.删除数据
        System.out.println("---删---");
        boolean result = list.remove("ccc");
        System.out.println(result); //true
        System.out.println(list); //[aaa, bbb, eee]
        boolean result1 = list.remove("ddd");  
        System.out.println(result1); //false
        System.out.println(list);// [aaa, bbb, eee]
        String result2 = list.remove(1);
        System.out.println(result2); //bbb
        System.out.println(list); //[aaa, eee]
        //3.修改数据
        System.out.println("---改---");
        list.set(0,"我喜欢你");
        System.out.println(list);// [我喜欢你, eee]
        //4.查找数据
        String result3 = list.get(0);
        System.out.println(result3); //我喜欢你
        //5.集合长度
        int result4 = list.size();
        System.out.println(result4); //2
    }
}
```



#### 练习

1.定义一个集合,添加字符串,并进行遍历,遍历格式参照: [元素1,元素2,元素3]

```java
import java.util.ArrayList;

public class ArrayListDemo1 {
    //定义一个集合,添加字符串,并进行遍历,遍历格式参照: [元素1,元素2,元素3]
    public static void main(String[] args) {
        //1.定义一个集合
        ArrayList<String> list = new ArrayList<>();
        //2.添加元素
        list.add("你好");
        list.add("我喜欢你");
        list.add("就是你");

        //3.遍历元素
        String result = "[";
        for (int i = 0; i < list.size(); i++) {
            if (i == list.size() -1){
                result = result + list.get(i) + "]";
            }else {
                result = result + list.get(i) + ",";
            }
        }

        //4.打印
        System.out.println(result);
    }
}
```

2.定义一个集合,并添加数字,并进行遍历,遍历格式参照: [元素1,元素2,元素3]

```java
import java.util.ArrayList;

public class ArrayListDemo2 {
    //定义一个集合,并添加数字,并进行遍历,遍历格式参照: [元素1,元素2,元素3]
    public static void main(String[] args) {
        //1.定义一个集合
        ArrayList<Integer> list = new ArrayList<>();
        //2.添加元素
        list.add(5);
        list.add(2);
        list.add(1);

        //3.遍历元素
        String result = "[";
        for (int i = 0; i < list.size(); i++) {
            if (i == list.size() -1){
                result = result + list.get(i) + "]";
            }else {
                result = result + list.get(i) + ",";
            }
        }

        //4.打印
        System.out.println(result);
    }
}
```

3.创建一个存储学生对象的集合，存储3个学生对象，使用程序实现在控制台遍历该集合

```java
import java.util.ArrayList;

public class ArrayListDemo3 {
    public static void main(String[] args) {
        //创建一个存储学生对象的集合，存储3个学生对象，使用程序实现在控制台遍历该集合
        //1.创建集合
        ArrayList<Student> list = new ArrayList<>();
        //2.创建学生对象
        Student stu1 = new Student("zhangsan",19);
        Student stu2 = new Student("lisi",18);
        Student stu3 = new Student("wangsu",16);
        //3.向集合添加元素
        list.add(stu1);
        list.add(stu2);
        list.add(stu3);
        //4.遍历集合
        for (int i = 0; i < list.size(); i++) {
            //i索引list.get(i) 元素/学生对象
            Student stu = list.get(i);
            System.out.println(stu.getName()+","+stu.getAge());
        }
    }
}
```

4.需求： 

1，main方法中定义一个集合，存入三个用户对象。 

   用户属性为：id，username，password    

2，要求：定义一个方法，根据id查找对应的学生信息。

   如果存在，返回索引

   如果不存在，返回-1

```java
import java.util.ArrayList;
import java.util.Scanner;

public class ArrayListDemo4 {
    /*
    * 需求：

      1，main方法中定义一个集合，存入三个用户对象。

         用户属性为：id，username，password

      2，要求：定义一个方法，根据id查找对应的学生信息。

         如果存在，返回索引

         如果不存在，返回-1
    * */
    public static void main(String[] args) {
        //1.定义一个集合
        ArrayList<User> list = new ArrayList<>();
        //2.创建用户对象
        User us1 = new User("wql","Wangqianlong",123);
        User us2 = new User("hx","hanxin",456);
        User us3 = new User("xz","xingzhen",789);
        //3.向集合中存储对象
        list.add(us1);
        list.add(us2);
        list.add(us3);
        //4.键盘输入查询id
        Scanner sc = new Scanner(System.in);
        System.out.print("请输入id：");
        String id = sc.next();
        int result = checkid(list,id);
        System.out.print("查询结果:"+result);


    }
    //4.定义方法，通过id查找对应学生信息
    public static int checkid(ArrayList<User> list,String id){
        //遍历获取每个id
        for (int i = 0; i < list.size(); i++) {
            User user = list.get(i); //获取集合每一个元素
            if (user.getId().equals(id)){
                return i;
            }
        }
        return -1;
    }
}
```

#### 学生管理系统

##### 需求：

​	采取控制台的方式去书写学生管理系统。

##### 分析：

##### 初始菜单：

```java
"-------------欢迎来到学生管理系统----------------"
"1：添加学生"
"2：删除学生"
"3：修改学生"
"4：查询学生"
"5：退出"
"请输入您的选择:"
```

###### 学生类：

​	属性：id、姓名、年龄、家庭住址

###### 添加功能：

​	键盘录入每一个学生信息并添加，需要满足以下要求：

* id唯一

###### 删除功能：

​	键盘录入要删除的学生id，需要满足以下要求：

* id存在删除
* id不存在，需要提示不存在，并回到初始菜单

###### 修改功能：

​	键盘录入要修改的学生id，需要满足以下要求

* id存在，继续录入其他信息
* id不存在，需要提示不存在，并回到初始菜单

###### 查询功能：

​	打印所有的学生信息，需要满足以下要求

* 如果没有学生信息，提示：当前无学生信息，请添加后再查询
* 如果有学生信息，需要按照以下格式输出。（不用过于纠结对齐的问题）

```java
id			姓名		年龄		家庭住址
ha001	张三		23		 南京
ha002	李四		24		 北京
ha003	王五		25		 广州
ha004	赵六	 	26		 深圳
```

- 案例需求

  ​	完成一个综合案例：学生管理系统。该系统主要功能如下：

  ​	添加学生：通过键盘录入学生信息，添加到集合中

  ​	删除学生：通过键盘录入要删除学生的学号，将该学生对象从集合中删除

  ​	修改学生：通过键盘录入要修改学生的学号，将该学生对象其他信息进行修改

  ​	查看学生：将集合中的学生对象信息进行展示

  ​	退出系统：结束程序

- 实现步骤

  1. 定义学生类，包含以下成员变量

     ​       private String sid            // 学生id

     ​       private String name       // 学生姓名

     ​       private String age          // 学生年龄

     ​       private String address   // 学生所在地

  2. 学生管理系统主界面的搭建步骤

     2.1 用输出语句完成主界面的编写
     2.2 用Scanner实现键盘输入
     2.3 用switch语句完成选择的功能
     2.4 用循环完成功能结束后再次回到主界面

  3. 学生管理系统的添加学生功能实现步骤

     3.1 定义一个方法，接收ArrayList<Student>集合
     3.2 方法内完成添加学生的功能
     ​         ①键盘录入学生信息
     ​         ②根据录入的信息创建学生对象
     ​         ③将学生对象添加到集合中
     ​         ④提示添加成功信息
     3.3 在添加学生的选项里调用添加学生的方法

  4. 学生管理系统的查看学生功能实现步骤

     4.1 定义一个方法，接收ArrayList<Student>集合
     4.2 方法内遍历集合，将学生信息进行输出
     4.3 在查看所有学生选项里调用查看学生方法

  5. 学生管理系统的删除学生功能实现步骤

     5.1 定义一个方法，接收ArrayList<Student>集合
     5.2 方法中接收要删除学生的学号
     5.3 遍历集合，获取每个学生对象
     5.4 使用学生对象的学号和录入的要删除的学号进行比较,如果相同，则将当前学生对象从集合中删除
     5.5 在删除学生选项里调用删除学生的方法

  6. 学生管理系统的修改学生功能实现步骤

     6.1 定义一个方法，接收ArrayList<Student>集合
     6.2 方法中接收要修改学生的学号
     6.3 通过键盘录入学生对象所需的信息，并创建对象
     6.4 遍历集合，获取每一个学生对象。并和录入的修改学生学号进行比较.如果相同，则使用新学生对象替换当前学生对象
     6.5 在修改学生选项里调用修改学生的方法

  7. 退出系统

     使用System.exit(0);退出JVM

```java
import java.util.ArrayList;
import java.util.Scanner;

public class StudentSystem {
    public static void main(String[] args) {
        ArrayList<Student> list = new ArrayList<>();
        loop: while (true) { //给循环起个标识符，让break跳出while循环
            System.out.println("----------欢迎来到学生管理系统----------");
            System.out.println("1.添加学生");
            System.out.println("2.删除学生");
            System.out.println("3.修改学生");
            System.out.println("4.查询学生");
            System.out.println("5.退出");
            System.out.print("请输入您的选择:");
            Scanner sc = new Scanner(System.in);
            String choose = sc.next();
            switch (choose){
                case "1" -> addStudent(list);
                case "2" -> deleteStudent(list);
                case "3" -> updateStudent(list);
                case "4" -> queryStudent(list);
                case "5" -> {
                    System.out.println("退出");
                    break loop; //单个break只会跳出switc循环，break+标识符可以跳出指定循环
                    //System.exit(0); 停止虚拟机运行
                }
                default -> System.out.println("没有这个选项");
            }
        }
    }
    //添加学生
    public static void addStudent(ArrayList<Student> list){
        Scanner sc = new Scanner(System.in);
        String id;
        while (true) {
            System.out.print("请输入学生id:");
            id = sc.next();
            int result = checkId(list,id);
            if (result >= 0){
                //表示存在，需要重新需入
                System.out.println("id已经存在，请重新录入");
            }else {
                //id不存在,表示可以继续使用
                break;
            }
        }
        System.out.print("请输入学生姓名:");
        String name = sc.next();
        System.out.print("请输入学生年龄:");
        int age = sc.nextInt();
        System.out.print("请输入学生家庭住址:");
        String adress = sc.next();
        //创建学生对象
        Student student = new Student(id,name,age,adress);
        //向集合中添加学生对象
        list.add(student);
        System.out.println("添加成功");
    }
    //删除学生
    public static void deleteStudent(ArrayList<Student> list){
        Scanner sc = new Scanner(System.in);
        System.out.print("请输入要删除学生的id:");
        String deleteId = sc.next();
        int result = checkId(list,deleteId);
        if (result >= 0){
            list.remove(result);
            System.out.println("删除成功");
        }else{
            System.out.println("没有要删除人的信息");
        }
    }
    //修改学生
    public static void updateStudent(ArrayList<Student> list){
        Scanner sc = new Scanner(System.in);
        System.out.print("请输入要修改学生的id:");
        String updateId = sc.next();
        int resultindex = checkId(list,updateId);
        if (resultindex == -1){
            //表示修改人不在集合中
            System.out.println("要修改的id:"+updateId+"不存在，请重新输入");
            return;
        }
        //修改人在集合中
        //获取要修改的学生对象
        Student student = list.get(resultindex);
        //输入信息进行修改
        System.out.print("请输入修改后的学生姓名:");
        String newName = sc.next();
        student.setName(newName);
        System.out.print("请输入修改后的学生年龄:");
        int newAge = sc.nextInt();
        student.setAge(newAge);
        System.out.print("请输入修改后的学生家庭住址:");
        String newAdress = sc.next();
        student.setAdress(newAdress);
        System.out.println("修改成功");
    }
    //查询学生
    public static void queryStudent(ArrayList<Student> list){
        if (list.size() == 0){
            System.out.println("当前无学生信息，请添加后再查询");
            return; //结束本方法
        }
        //有学生信息，按照以下格式输出
        System.out.println("id\t\t姓名\t年龄\t家庭住址");
        for (int i = 0; i < list.size(); i++) {
            Student student = list.get(i);
            System.out.println(student.getId()+"\t"+student.getName()+"\t"+student.getAge()+"\t"+student.getAdress());
        }
    }
    //通过id查询是否在集合中
    public static int checkId(ArrayList<Student> list,String id){
        for (int i = 0; i < list.size(); i++) {
            Student student = list.get(i);
            if (student.getId().equals(id)){
                return i;
            }
        }
        //不存在
        return -1;
    }
}
```

#### 学生管理系统升级

##### 需求：

​	为学生管理系统书写一个登陆、注册、忘记密码的功能。

​	只有用户登录成功之后，才能进入到学生管理系统中进行增删改查操作。

##### 分析：

###### 登录界面：

```java
System.out.println("欢迎来到学生管理系统");
System.out.println("请选择操作1登录 2注册 3忘记密码");
```

###### 用户类：

​	属性：用户名、密码、身份证号码、手机号码

###### 注册功能：

​	1，用户名需要满足以下要求：

​		验证要求：

​			用户名唯一

​			用户名长度必须在3~15位之间 

​			只能是字母加数字的组合，但是不能是纯数字

​	2，密码键盘输入两次，两次一致才可以进行注册。

​	3，身份证号码需要验证。

​		验证要求：

​			长度为18位

​			不能以0为开头

​			前17位，必须都是数字

​			最为一位可以是数字，也可以是大写X或小写x

​	4，手机号验证。

​		验证要求：

​			长度为11位

​			不能以0为开头

​			必须都是数字

###### 登录功能：

​	1，键盘录入用户名

​	2，键盘录入密码

​	3，键盘录入验证码

验证要求：

​		用户名如果未注册，直接结束方法，并提示：用户名未注册，请先注册

​		判断验证码是否正确，如不正确，重新输入

​		再判断用户名和密码是否正确，有3次机会

###### 忘记密码：

​       1，键盘录入用户名，判断当前用户名是否存在，如不存在，直接结束方法，并提示：未注册

​	2，键盘录入身份证号码和手机号码

​	3，判断当前用户的身份证号码和手机号码是否一致，

​			如果一致，则提示输入密码，进行修改。

​			如果不一致，则提示：账号信息不匹配，修改失败。

###### 验证码规则：

​	长度为5

​	由4位大写或者小写字母和1位数字组成，同一个字母可重复

​	数字可以出现在任意位置

比如：

​	aQa1K

```java
import java.util.ArrayList;
import java.util.Random;
import java.util.Scanner;

public class App {
    public static void main(String[] args) {
        ArrayList<User> list = new ArrayList<>();
        while (true){
            System.out.println("---------欢迎来到学生管理系统升级版---------");
            System.out.println("请选择操作：1登陆，2注册，3忘记密码");
            Scanner sc = new Scanner(System.in);
            System.out.print("请输入选择:");
            String choose = sc.next();
            switch (choose){
                case "1" -> Login(list);
                case "2" -> register(list);
                case "3" -> forgetPassword(list);
                case "4" -> {
                    System.out.println("谢谢使用，再见！");
                    System.exit(0);
                }
                default -> System.out.println("没有这个选项");
            }
        }
    }
    //登陆
    public static void Login(ArrayList<User> list){
        //1.键盘录入用户名
        Scanner sc =new Scanner(System.in);
        for (int i = 0; true; i++) {
            System.out.print("请输入用户名:");
            String username = sc.next();
            int checkIndex = checkIndex(list,username);
            if (checkIndex == -1){
                System.out.println("用户名"+username+"没有注册，请先注册再登陆");
                return;
            }
            //2.键盘输入密码
            System.out.println("请输入密码:");
            String password = sc.next();
            //3.键盘输入验证码
            String rightCode = GetCode();
            System.out.println("当前正确验证码:"+rightCode);
            while (true) {
                System.out.print("请输入验证码:");
                String code = sc.next();
                if (code.equalsIgnoreCase(rightCode)){
                    System.out.println("验证码正确");
                    break;
                }else {
                    System.out.println("验证码错误，请重新输入");
                }
            }
            //验证用户名和密码是否正确
            //将上面输入的数据封装为一个对象
            User InfoUser = new User(username,password,null,null);
            boolean Result = checkInfo(list,InfoUser);
            if (Result){
                System.out.println("登陆成功");
                break;
            }else {
                System.out.println("登陆失败,用户名或密码错误");
                if (i == 2){
                    System.out.println("当前账号"+username+"被锁定");
                    return;
                }else {
                    System.out.println("用户名或密码错误，还剩"+(2-i)+"次");
                }
            }
        }
    }
    //注册
    public static void register(ArrayList<User> list){
        //1.键盘录入用于名
        //用户名需要满足以下要求：
        //验证要求：
        //先验证格式是否正确，再验证是否唯一
        //用户名长度必须在3~15位之间
        //只能是字母加数字的组合，但是不能是纯数字
        //用户名唯一
        Scanner sc = new Scanner(System.in);
        String name;
        while (true) {
            System.out.print("请输入用户名:");
            name = sc.next();
            boolean result = checkUsernmae(name);
            if (!result){
                System.out.println("用户名格式不满足条件，请重新输入!");
                continue;
            }
            //判断用户名是否唯一
            int resultIndex = checkIndex(list,name);
            if (resultIndex >= 0){
                //用户名存在
                System.out.println("用户名"+name+"存在"+"，请重新输入。");
            }else {
                //用户名不存在，可以继续录入
                System.out.println("用户名"+name+"可以使用。");
                break;
            }
        }
        //2.键盘输入密码
        //密码键盘输入两次，两次一致才可以进行注册。
        String password;
        while (true) {
            System.out.print("请输入要注册的密码:");
            password = sc.next();
            System.out.print("请再次输入要注册的密码:");
            String againPassword = sc.next();
            if (!password.equals(againPassword)){
                System.out.println("两次密码输入不一致，请重新输入！");
            }else{
                System.out.println("两次密码输入一致，继续录入其他数据");
                break;
            }
        }
        //3.键盘输入身份证号
        //验证要求：
        //长度为18位
        //不能以0为开头
        //前17位，必须都是数字
        //最为一位可以是数字，也可以是大写X或小写x
        String personId;
        while (true) {
            System.out.print("请输入身份证号:");
            personId = sc.next();
            boolean result = checkpersonID(personId);
            if (!result){
                System.out.println("身份证格式不正确，请重新输入!");
            }else {
                System.out.println("身份证格式正确，请继续输入其他信息");
                break;
            }
        }
        //4.键盘输入手机号码
        //验证要求：
        //长度为11位
        //不能以0为开头
        //必须都是数字
        String userPhone;
        while (true) {
            System.out.print("请输入注册手机号:");
            userPhone = sc.next();
            boolean resultnumber = checkPhoneNumber(userPhone);
            if (!resultnumber){
                System.out.println("手机号格式错误，请重新输入");
            }else {
                System.out.println("手机号正确");
                break;
            }
        }
        //创建用户对象
        User user = new User(name,password,personId,userPhone);
        //把用户对象添加到集合中
        list.add(user);
        System.out.println("注册成功");
        pringList(list);
    }
    //打印集合的学生对象
    public static void pringList(ArrayList<User> list){
        for (User user : list) {
            System.out.println(user.getUsername() + user.getPassword() + user.getPersonId() + user.getPhoneNumber());
        }
    }
    //忘记密码
    public static void forgetPassword(ArrayList<User> list){
        Scanner sc = new Scanner(System.in);
        System.out.print("请输入用户名:");
        String name =sc.next();
        int Index = checkIndex(list,name);
        if (Index == -1){
            System.out.println("用户不存在，请先注册");
            return;
        }
        //键盘录入身份证号和手机号码
        System.out.print("请输入身份证号:");
        String personID = sc.next();
        System.out.print("请输入手机号码:");
        String Phone = sc.next();
        //判断当前用户的身份证号码和手机号码是否一致，
        //封装用户的身份证号码和手机号码
        User InfoUser = new User(null,null,personID,Phone);
        boolean result = CheckInfo(list,InfoUser,Index);
        if (!result){
            System.out.println("账号信息不匹配");
            return;
        }
        System.out.println("身份确认，可以修改密码");
        String newPassword;
        while (true) {
            System.out.print("请输入修改后的密码:");
            newPassword = sc.next();
            System.out.print("请再次输入密码:");
            String AgainNewPassword = sc.next();
            if (newPassword.equals(AgainNewPassword)){
                System.out.println("两次密码输入一致");
                break;
            }else{
                System.out.println("两次密码不一致，请重新输入");
                continue;
            }
        }
        //修改数据
        changeDate(list,Index,newPassword);
        


    }
    //判断用户名格式
    public static boolean checkUsernmae(String username){
        //将字符串变为字符数组
        char[] arr = username.toCharArray();
        //计数器
        int small = 0;
        int big = 0;
        int number = 0;
        for (int i = 0; i < arr.length; i++) {
            if (arr[i] <= 'z' && arr[i] >= 'a'){
                small++;
            } else if (arr[i] <= 'Z' && arr[i] >= 'A') {
                big++;
            } else if (arr[i] <= '9' && arr[i] >= '0') {
                number++;
            }
        }
        //用户名长度必须在3~15位之间
        //只能是字母加数字的组合，但是不能是纯数字
        if ((small+big+number) >= 3 && (small+big+number) <=15){
            if (small > 0 || big > 0){
                return number != 0;
            }else {
                return false;
            }
        }else {
            return false;
        }
    }
    //判断用户名是否唯一
    public static int checkIndex(ArrayList<User> list,String name){
        for (int i = 0; i < list.size(); i++) {
            User user = list.get(i);
            if (user.getUsername().equals(name)){
                return i;
            }
        }
        //不存在,唯一
        return -1;
    }
    //判断身份证号码
    public static boolean checkpersonID(String personId){
        //长度为18位
        if (personId.length() != 18){
            return false;
        }
        //不能以0为开头
        if (personId.startsWith("0")){
            return false;
        }
        //前17位，必须都是数字
        for (int i = 0; i < personId.length(); i++) {
            char c = personId.charAt(i);
            if (!(c >= '0' && c <= '9')){
                return false;
            }
        }
        //最为一位可以是数字，也可以是大写X或小写x
        char endChar = personId.charAt(personId.length()-1);
        if ((endChar >= '0' && endChar <= '9') || (endChar == 'X') || (endChar == 'x')){
            return true;
        }else {
            return false;
        }
    }
    //判断手机号码
    public static boolean checkPhoneNumber(String phonenumber){
        //验证要求：
        //长度为11位
        if (phonenumber.length() != 11){
            return false;
        }
        //不能以0为开头
        if (phonenumber.startsWith("0")){
            return false;
        }
        //必须都是数字
        for (int i = 0; i < phonenumber.length(); i++) {
            char c = phonenumber.charAt(i);
            if (!(c >= '0' && c <= '9')){
                return false;
            }
        }
        return true;
    }

    //生成一个验证码
    //长度为5
    //由4位大写或者小写字母和1位数字组成，同一个字母可重复
    //数字可以出现在任意位置
    private static String GetCode(){
        //1.创建一个集合添加所有的大写和小写字母
        ArrayList<Character> list = new ArrayList<>();
        for (int i = 0; i < 26; i++) {
            list.add((char)('a' + i));
            list.add((char)('A' + i));
        }
        //2.随机抽取4个字符
        StringBuilder sb =new StringBuilder();
        Random r = new Random();
        for (int i = 0; i < 4; i++) {
            //获取随机索引
            int index = r.nextInt(list.size());
            //利用随机索引获取字符
            sb.append(list.get(index));
        }
        //3.把一个随机数字放到末尾
        int number = r.nextInt(10);
        sb.append(number);

        //4.把字符串变成字符数组，在数组中修改，然后再穿件一个新的字符串
        char[] arr = sb.toString().toCharArray();
        //拿着最后一个索引，跟随机索引交换
        int Index = r.nextInt(arr.length);
        //交换索引指向的元素交换
        char temp = arr[Index];
        arr[Index] = arr[arr.length-1];
        arr[arr.length-1] = temp;
        //重新变为字符串并且返回
        return new String(arr);
    }
    //校验用户名和密码
    public static boolean checkInfo(ArrayList<User> list,User InfoUser){
        //遍历集合，判断用户名是否存在
        int Index = checkIndex(list,InfoUser.getUsername());
        if (Index == -1){
            //用户名不存在
            return false;
        }else {
            User user = list.get(Index);
            return InfoUser.getPassword().equals(user.getPassword());
        }
    }
    //校验用户的身份证号码和手机号码
    public static boolean CheckInfo(ArrayList<User> list,User InfoUser,int index){
        User user = list.get(index);
        if (user.getPersonId().equals(InfoUser.getPersonId())){
            return user.getPhoneNumber().equals(InfoUser.getPhoneNumber());
        }else {
            return false;
        }
    }
    //修改密码
    public static void changeDate(ArrayList<User> list,int index,String change){
        User user = list.get(index);
        user.setPassword(change);
        System.out.println("修改数据成功");
    }
}

```

## static 静态变量

> static表示静态,是java中的一个修饰符,可以修饰成员方法,成员变量

### 静态变量

被static修饰的成员变量,叫做静态变量

特点:

- 被该类所有对象**共享**
- 不属于对象,属于**类**
- 静态变量是随着类的加载而加载,放于堆内存中的静态区,优先于对象出现的

调用方式:

- **类名调用(推荐)**
- 对象名调用

**定义格式**

```java
修饰符 static 数据类型 变量名 = 初始值；    
```

**举例**

```java
public class Student {
    public static String schoolName = "常州大学"； // 属于类，只有一份。
    // .....
}
```

**静态成员变量的访问:**

**格式：类名.静态变量**

```java
public static void  main(String[] args){
    System.out.println(Student.schoolName); // 常州大学
    Student.schoolName = "程序员";
    System.out.println(Student.schoolName); // 程序员
}
```

### 实例变量及其访问

无static修饰的成员变量属于每个对象的，  这个成员变量叫**实例变量**，之前我们写成员变量就是实例成员变量。

**需要注意的是**：实例成员变量属于每个对象，必须创建类的对象才可以访问。   

**格式：对象.实例成员变量**

### 静态方法

被static修饰的成员方法,叫做静态方法

>静态方法的生命周期与类相同，在类定义的时候静态方法就被分配和装载入内存中，当本进程结束时，才会随之销毁。
>
>非静态方法的生命周期和类的实例化对象相同，只有当类实例化了一个对象，非静态方法才会被创建，而当这个对象被销毁时，非静态方法也马上被销毁。

特点:

- 多用在测试类和工具类中
- javabean类中很少会用

调用方式:

- **类名调用(推荐)**
- 对象名调用

**举例**

```java
public class Student{
    private Student(){}  //私有化构造方法 目的:不让外界创建他的对象
    public static String schoolName = "常州大学"； // 属于类，只有一份。
    // .....
    public static void study(){
    	System.out.println("我们都是程序员");   
    }
}
```

**静态成员变量的访问:**

**格式：类名.静态方法**

```java
public static void  main(String[] args){
    Student.study();
}
```

### Javabean类,测试类,工具类
> - Javabean类: 用来描述一类事物的类,比如,Student,Teacher等
> - 测试类: 用来检查其他类是否书写正确,带有main方法的类,是程序的入口
> - 工具类: 不是用来描述一类事物的,而是帮我们做一些事情的类
>
> **工具类:**
>
> 1. 类名见名知意
> 2. 私有化构造方法 **目的:不让外界创建他的对象**
> 3. 方法定义为静态
>
> 练习:
>
> > 编写一个数组的工具类:ArrayUtil
> >
> > - 提供一个工具类方法printArr,用于放回整数数组的内容 ,返回的字符串格式如下[10,20,50] (只考虑整数数组,且只考虑一维数组)
> > - 提供一个工具类getAerage,用于返回平均分.(只考虑浮点型数组,且只考虑一维数组)
>
> ```java
> public class ArrayUtil {
>     private ArrayUtil(){} //私有化构造方法 目的:不让外界创建他的对象
>     //提供一个工具类方法printArr,用于放回整数数组的内容 ,返回的字符串格式如下[10,20,50] (只考虑整数数组,且只考虑一维数组)
>     //需要定义为静态，方便调用
>     public static String  printArr(int[] arr){
>         StringBuilder sb = new StringBuilder();
>         sb.append("[");
> 
>         for (int i = 0; i < arr.length; i++) {
>             if(i == arr.length - 1){
>                 sb.append(arr[i]);
>             }else{
>                 sb.append(arr[i]).append(", ");
>             }
>         }
>         sb.append("]");
>         return sb.toString();
>     }
>     //提供一个工具类getAerage,用于返回平均分.(只考虑浮点型数组,且只考虑一维数组)
>     public static double getAerage(double[] arr){
>         double sum = 0;
>         for (int i = 0; i < arr.length; i++) {
>             sum += arr[i];
>         }
>         return sum/arr.length;
>     }
> }
> ```
>

### 实例方法及其访问

无static修饰的成员方法属于每个对象的，这个成员方法也叫做**实例方法**。

**需要注意的是**：实例方法是属于每个对象，必须创建类的对象才可以访问。  

**格式：对象.实例方法**

**示例**：

```java
public class Student {
    // 实例变量
    private String name ;
    // 2.方法：行为
    // 无 static修饰，实例方法。属于每个对象，必须创建对象调用
    public void run(){
        System.out.println("学生可以跑步");
    }
	// 无 static修饰，实例方法
    public  void sleep(){
        System.out.println("学生睡觉");
    }
    public static void study(){
        
    }
}
```

```java
public static void main(String[] args){
    // 创建对象 
    Student stu = new Student ;
    stu.name = "张三";
    // Student.sleep();// 报错，必须用对象访问。
    stu.sleep();
    stu.run();
}
```

### 注意事项

- 静态方法只能访问静态变量和静态方法,不能调用非静态变量和非静态方法
- 非静态方法可以访问静态变量或者静态方法,也可以访问非静态的成员变量和非静态的成员方法
- **静态方法中没有this关键字**

## main方法

- public : 被JVM调用,访问权限足够大
- static : 被JVM调用,不用创建对象,直接类名访问,因为main方法是静态的,所以测试类中的其他方法也需要是静态的
- void : 被JVM调用,不需要给JVM返回值
- main : 一个通用的名称,虽然不是关键字,但是被JVM识别
- String[] args : 以前用于键盘录入数据,现在没有作用

## 继承

### 概述

#### 引入

假如我们要定义如下类:
学生类,老师类和工人类，分析如下。

1. 学生类
   属性:姓名,年龄
   行为:吃饭,睡觉

2. 老师类
   属性:姓名,年龄，薪水
   行为:吃饭,睡觉，教书

3. 班主任
   属性:姓名,年龄，薪水
   行为:吃饭,睡觉，管理

如果我们定义了这三个类去开发一个系统，那么这三个类中就存在大量重复的信息（属性:姓名，年龄。行为：吃饭，睡觉）。这样就导致了相同代码大量重复，代码显得很臃肿和冗余，那么如何解决呢？

假如多个类中存在相同属性和行为时，我们可以将这些内容抽取到单独一个类中，那么多个类无需再定义这些属性和行为，只要**继承**那一个类即可。

其中，多个类可以称为**子类**，单独被继承的那一个类称为**父类**、**超类（superclass）**或者**基类**。

#### 继承的含义

继承描述的是事物之间的所属关系，这种关系是：`is-a` 的关系。例如，兔子属于食草动物，食草动物属于动物。可见，父类更通用，子类更具体。我们通过继承，可以使多种事物之间形成一种关系体系。

**继承**：就是子类继承父类的**属性**和**行为**，使得子类对象可以直接具有与父类相同的属性、相同的行为。子类可以直接访问父类中的**非私有**的属性和行为。

#### 继承的好处

1. 提高**代码的复用性**（减少代码冗余，相同代码重复利用）。
2. 使类与类之间产生了关系。

### 继承的格式

通过 `extends` 关键字，可以声明一个子类继承另外一个父类，定义格式如下：

```java
class 父类 {
	...
}

class 子类 extends 父类 {
	...
}
```

**需要注意：Java是单继承的，一个类只能继承一个直接父类，跟现实世界很像，但是Java中的子类是更加强大的。**

**java只支持单继承(一个儿子一个爸爸),不支持多继承(不允许一个儿子多个爸爸),但支持多层继承**

#### 多层继承

子类A 继承 父类B, 父类B 可以继承 父类C

> 父类B 是子类A 的直接父类
>
> 父类C 是子类A 的间接父类

每一个类都直接或间接的继承于Object

没有父类时候虚拟机默认继承于Object类中

```java
public class A extends Object {

}
```

### 继承案例

#### 案例

请使用继承定义以下类:

1. 学生类
   属性:姓名,年龄
   行为:吃饭,睡觉
2. 老师类
   属性:姓名,年龄，薪水
   行为:吃饭,睡觉，教书
3. 班主任
   属性:姓名,年龄，薪水
   行为:吃饭,睡觉，管理

#### 案例代码实现

**1.父类Human类**

  ```java
 public class Human {
    // 合理隐藏
    private String name ;
    private int age ;
	
    // 合理暴露
    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public int getAge() {
        return age;
    }

    public void setAge(int age) {
        this.age = age;
    }
 }
  ```

**2.子类Teacher类**

  ```java
public class Teacher extends Human {
    // 工资
    private double salary ;
    
    // 特有方法
    public void teach(){
        System.out.println("老师在认真教技术！")；
    }

    public double getSalary() {
        return salary;
    }

    public void setSalary(double salary) {
        this.salary = salary;
    }
}
  ```

**3.子类Student类**

  ```java
public class Student extends Human{
 
}
  ```

**4.子类BanZhuren类**

```java 
public class Teacher extends Human {
    // 工资
    private double salary ;
    
       // 特有方法
    public void admin(){
        System.out.println("班主任强调纪律问题！")；
    }
    
    public double getSalary() {
        return salary;
    }

    public void setSalary(double salary) {
        this.salary = salary;
    }
}
```


**5.测试类**

  ```java
  public class Test {
      public static void main(String[] args) {
          Teacher dlei = new Teacher();
          dlei.setName("播仔");
          dlei.setAge("31");
          dlei.setSalary(1000.99);
          System.out.println(dlei.getName());
          System.out.println(dlei.getAge());
          System.out.println(dlei.getSalary());
          dlei.teach();
          
          BanZhuRen linTao = new BanZhuRen();
          linTao.setName("灵涛");
          linTao.setAge("28");
          linTao.setSalary(1000.99);
          System.out.println(linTao.getName());
          System.out.println(linTao.getAge());
          System.out.println(linTao.getSalary());
          linTao.admin();

          Student xugan = new Student();
          xugan.setName("播仔");
          xugan.setAge("31");
          //xugan.setSalary(1000.99); // xugan没有薪水属性，报错！
          System.out.println(xugan.getName());
          System.out.println(xugan.getAge());



      }
  }
  ```

#### 小结

1.继承实际上是子类相同的属性和行为可以定义在父类中，子类特有的属性和行为由自己定义，这样就实现了相同属性和行为的重复利用，从而提高了代码复用。

2.子类继承父类，就可以直接得到父类的成员变量和方法。是否可以继承所有成分呢

### 子类不能继承的内容

#### 引入

并不是父类的所有内容都可以给子类继承的：

| 构造方法 | public : 不能继承 |                     private : 不能继承                     |
| :------: | :---------------: | :--------------------------------------------------------: |
| 成员变量 |  public : 能继承  | private : 能继承(通过get/set方法访问父类的private成员变量) |
| 成员方法 |  public : 能继承  |                     private : 不能继承                     |

Java中子类不会继承父类static变量和方法。因为静态资源是属于类本身的。但是子类可以访问到的。

子类和父类中同名的static变量和方法都是相互独立的，并不存在任何的重写的关系。

#### 演示代码

```java
public class Demo03 {
    public static void main(String[] args) {
        Zi z = new Zi();
        System.out.println(z.num1);
//		System.out.println(z.num2); // 私有的子类无法使用
        // 通过get/set方法访问父类的private成员变量
        System.out.println(z.getNum2());

        z.show1();
        // z.show2(); // 私有的子类无法使用
    }
}

class Fu {
    public int num1 = 10;
    private int num2 = 20;

    public void show1() {
        System.out.println("show1");
    }

    private void show2() {
        System.out.println("show2");
    }

    public int getNum2() {
        return num2;
    }

    public void setNum2(int num2) {
        this.num2 = num2;
    }
}

class Zi extends Fu {
}
```

### 继承后的特点—成员变量

当类之间产生了继承关系后，其中各类中的成员变量，又产生了哪些影响呢？

#### 成员变量不重名

如果子类父类中出现**不重名**的成员变量，这时的访问是**没有影响的**。代码如下：

```java
class Fu {
	// Fu中的成员变量
	int num = 5;
}
class Zi extends Fu {
	// Zi中的成员变量
	int num2 = 6;
  
	// Zi中的成员方法
	public void show() {
		// 访问父类中的num
		System.out.println("Fu num="+num); // 继承而来，所以直接访问。
		// 访问子类中的num2
		System.out.println("Zi num2="+num2);
	}
}
class Demo04 {
	public static void main(String[] args) {
        // 创建子类对象
		Zi z = new Zi(); 
      	// 调用子类中的show方法
		z.show();  
	}
}

演示结果：
Fu num = 5
Zi num2 = 6
```

#### 成员变量重名

如果子类父类中出现**重名**的成员变量，这时的访问是**有影响的**。代码如下：

```java
class Fu1 {
	// Fu中的成员变量。
	int num = 5;
}
class Zi1 extends Fu1 {
	// Zi中的成员变量
	int num = 6;
  
	public void show() {
		// 访问父类中的num
		System.out.println("Fu num=" + num);
		// 访问子类中的num
		System.out.println("Zi num=" + num);
	}
}
class Demo04 {
	public static void main(String[] args) {
      	// 创建子类对象
		Zi1 z = new Zi1(); 
      	// 调用子类中的show方法
		z1.show(); 
	}
}
演示结果：
Fu num = 6
Zi num = 6
```

**子父类中出现了同名的成员变量时，子类会优先访问自己对象中的成员变量。如果此时想访问父类成员变量如何解决呢？我们可以使用super关键字。**

#### super访问父类成员变量

子父类中出现了同名的成员变量时，在子类中需要访问父类中非私有成员变量时，需要使用`super` 关键字，修饰父类成员变量，类似于之前学过的 `this` 。

需要注意的是：**super代表的是父类对象的引用，this代表的是当前对象的引用。**

**使用格式：**

```java
super.父类成员变量名
```

子类方法需要修改，代码如下：

```java
class Fu {
	// Fu中的成员变量。
	int num = 5;
}

class Zi extends Fu {
	// Zi中的成员变量
	int num = 6;
  
	public void show() {
        int num = 1;
      
        // 访问方法中的num
        System.out.println("method num=" + num);
        // 访问子类中的num
        System.out.println("Zi num=" + this.num);
        // 访问父类中的num
        System.out.println("Fu num=" + super.num);
	}
}

class Demo04 {
	public static void main(String[] args) {
      	// 创建子类对象
		Zi1 z = new Zi1(); 
      	// 调用子类中的show方法
		z1.show(); 
	}
}

演示结果：
method num=1
Zi num=6
Fu num=5
```

> 小贴士：Fu 类中的成员变量是非私有的，子类中可以直接访问。若Fu 类中的成员变量私有了，子类是不能直接访问的。通常编码时，我们遵循封装的原则，使用private修饰成员变量，那么如何访问父类的私有成员变量呢？对！可以在父类中提供公共的getXxx方法和setXxx方法。

### 继承后的特点—成员方法

当类之间产生了关系，其中各类中的成员方法，又产生了哪些影响呢？

#### 成员方法不重名

如果子类父类中出现**不重名**的成员方法，这时的调用是**没有影响的**。对象调用方法时，会先在子类中查找有没有对应的方法，若子类中存在就会执行子类中的方法，若子类中不存在就会执行父类中相应的方法。代码如下：

```java
class Fu {
	public void show() {
		System.out.println("Fu类中的show方法执行");
	}
}
class Zi extends Fu {
	public void show2() {
		System.out.println("Zi类中的show2方法执行");
	}
}
public  class Demo05 {
	public static void main(String[] args) {
		Zi z = new Zi();
     	//子类中没有show方法，但是可以找到父类方法去执行
		z.show(); 
		z.show2();
	}
}
```

#### 成员方法重名

如果子类父类中出现**重名**的成员方法，则创建子类对象调用该方法的时候，**子类对象会优先调用自己的方法**。

代码如下：

```java
class Fu {
	public void show() {
		System.out.println("Fu show");
	}
}
class Zi extends Fu {
	//子类重写了父类的show方法
	public void show() {
		System.out.println("Zi show");
	}
}
public class ExtendsDemo05{
	public static void main(String[] args) {
		Zi z = new Zi();
     	// 子类中有show方法，只执行重写后的show方法
		z.show();  // Zi show
	}
}
```

### 方法重写

#### 概念

**方法重写** ：子类中出现与父类一模一样的方法时（返回值类型，方法名和参数列表都相同），会出现覆盖效果，也称为重写或者复写。**声明不变，重新实现**。

本质:覆盖虚方法表中的方法

#### 使用场景与案例

发生在子父类之间的关系。
子类继承了父类的方法，但是子类觉得父类的这方法不足以满足自己的需求，子类重新写了一个与父类同名的方法，以便覆盖父类的该方 法。

例如：我们定义了一个动物类代码如下：

```java
public class Animal  {
    public void run(){
        System.out.println("动物跑的很快！");
    }
    public void cry(){
        System.out.println("动物都可以叫~~~");
    }
}
```

然后定义一个猫类，猫可能认为父类cry()方法不能满足自己的需求

代码如下：

```java
public class Cat extends Animal {
    public void cry(){
        System.out.println("我们一起学猫叫，喵喵喵！喵的非常好听！");
    }
}

public class Test {
	public static void main(String[] args) {
      	// 创建子类对象
      	Cat ddm = new Cat()；
        // 调用父类继承而来的方法
        ddm.run();
      	// 调用子类重写的方法
      	ddm.cry();
	}
}
```

#### @Override重写注解

* @Override:注解，重写注解校验！

* 这个注解标记的方法，就说明这个方法必须是重写父类的方法，否则编译阶段报错。

* 建议重写都加上这个注解，一方面可以提高代码的可读性，一方面可以防止重写出错！

  加上后的子类代码形式如下：

  ``` java
  public class Cat extends Animal {
       // 声明不变，重新实现
      // 方法名称与父类全部一样，只是方法体中的功能重写写了！
      @Override
      public void cry(){
          System.out.println("我们一起学猫叫，喵喵喵！喵的非常好听！");
      }
  }
  ```


#### 注意事项

1. 方法重写是发生在子父类之间的关系。
2. 子类方法覆盖父类方法，必须要保证权限大于等于父类权限。(空着不写<protected<public)
3. 子类方法覆盖父类方法，返回值类型、函数名和参数列表都要一模一样。
4. 只有被添加到虚方法表中的方法才能被重写(private,static,final修饰的方法都无法添加到虚方法表中)

### 继承后的特点—构造方法

#### 引入

当类之间产生了关系，其中各类中的构造方法，又产生了哪些影响呢？
首先我们要回忆两个事情，构造方法的定义格式和作用。

1. 构造方法的名字是与类名一致的。所以子类是无法继承父类构造方法的。
2. 构造方法的作用是初始化对象成员变量数据的。所以子类的初始化过程中，必须先执行父类的初始化动作。子类的构造方法中默认有一个`super()` ，表示调用父类的构造方法(无参构造)，父类成员变量初始化后，才可以给子类使用。（**先有爸爸，才能有儿子**）

**继承后子类构方法器特点:子类所有构造方法的第一行都会默认先调用父类的无参构造方法**

> 原因:
>
> - 子类初始化前,有可能会使用到父类中的数据,如果父类没有完成初始化,子类将无法使用父类的数据
> - 子类初始化之前,一定要调用父类构造方法先完成父类数据空间的初始化

#### 案例演示

按如下需求定义类:

1. 人类
   成员变量: 姓名,年龄
   成员方法: 吃饭
2. 学生类
   成员变量: 姓名,年龄,成绩
   成员方法: 吃饭

代码如下：

```java
class Person {
    private String name;
    private int age;

    public Person() {
        System.out.println("父类无参");
    }

    // get/set省略
}

class Student extends Person {
    private double score;

    public Student() {
        //super(); // 调用父类无参,默认就存在，可以不写，必须再第一行
        System.out.println("子类无参");
    }
    
     public Student(double score) {
        //super();  // 调用父类无参,默认就存在，可以不写，必须再第一行
        this.score = score;    
        System.out.println("子类有参");
     }

}

public class Demo07 {
    public static void main(String[] args) {
        Student s1 = new Student();
        System.out.println("----------");
        Student s2 = new Student(99.9);
    }
}

输出结果：
父类无参
子类无参
----------
父类无参
子类有参
```

#### 小结

* 子类构造方法执行的时候，都会在第一行默认先调用父类无参数构造方法一次。
* 子类构造方法的第一行都隐含了一个**super()**去调用父类无参数构造方法，**super()**可以省略不写。

### super(...)和this(...)

#### 引入

请看上节中的如下案例：

```java 
class Person {
    private String name;
    private int age;

    public Person() {
        System.out.println("父类无参");
    }

    // getter/setter省略
}

class Student extends Person {
    private double score;

    public Student() {
        //super(); // 调用父类无参构造方法,默认就存在，可以不写，必须再第一行
        System.out.println("子类无参");
    }
    
     public Student(double score) {
        //super();  // 调用父类无参构造方法,默认就存在，可以不写，必须再第一行
        this.score = score;    
        System.out.println("子类有参");
     }
      // getter/setter省略
}

public class Demo07 {
    public static void main(String[] args) {
        // 调用子类有参数构造方法
        Student s2 = new Student(99.9);
        System.out.println(s2.getScore()); // 99.9
        System.out.println(s2.getName()); // 输出 null
        System.out.println(s2.getAge()); // 输出 0
    }
}
```

我们发现，子类有参数构造方法只是初始化了自己对象中的成员变量score，而父类中的成员变量name和age依然是没有数据的，怎么解决这个问题呢，我们可以借助与super(...)去调用父类构造方法，以便初始化继承自父类对象的name和age.

#### super和this的用法格式

super和this完整的用法如下

```java
this.成员变量    	--    本类的
super.成员变量    	--    父类的

this.成员方法名()  	--    本类的    
super.成员方法名()   --    父类的
```

接下来我们使用调用构造方法格式：

```java
super(...) -- 调用父类的构造方法，根据参数匹配确认
this(...) -- 调用本类的其他构造方法，根据参数匹配确认
```

- this : 理解为一个变量,表示当前方法调用者的地址值 
- super : 代表父类存储空间

#### super(....)用法演示

代码如下：

```java
class Person {
    private String name ="凤姐";
    private int age = 20;

    public Person() {
        System.out.println("父类无参");
    }
    
    public Person(String name , int age){
        this.name = name ;
        this.age = age ;
    }

}

class Student extends Person {
    private double score = 100;

    public Student() {
        //super(); // 调用父类无参构造方法,默认就存在，可以不写，必须再第一行
        System.out.println("子类无参");
    }
    
     public Student(String name ， int age，double score) {
        super(name ,age);// 调用父类有参构造方法Person(String name , int age)初始化name和age
        this.score = score;    
        System.out.println("子类有参");
     }
}

public class Demo07 {
    public static void main(String[] args) {
        // 调用子类有参数构造方法
        Student s2 = new Student("张三"，20，99);
        System.out.println(s2.getScore()); // 99
        System.out.println(s2.getName()); // 输出 张三
        System.out.println(s2.getAge()); // 输出 20
    }
}
```

**注意：**

**子类的每个构造方法中均有默认的super()，调用父类的空参构造。手动调用父类构造会覆盖默认的super()。**

**super() 和 this() 都必须是在构造方法的第一行，所以不能同时出现。**

super(..)是根据参数去确定调用父类哪个构造方法的。

#### super(...)

**父类空间优先于子类对象产生**

在每次创建子类对象时，先初始化父类空间，再创建其子类对象本身。目的在于子类对象中包含了其对应的父类空间，便可以包含其父类的成员，如果父类成员非private修饰，则子类可以随意使用父类成员。代码体现在子类的构造七调用时，一定先调用父类的构造方法。

#### this(...)用法演示

this(...)

 *    默认是去找本类中的其他构造方法，根据参数来确定具体调用哪一个构造方法。
 *    为了借用其他构造方法的功能。

```java
package com.itheima._08this和super调用构造方法;
/**
 * this(...):
 *    默认是去找本类中的其他构造方法，根据参数来确定具体调用哪一个构造方法。
 *    为了借用其他构造方法的功能。
 *
 */
public class ThisDemo01 {
    public static void main(String[] args) {
        Student xuGan = new Student();
        System.out.println(xuGan.getName()); // 输出:张三
        System.out.println(xuGan.getAge());// 输出:21
        System.out.println(xuGan.getSex());// 输出： 男
    }
}

class Student{
    private String name ;
    private int age ;
    private char sex ;

    public Student() {
  // 调用其他构造方法：Student(String name, int age, char sex)
        this("张三",21,'男');
    }

    public Student(String name, int age, char sex) {
        this.name = name ;
        this.age = age   ;
        this.sex = sex   ;
    }

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public int getAge() {
        return age;
    }

    public void setAge(int age) {
        this.age = age;
    }

    public char getSex() {
        return sex;
    }

    public void setSex(char sex) {
        this.sex = sex;
    }
}
```

#### 小结

* **子类的每个构造方法中均有默认的super()，调用父类的空参构造。手动调用父类构造会覆盖默认的super()。**

* **super() 和 this() 都必须是在构造方法的第一行，所以不能同时出现。**

* **super(..)和this(...)是根据参数去确定调用父类哪个构造方法的。**
* super(..)可以调用父类构造方法初始化继承自父类的成员变量的数据。
* this(..)可以调用本类中的其他构造方法。

| 关键字 |            访问成员变量             |               访问成员方法                |            访问构造方法             |
| :----: | :---------------------------------: | :---------------------------------------: | :---------------------------------: |
|  this  | this.成员变量   (访问本类成员变量)  | this.成员方法(...)       访问本类成员方法 | this(....)         访问本类构造方法 |
| super  | super.成员变量   (访问父类成员变量) |  super.成员方法(...)    访问父类成员方法  |  super(....)      访问父类构造方法  |

### 继承的特点

1. Java只支持单继承，不支持多继承。

  ```java
// 一个类只能有一个父类，不可以有多个父类。
class A {}
class B {}
class C1 extends A {} // ok
// class C2 extends A, B {} // error
  ```

2. 一个类可以有多个子类。

  ```java
// A可以有多个子类
class A {}
class C1 extends A {}
class C2 extends  A {}
  ```

3. 可以多层继承。

  ```java
class A {}
class C1 extends A {}
class D extends C1 {}
  ```

  > 顶层父类是Object类。所有的类默认继承Object，作为父类。

### 小结：

会写一个继承结构下的标准Javabean即可

需求：

​	猫：属性，姓名，年龄，颜色

​	狗：属性，姓名，年龄，颜色，吼叫

 书写技巧：

​        1.在大脑中要区分谁是父，谁是子

​        2.把共性写到父类中，独有的东西写在子类中

​        3.开始编写标准Javabean（从上往下写）

​        4.在测试类中，创建对象并赋值调用

代码示例：

```java
package com.itheima.test4;

public class Animal {
    //姓名，年龄，颜色
    private String name;
    private int age;
    private String color;


    public Animal() {
    }

    public Animal(String name, int age, String color) {
        this.name = name;
        this.age = age;
        this.color = color;
    }

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public int getAge() {
        return age;
    }

    public void setAge(int age) {
        this.age = age;
    }

    public String getColor() {
        return color;
    }

    public void setColor(String color) {
        this.color = color;
    }
}


public class Cat extends Animal{
    //因为猫类中没有独有的属性。
    //所以此时不需要写私有的成员变量

    //空参
    public Cat() {
    }

    //需要带子类和父类中所有的属性
    public Cat(String name, int age, String color) {
        super(name,age,color);
    }
}


public class Dog extends Animal{
    //Dog ：吼叫
    private String wang;

    //构造
    public Dog() {
    }

    //带参构造：带子类加父类所有的属性
    public Dog(String name, int age, String color,String wang) {
        //共性的属性交给父类赋值
        super(name,age,color);
        //独有的属性自己赋值
        this.wang = wang;
    }

    public String getWang() {
        return wang;
    }

    public void setWang(String wang) {
        this.wang = wang;
    }
}

public class Demo {
    public static void main(String[] args) {
        //Animal ： 姓名，年龄，颜色
        //Cat :
        //Dog ：吼叫

        //创建狗的对象
        Dog d = new Dog("旺财",2,"黑色","嗷呜~~");
        System.out.println(d.getName()+", " + d.getAge() + ", " + d.getColor() + ", " + d.getWang());

        //创建猫的对象
        Cat c = new Cat("中华田园猫",3,"黄色");
        System.out.println(c.getName() + ", " + c.getAge() + ", " + c.getColor());
    }
}
```

## 多态

同类型的对象,表现出的不同形态

### 多态的表现形式

```java
父类类型 对象名称 = 子类对象;
```

### 多态的前提

- 有继承关系
- 有父类引用指向子类对象
- 有方法重写

### 多态的优点

**使用父类作为参数,可以接收所有子类对象,体现多态的扩展性与遍历**

### 多态调用成员的特点

- 变量调用 : 编译看左边,运行也看左边

> 编译看左边：javac编译代码的时候，会看左边的父类中有没有这个变量，如果有，编译成功，如果没有编译失败
>
> 运行也看左边： java运行代码的时候，实际获取的就是左边父类成员变量的值
>
> 成员变量理解: 在子类对象中,会把父类的成员变量也继承下来,父: name 子:name

- 方法调用 : 编译看左边,运行看右边

>编译看左边： javac编译代码的时候，会看左边的父类中有没有这个方法，如果有，编译成功，如果没有，编译失败
>运行看右边： java运行的时候，实际商运行的是子类中的方法
>
>成员方法理解: 如果子类对方法进行了重写,那么在虚方法表中是会把父类的方法进行覆盖

### 多态的弊端

**不能调用子类的特有功能**

原因: 当调用成员方法的时候,编译看左边,运行看右边,那么在编译的时候会先检查左边的父类中有没有这个方法,如果没有直接报错.

解决方案: 强制转换成子类类型

```java
Zi 新对象名称 = (Zi)对象名称;
```

#### instanceof 类型判断

```
对象名称 instanceof 类名
```

#### 新特性

将强制转换和判断合二为一

```java
if (对象名称 instanceof 需要判断类名 新对象名称){
  
}else if (对象名称 instanceof 需要判断类名 新对象名称){
  
}else{
  sout("没有这个类型,无法转换")
}
```

#### 强制类型转换能解决的问题

- 可以转换成真正的子类类型,从而调用子类独有的功能
- 转换类型与真实对象类型不一致会报错
- 转换的时候用instanceof关键字进行判断

### 练习

>根据需求完成代码:
>
>1.定义狗类
>		属性：
>			年龄，颜色
>		行为:
>			eat(String something)(something表示吃的东西)
>			看家lookHome方法(无参数)
>
>2.定义猫类
>	属性：
>		年龄，颜色
>	行为:
>		eat(String something)方法(something表示吃的东西)
>		逮老鼠catchMouse方法(无参数)
>
>3.定义Person类//饲养员
>	属性：
>		姓名，年龄
>	行为：
>		keepPet(Dog dog,String something)方法
>			功能：喂养宠物狗，something表示喂养的东西
>	行为：
>		keepPet(Cat cat,String something)方法
>			功能：喂养宠物猫，something表示喂养的东西
>	生成空参有参构造，set和get方法  
>4.定义测试类(完成以下打印效果):
>	keepPet(Dog dog,String somethind)方法打印内容如下：
>		年龄为30岁的老王养了一只黑颜色的2岁的狗
>		2岁的黑颜色的狗两只前腿死死的抱住骨头猛吃
>	keepPet(Cat cat,String somethind)方法打印内容如下：
>		年龄为25岁的老李养了一只灰颜色的3岁的猫
>		3岁的灰颜色的猫眯着眼睛侧着头吃鱼

```java
public class Test2 {
    /*
    * 根据需求完成代码:
	1.定义狗类
		属性：
			年龄，颜色
		行为:
			eat(String something)(something表示吃的东西)
			看家lookHome方法(无参数)

	2.定义猫类
		属性：
			年龄，颜色
		行为:
			eat(String something)方法(something表示吃的东西)
			逮老鼠catchMouse方法(无参数)

	3.定义Person类//饲养员
		属性：
			姓名，年龄
		行为：
			keepPet(Dog dog,String something)方法
				功能：喂养宠物狗，something表示喂养的东西
		行为：
			keepPet(Cat cat,String something)方法
				功能：喂养宠物猫，something表示喂养的东西
		生成空参有参构造，set和get方法
	4.定义测试类(完成以下打印效果):
		keepPet(Dog dog,String somethind)方法打印内容如下：
			年龄为30岁的老王养了一只黑颜色的2岁的狗
			2岁的黑颜色的狗两只前腿死死的抱住骨头猛吃
		keepPet(Cat cat,String somethind)方法打印内容如下：
			年龄为25岁的老李养了一只灰颜色的3岁的猫
			3岁的灰颜色的猫眯着眼睛侧着头吃鱼
    * */
    public static void main(String[] args) {
        Persons person = new Persons("老王",30);
        Dogs dogs =new Dogs(2,"黑");
        person.keepPet(dogs,"骨头");

        Persons persons2 = new Persons("老王",25);
        Cats cats = new Cats(3,"灰");
        persons2.keepPet(cats,"鱼");
    }
}
class Animals{
    //属性：
    //			年龄，颜色
    //		行为:
    //			eat(String something)(something表示吃的东西)
    private int age;
    private String color;

    public Animals() {
    }

    public Animals(int age, String color) {
        this.age = age;
        this.color = color;
    }

    /**
     * 获取
     * @return age
     */
    public int getAge() {
        return age;
    }

    /**
     * 设置
     * @param age
     */
    public void setAge(int age) {
        this.age = age;
    }

    /**
     * 获取
     * @return color
     */
    public String getColor() {
        return color;
    }

    /**
     * 设置
     * @param color
     */
    public void setColor(String color) {
        this.color = color;
    }
    public void eat(String something){
        System.out.println("动作在吃"+something);
    }
}
class Dogs extends Animals{
    //1.定义狗类
    //		属性：
    //			年龄，颜色
    //		行为:
    //			eat(String something)(something表示吃的东西)
    //			看家lookHome方法(无参数)
    public Dogs(){}
    public Dogs(int age,String color){
        super(age,color);
    }
    //行为
    @Override
    public void eat(String something){
        System.out.println(getAge()+"岁的"+getColor()+"颜色的狗两只前腿死死的抱住"+something+"猛吃");
    }

    public void lookHome(){
        System.out.println("狗在看家");
    }
}
class Cats extends Animals{
    public Cats(){
    }
    public Cats(int age,String color){
        super(age, color);
    }

    @Override
    public void eat(String something){
        System.out.println(getAge()+"岁的"+getColor()+"颜色的猫眯着眼睛侧着头吃"+something);
    }

    public void catchMouse(){
        System.out.println("抓老鼠");
    }
}
class Persons{
    //定义Person类//饲养员
    //		属性：
    //			姓名，年龄
    //		行为：
    //			keepPet(Dog dog,String something)方法
    //				功能：喂养宠物狗，something表示喂养的东西
    //		行为：
    //			keepPet(Cat cat,String something)方法
    //				功能：喂养宠物猫，something表示喂养的东西
    //		生成空参有参构造，set和get方法
    private String name;
    private int age;

    public Persons() {
    }

    public Persons(String name, int age) {
        this.name = name;
        this.age = age;
    }

    /**
     * 获取
     * @return name
     */
    public String getName() {
        return name;
    }

    /**
     * 设置
     * @param name
     */
    public void setName(String name) {
        this.name = name;
    }

    /**
     * 获取
     * @return age
     */
    public int getAge() {
        return age;
    }

    /**
     * 设置
     * @param age
     */
    public void setAge(int age) {
        this.age = age;
    }
    public void keepPet(Animals animals,String something){
        String an = "";
        if (animals instanceof Dogs){
            an = "狗";
        } else if (animals instanceof Cats) {
            an = "猫";
        }
        System.out.println("年龄为"+age+"岁的"+name+"养了一只"+animals.getColor()+"颜色的"+animals.getAge()+"岁的"+an);
        animals.eat(something);
    }
}

```

## 使用其他类的规则

- 使用同一个包中的类时,不需要导包
- 使用java.lang包中的类时,不需要导包
- 其他情况都需要导包
- 如果同时使用两个包中的同名类,需要用全类名

## final 修饰词

方法 : 表明该方法是最终方法,**不能被重写**

类 : 表明该类是最终类,**不能被继承**

变量 : 叫做**常量**,只能被赋值一次

### 常量

命名规范:

- 单个单词 : 全部大写
- 多个单词 : 全部大写,单词之间用下划线隔开

细节:

final修饰的变量是基本类型:那么变量存储的**数据值**不能发生改变.

final修饰的变量是引用类型:那么变量存储的**地址值**不能发生改变,对象内部的可以改变

## 权限修饰符

- 权限修饰符:用来控制一个成员能够被访问的范围
- 可以修饰成员变量,方法,构造方法,内部类

### 权限修饰符的分类

作用范围从大到小(private < 空着不写(默认) < protected < public)

|  修饰符   | 同一个类中 | 同一个包中其他类 | 不同包下的子类 | 不同包下的无关类 |
| :-------: | :--------: | :--------------: | :------------: | :--------------: |
|  private  |    可以    |                  |                |                  |
| 空着不写  |    可以    |       可以       |                |                  |
| protected |    可以    |       可以       |      可以      |                  |
|  public   |    可以    |       可以       |      可以      |       可以       |

### 使用规则

一般使用private和public

- 成员变量私有

- 方法公开

  特性 : 如果方法中的代码是抽取其他方法中共性代码,这个方法一般也私有

## 代码块

- 局部代码块
- 构造代码块
- 静态代码块

### 局部代码块

使用{}包裹代码,提前结束

### 构造代码块

写在成员位置的代码块,用{}包裹

作用: 可以把多个构造方法中重复的代码抽取出来,我们在创建本类对象的时候会先执行构造代码块,再执行构造方法

### 静态代码块

格式: static{}

特点: 需要通过static关键字修饰,随着类的加载而加载,并且自动触发,**只执行一次**

使用场景: 在类加载的时候,做一些数据初始化的时候使用

## 抽象类

### 抽象方法

- 抽象方法 : 将**共性**的行为(方法)抽取到父类之后.由于每一个子类执行的内容是不一样,所以,在父类中不能确定具体的方法体.该方法就可以定义为抽象方法
- 抽象类 : 如果一个**类中存在抽象方法**,那么该类就**必须声明为抽象类**

### 抽象类和抽象方法的定义格式

- 抽象方法的定义格式

`public abstract 返回值类型 方法名(参数列表);`

- 抽象类的定义格式

`public abstract class 类名{}`

### 注意事项

- **抽象类不能创建对象**
- 抽象类中不一定有抽象方法,有抽象方法的类一定是抽象类
- 可以有构造方法
- 抽象类的子类要么重写抽象类中的所有抽象方法,要么是抽象类

## 接口(定义规则)

### 接口的定义和使用

- 接口用关键词interface来定义

  `public interface 接口名{}`

- **接口不能创建对象**

- 接口和类之间是实现关系,通过implements关键词表示

  `public class 类名 implements 接口名{}`

- 接口的子类(实现类)

  要么重写接口中的所有抽象方法

  要么是抽象类

> 1.接口和类的实现关系,可以是单实现,也可以是多实现
>
> `public class 类名 implements 接口1,接口2{}`
>
> 2.实现类还可以在继承一个类的同时实现多个接口
>
> `public class 类名 extends 父类 implements 接口1,接口2{}`

**当一个方法的参数是接口时,可以传递接口所有实现类的对象,这种方式称之为接口多态**

### 接口中成员的特点

#### 成员变量

只能是常量

默认修饰符 : public static final

#### 构造方法

没有

#### 成员方法

抽象方法 ,默认修饰符: public abstract

定义有方法体的方法和定义私有方法

### 接口和类之间的关系

#### 类和类的关系

继承关系,只能单继承,不能多继承,但是可以多层继承

#### 类和接口的关系

实现关系,可以单实现,也可以多实现,还可以在继承一个类的同时实现多个接口

多个接口有重名的方法只需要重写一次就行

假如我们定义一个运动员的**接口**（规范），代码如下：

```java
/**
   接口：接口体现的是规范。
 * */
public interface SportMan {
    void run(); // 抽象方法，跑步。
    void law(); // 抽象方法，遵守法律。
    String compittion(String project);  // 抽象方法，比赛。
}
```

接下来定义一个乒乓球运动员类，实现接口，实现接口的**实现类**代码如下：

```java
package com.itheima._03接口的实现;
/**
 * 接口的实现：
 *    在Java中接口是被实现的，实现接口的类称为实现类。
 *    实现类的格式:
 *      class 类名 implements 接口1,接口2,接口3...{
 *
 *
 *      }
 * */
public class PingPongMan  implements SportMan {
    @Override
    public void run() {
        System.out.println("乒乓球运动员稍微跑一下！！");
    }

    @Override
    public void law() {
        System.out.println("乒乓球运动员守法！");
    }

    @Override
    public String compittion(String project) {
        return "参加"+project+"得金牌！";
    }
}
```

**测试代码**：

```java
public class TestMain {
    public static void main(String[] args) {
        // 创建实现类对象。
        PingPongMan zjk = new PingPongMan();
        zjk.run();
        zjk.law();
        System.out.println(zjk.compittion("全球乒乓球比赛"));

    }
}
```

**类与接口之间的关系是多实现的，一个类可以同时实现多个接口。**

首先我们先定义两个接口，代码如下：

```java
/** 法律规范：接口*/
public interface Law {
    void rule();
}

/** 这一个运动员的规范：接口*/
public interface SportMan {
    void run();
}

```

然后定义一个实现类：

```java
/**
 * Java中接口是可以被多实现的：
 *    一个类可以实现多个接口: Law, SportMan
 *
 * */
public class JumpMan implements Law ,SportMan {
    @Override
    public void rule() {
        System.out.println("尊长守法");
    }

    @Override
    public void run() {
        System.out.println("训练跑步！");
    }
}
```

#### 接口和接口的关系

继承关系,可以单继承,也可以多继承

案例演示：

```java 
public interface Abc {
    void go();
    void test();
}

/** 法律规范：接口*/
public interface Law {
    void rule();
    void test();
}

 *
 *  总结：
 *     接口与类之间是多实现的。
 *     接口与接口之间是多继承的。
 * */
public interface SportMan extends Law , Abc {
    void run();
}
```

### JDK8和JDK9开始,接口新增的方法

接口中可以定义有方法体的方法(默认,静态)

接口中可以定义私有方法

#### 接口中默认方法的定义格式

```java
public default 返回值类型 方法名(参数列表){}
public default void show(){}
```

##### 注意事项

- 默认方法不是抽象方法,所以不强制重写,重写的时候去掉default关键词
- public可以省略,defualt不能省略
- 如果实现了多个接口,多个接口中存在相同名字的默认方法,子类就必须对该方法进行重写

#### 接口中静态方法的定义格式

```java
public static 返回值类型 方法名(参数列表){}
public static void show(){}
```

##### 注意事项

- 静态方法只能通过接口名调用,不能通过实现类名或者对象名调用
- public可以省略,static不能省略

### 私有方法定义格式

```java
//普通私有方法服务默认方法
private 返回值类型 方法名(参数类别){}
private void show(){}

//静态私有方法服务静态方法
private static 返回值类型 方法名(){}
private static void show(){}
```

## 适配器设计模式

当一个接口中抽象方法过多,但是只要使用其中一部分的时候,就可以适配器设计模式

### 书写步骤

编写中间类XXXAdapeter,实现对应的接口

对接口中的抽象方法进行空实现

让真正的实现类继承中间类,并重写所需要的方法

为了避免其他类创建适配器类的对象,中间的适配器类用abstract进行修饰

## 内部类

类的五大成员:属性,构造方法,代码块,内部类

**在一个类的里面,再定义一个类**

例如:在A类的内部定义B类,B类就被称为内部类

```java
public class Outer{//外部类
  public class Inner{//内部类
    
  }
}
```

内部类表示的事物是外部类的一部分

内部类单独出现没有任何意义

**内部类的访问特点**

- 内部类可以直接访问外部类的成员,包括私有
- 外部类要访问内部类的成员,必须创建对象

### 内部类的分类

按定义的位置来分

1. **成员内部内**，类定义在了成员位置 (类中方法外称为成员位置，无static修饰的内部类)
2. **静态内部类**，类定义在了成员位置 (类中方法外称为成员位置，有static修饰的内部类)
3. **局部内部类**，类定义在方法内
4. **匿名内部类**，没有名字的内部类，可以在方法中，也可以在类中方法外。

### 成员内部类

**成员内部类特点**：

- 无static修饰的内部类，属于外部类对象的。
- 宿主：外部类对象。

**内部类的使用格式**：

```java
 外部类.内部类 // 访问内部类的类型都是用 外部类.内部类
```

**获取成员内部类对象的两种方式**：

方式一：外部直接创建成员内部类的对象

```java
外部类.内部类 变量 = new 外部类（）.new 内部类（）;
```

方式二：在外部类中定义一个方法提供内部类的对象

**案例演示**

```java
方式一：
public class Test {
    public static void main(String[] args) {
        //  宿主：外部类对象。
       // Outer out = new Outer();
        // 创建内部类对象。
        Outer.Inner oi = new Outer().new Inner();
        oi.method();
    }
}

class Outer {
    // 成员内部类，属于外部类对象的。
    // 拓展：成员内部类不能定义静态成员。
    public class Inner{
        // 这里面的东西与类是完全一样的。
        public void method(){
            System.out.println("内部类中的方法被调用了");
        }
    }
}


方式二：
public class Outer {
    String name;
    private class Inner{
        static int a = 10;
    }
    public Inner getInstance(){
        return new Inner();
    }
}

public class Test {
    public static void main(String[] args) {
        Outer o = new Outer();
        System.out.println(o.getInstance());


    }
}
```

#### 成员内部类的细节

编写成员内部类的注意点：

1. 成员内部类可以被一些修饰符所修饰，比如： private，默认，protected，public，static等
2. 在成员内部类里面，JDK16之前不能定义静态变量，JDK16开始才可以定义静态变量。
3. **创建内部类对象时，对象中有一个隐含的Outer.this记录外部类对象的地址值**。

详解：

​	内部类被private修饰，外界无法直接获取内部类的对象，只能通过方式二获取内部类的对象

​	被其他权限修饰符修饰的内部类一般用方式一直接获取内部类的对象

​	内部类被static修饰是成员内部类中的特殊情况，叫做静态内部类下面单独学习。

​	内部类如果想要访问外部类的成员变量，外部类的变量必须用final修饰，JDK8以前必须手动写final，JDK8之后不需要手动写，JDK默认加上。

#### 成员内部类面试题

请在?地方向上相应代码,以达到输出的内容

注意：内部类访问外部类对象的格式是：**外部类名.this**

```java
public class Test {
    public static void main(String[] args) {
        Outer.inner oi = new Outer().new inner();
        oi.method();
    }
}

class Outer {	// 外部类
    private int a = 30;

    // 在成员位置定义一个类
    class inner {
        private int a = 20;

        public void method() {
            int a = 10;
            System.out.println(???);	// 10   答案：a
            System.out.println(???);	// 20	答案：this.a
            System.out.println(???);	// 30	答案：Outer.this.a
        }
    }
}
```

### 静态内部类

**静态内部类特点**：

* 静态内部类是一种特殊的成员内部类。

- 有static修饰，属于外部类本身的。
- 总结：静态内部类与其他类的用法完全一样。只是访问的时候需要加上外部类.内部类。
- **拓展1**:静态内部类可以直接访问外部类的静态成员。
- **拓展2**:静态内部类不可以直接访问外部类的非静态成员，如果要访问需要创建外部类的对象。
- **拓展3**:静态内部类中没有Outer.this。

**内部类的使用格式**：

```
外部类.内部类
```

**静态内部类对象的创建格式**：

```java
外部类.内部类  变量 = new  外部类.内部类构造器;
```

**调用方法的格式：**

* 调用非静态方法的格式：先创建对象，用对象调用
* 调用静态方法的格式：外部类名.内部类名.方法名();

**案例演示**：

```java
// 外部类：Outer01
class Outer01{
    private static  String sc_name = "程序";
    // 内部类: Inner01
    public static class Inner01{
        // 这里面的东西与类是完全一样的。
        private String name;
        public Inner01(String name) {
            this.name = name;
        }
        public void showName(){
            System.out.println(this.name);
            // 拓展:静态内部类可以直接访问外部类的静态成员。
            System.out.println(sc_name);
        }
    }
}

public class InnerClassDemo01 {
    public static void main(String[] args) {
        // 创建静态内部类对象。
        // 外部类.内部类  变量 = new  外部类.内部类构造器;
        Outer01.Inner01 in  = new Outer01.Inner01("张三");
        in.showName();
    }
}
```

### 局部内部类

- **局部内部类** ：定义在**方法中**的类。

定义格式:

```java
class 外部类名 {
	数据类型 变量名;
	
	修饰符 返回值类型 方法名(参数列表) {
		// …
		class 内部类 {
			// 成员变量
			// 成员方法
		}
	}
}
```

### 匿名内部类【重点】

#### 概述

**匿名内部类** ：是内部类的简化写法。他是一个隐含了名字的内部类。开发中，最常用到的内部类就是匿名内部类了。

#### 格式

```java
new 类名或者接口名() {
     重写方法;
};
```

包含了：

* **继承或者实现关系**

* 方法重写
* 创建对象

所以从语法上来讲，这个整体其实是匿名内部类对象

#### 什么时候用到匿名内部类 

**实际上，如果我们希望定义一个只要使用一次的类，就可考虑使用匿名内部类。匿名内部类的本质作用**

**是为了简化代码**。 

之前我们使用接口时，似乎得做如下几步操作：

1. 定义子类
2. 重写接口中的方法
3. 创建子类对象
4. 调用重写后的方法

```java
interface Swim {
    public abstract void swimming();
}

// 1. 定义接口的实现类
class Student implements Swim {
    // 2. 重写抽象方法
    @Override
    public void swimming() {
        System.out.println("狗刨式...");
    }
}

public class Test {
    public static void main(String[] args) {
        // 3. 创建实现类对象
        Student s = new Student();
        // 4. 调用方法
        s.swimming();
    }
}
```

我们的目的，最终只是为了调用方法，那么能不能简化一下，把以上四步合成一步呢？匿名内部类就是做这样的快捷方式。

#### 匿名内部类前提和格式

匿名内部类必须**继承一个父类**或者**实现一个父接口**。

**匿名内部类格式**

```java
new 父类名或者接口名(){
    // 方法重写
    @Override 
    public void method() {
        // 执行语句
    }
};
```

#### 使用方式

以接口为例，匿名内部类的使用，代码如下：

```java
interface Swim {
    public abstract void swimming();
}

public class Demo07 {
    public static void main(String[] args) {
        // 使用匿名内部类
		new Swim() {
			@Override
			public void swimming() {
				System.out.println("自由泳...");
			}
		}.swimming();

        // 接口 变量 = new 实现类(); // 多态,走子类的重写方法
        Swim s2 = new Swim() {
            @Override
            public void swimming() {
                System.out.println("蛙泳...");
            }
        };

        s2.swimming();
        s2.swimming();
    }
}
```

#### 匿名内部类的特点

1. 定义一个没有名字的内部类
2. 这个类实现了父类，或者父类接口
3. 匿名内部类会创建这个没有名字的类的对象

#### 匿名内部类的使用场景

通常在方法的形式参数是接口或者抽象类时，也可以将匿名内部类作为参数传递。代码如下：

```java
interface Swim {
    public abstract void swimming();
}

public class Demo07 {
    public static void main(String[] args) {
        // 普通方式传入对象
        // 创建实现类对象
        Student s = new Student();
        
        goSwimming(s);
        // 匿名内部类使用场景:作为方法参数传递
        Swim s3 = new Swim() {
            @Override
            public void swimming() {
                System.out.println("蝶泳...");
            }
        };
        // 传入匿名内部类
        goSwimming(s3);

        // 完美方案: 一步到位
        goSwimming(new Swim() {
            public void swimming() {
                System.out.println("大学生, 蛙泳...");
            }
        });

        goSwimming(new Swim() {
            public void swimming() {
                System.out.println("小学生, 自由泳...");
            }
        });
    }

    // 定义一个方法,模拟请一些人去游泳
    public static void goSwimming(Swim s) {
        s.swimming();
    }
}
```

