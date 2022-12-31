# Java基础

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

> 编译: javac是JDK提供的编译工具,激昂Java文件编译成class文件==需要带后缀==
>
> 运行: 运行代码,运行编译后的class文件==不带后缀==

## 基础

### 注释

==单行注释: `//注释信息`==

==多行注释: `/*注释信息*/ `==

文档注释: `/**注释信息*/`

### 关键字

> ==关键字==:被java赋予特定含义的英文单词
>
> **关键字的字母==全部小写==**

  #### class

==class==:用于(创建/定义)一个类,后面跟随类名.

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

==数据类型 变量名 = 数据值;==

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
> 3. 一条语句可以定义多个变量,==用逗号分隔==
> 4. 变量在使用之前一定要进行赋值(==初始化变量==)
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

> ==定义long类型的变量==,在数据值的后面需要加一个==L==作为后缀(L可以大写也可以小写)
>
> ==定义float类型的变量==,在数据值的后面需要加一个==F==作为后缀(大小写都可以)
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

### 标识符

> 标识符: 给类、方法、变量等起的名字

1. 由数字、字母、下划线和美元符组成
2. 不能以数字开头
3. 不能是关键字
4. 区分大小写

## 键盘录入

==Scanner类,可以接收键盘输入的数字==

步骤一:导包

`import java.util.Scanner;`

> 导包的动作必须出现在==类定义的上边==

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

> 用==运算符==把字面量或者变量连接起来,==符合java语法的式子==就可以称为表达式.
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

> ==加减乘==
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
> ==除/== 
>
> ==1.整数参与计算,结果只能得到整数==
>
> 2.小数参与计算,结果有可能是不精确的
>
> 例子:
>
> 10/2  结果5
>
> ==10/3  结果3==
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

==数字进行运算时,数据类型不一样不能运算,需要转成一样的,才能运算==

#### 隐式转换

把一个取值范围小的数值,转换成取值范围大的数据

```java
int a = 10;
double b = a;
```

##### 隐式转换的两种提升规则

1.取值范围小的,和取值范围大的进行运算,小的会先提升为大的,再进行运算.

2.==byte、short、char==三种类型的数据在运算的时候,都会先提升为int,然后再进行运算

>整数和小数取值范围大小关系:
>
>double>float>long>int>short>byte

 #### 强制转换

1.如果把一个==取值范围大==的数值,赋值给==取值范围小==的变量.不允许直接赋值,需要强制转换.

2.格式: ==目标数据类型 变量名 = (目标数据类型)被强制的数据;==

```java
double a = 123;
int b = (int)a;
```

#### 字符串的“+”操作

1.当“+”操作中出现字符串时,这个“+”是字符串连接符,而不是算术运算符.会将前后的数据进行==拼接==,并产生一个新的字符串.

> "123"+123
>
> 结果:
>
> "123123"

2.连接进行“+”操作时,==从左到右逐个执行==

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

> 当==字符+字符或者字符+数字==时,会把字符通过ASCII码表查询到对应的数字再进行计算

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
> ==赋值后的数据类型同左边一样==

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

> & ==两边都要满足==
>
> | ==两边满足一个==

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
> ||,&&  如果==左边能确定整个表达式的结果==,==右边不执行==

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

==关系表达式 ? 表达式1:表达式2==

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

> ==执行流程:==
>
> 1. 首先计算表达式的==值==
> 2. 依次和case后面的值进行比较,如果有对应的值,就会执行相应的语句,在执行的过程中,遇到break就会结束.
> 3. 如果没有发现break,那么程序就会继续执行下一个case语句体,一直遇到break或者打括号为止.
> 4. 如果所有的case后面的值和表达式的值都不匹配,就会执行default里面的语句体,然后结束整个switch语句.

> ==注意⚠️==
>
> 1. case后面的值只能是==字面量==,不能是变量
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

==case语句后面的打括号里如果只有一条语句,打括号可以删除==

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

> ==执行流程:==
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

#### for循环和while循环的对比

>相同点:运行规则一样
>
>不同点:
>
>for循环中,控制循环的变量,因为归属for循环的语法结构中,在for循环结束后,就不能再次被访问到
>
>while循环中,控制循环的变量,对于while循环来说不归属其语法结构中,在while循环结束后,该变量还可以继续使用
>
>==习惯区别==
>
>for循环中: 知道==循环次数或者循环的范围==
>
>while循环中; 不知道循环次数和范围,只知道==循环的结束条件==.

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

> ==运行流程==
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
> 口诀：==包头不包尾，包左不包右==

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

> 数组指的是一种容器,可以用来存储==同种数据类型==的多个值

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
> 索引特点: ==从0开始,逐个+1增长==,连续不间断

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
> 一旦==覆盖==元素组之后,原来的数据就==不存在==了

### 数组遍历

> 将数组中所有的内容取出来,取出来之后可以(打印,求和,判断...)
>
> 注意:
>
> 遍历指的是==取出数据==的过程,不仅仅打印

#### 数组长度属性

> 在java中,关于数组的一个长度属性,length
>
> ==调用方式:== `数组名.length``

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

> ==方法==运行时使用的内存,比如main方法运行,进入方法栈中执行

### 堆

> 存储对象或者数组,==new==来创建,都存储在堆内存

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

> ==形参==: 全称形式参数,是指==方法定义==中的参数
>
> ==实参==: 全称实际参数,方法调用中的参数

==注意==:方法调用时,参数的数量与类型必须与方法中小括号里面的变量一一对应,否则程序报错

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

同一个类中,==方法名相同==,==参数不同==的方法,与返回值无关.

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

==类==:是对象共同特征的描述

==对象:==是真实存在的具体东西

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
- 被private修饰的成员只能在本类中才能访问

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

#### 成员变量和局部变量

==就近原则==

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
  修饰符 类名(参数){
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

3.提供至少两个构造方法: 无参构造方法和带参数构造方法

4.成员方法: 提供每一个成员变量对应的setXxx()/getSxx() ;如果还有其他行为,也需要写上
