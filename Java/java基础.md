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
      	System.out.println("尘世烟雨客")
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
import java.util.Scanner
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
