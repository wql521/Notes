### Math
- 是一个帮助我们用于进行数学计算的工具类
- 私有化构造方法,所有方法都是静态的
#### 常用方法
|  方法名                                           |                 说明                 |
|:-----------------------------------------------|:-----------------------------------|
|  public static int  abs(int a)                 |            获取参数绝对值                 |
|  public static double  ceil(double a)          |               向上取整                 |
|  public static double  floor(double a)         |               向下取整                 |
|  public static int  round(float a)             |               四舍五入                 |
|  public static int  max(int a,int b)           |        获取两个int值中较大值                |
| public static double sqrt(double a)            | 返回a的平方根                            |
| public static double cbrt(double a)            | 返回a的立方根                            |
|  public static double  pow(double a,double b)  |           返回a的b次幂的值                |
|  public static double  random()                |  返回为double的随机值,范围[0.0,1.0)         |  

### System
System是一个工具类,提供了一些与系统相关的方法
#### 计算机的时间原点
**1970年1月1日  00:00:00**
中国从计算机获取到的时间是**1970年1月1日  08:00:00**
#### 常用方法
| 方法名                                                                           | 说明                         |
|:-------------------------------------------------------------------------------- |:---------------------------- |
| `public static void exit(int status)`                                            | 终止当前的java虚拟机         |
| `public static long currentTimeMillis()`                                         | 返回当前系统的时间毫秒值形式 |
| `public static void arraycopy(数据源数组,起始索引,目的地数组,起始索引,拷贝个数)` | 数组拷贝                     |
终止虚拟机:
0:表示当前虚拟机是正常停止
非0:表示当前虚拟机异常停止
拷贝数组:
1. 如果数据源数组和目的地数组都是基本数据类型,那么两者的类型必须保持一致,否则会报错
2. 在拷贝的时候需要考虑数组的长度,如果超出范围会报错
3. 如果数据源数组和目的地数组都是引用数据类型,那么子类类型可以赋值给父类类型(拷贝的是地址)
### Runtime
| 方法名                                   | 说明                       |
|:--------------------------------------|:-------------------------|
| `public static Runtime getRuntime()`  | 当前系统的运行环境对象              |
| `public void exit(int status)`        | 停止虚拟机                    |
| `public int availableProcessors()`    | 获取CPU的线程数                |
| `public long maxMemory()`             | JVM能从系统中获取总内存大小(单位byte)  |
| `public long totalMemory()`           | JVM已经从系统中获取总内存大小(单位byte) |
| `public long freeMemory()`            | JVM剩余内存大小(单位byte)        |
| `public Process exec(String command)` | 运行cmd命令                  |  
cmd:
shutdown:关机
加上参数才能执行:
-s :默认在一分钟之后关机
-s -t 指定时间: 指定关机时间
-a :取消关机操作
-r : 关机并且重启
### Object
Object是java中的顶级父类,所有的类都直接或间接的继承与Object类
Object类中的方法可以被所有子类访问,所以我们要学习Object类和其中的方法
| 方法名               | 说明   |
|:------------------|:-----|
| `public Object()` | 空参构造 |  
顶级父类只有无参构造
#### 常用方法
|  方法名                                                |  说明                        |
|:----------------------------------------------------|:---------------------------|
|  `public String toString()`                         |  返回对象的字符串表示形式              |
|  `public boolean equals(Object obj)`                |  比较两个对象是否相等                |
| `public static boolean equals(Object a , Object b)` | 先做非空判断,对a进行null判断,为空则返回false,比较两个对象              |
|  `public Object clone(int a)`                       |  对象克隆                      |
| `public static boolean isNull(Object obj)`          | 判断对象是否为null,为null返回true,反之 |
| `public static boolean nonNull(Object obj)`         | 判断对象是否为null,跟isNull结果相反    |  
##### toString方法:
如果打印一个对象,想要看到属性值的话,那么就**重写toString方法**
在重写方法的时候,属性值进行拼接.
##### equals方法:
如果没有重写equals方法,默认使用Object中的方法进行比较,比较的是地址值是否相等
如果重写equals方法,重写之后比较对象内部的属性值
##### 对象克隆:
把A对象的属性值完全拷贝给B对象,也叫对象拷贝,对象复制
方法在底层会帮我们创建一个对象,并且原对象中的数据拷贝过去
细节:
1. 重写Object中的clone方法(可以实现浅克隆和深克隆(采用第三方工具最好))
2. 让javabean类实现Cloneable接口
3. 创建元对象并调用clone接口
>Cloneable接口
>如果一个接口里面没有抽象方法
>表示当前的接口是一个标记性接口
>Cloneable表示一旦实现,那么当前类的对象就可以被克隆
### BigInteger
在java中,整数有四种类型:byte,short,int,long
在底层占用字节个数:byte1个字节,short2个字节,int4个字节,long8个字节
| 构造方法                                          | 说明                        |
|:----------------------------------------------|:--------------------------|
| `public BigInteger(int num, Random rnd)`      | 获取随机大整数,范围:[0~2的num次方-1]  |
| `public BigInteger(String val)`               | 获取指定的大整数                  |
| `public BigInteger(String val,int int radix)` | 获取指定进制的大整数                |
| `public BigInteger valueOf(long val)`         | 静态方法获取BigInteger的对象,内部有优化 |  
**对象一旦创建,内部记录的值不能发生改变,只要进行计算都会产生一个新的BigInteger对象**
#### valueOf方法:
1. 能表示范围较小,在long的取值范围之内,如果超出long的范围就不行
2. 在内部对常用的数字: -16~16进行了优化;提前把-16~16先创建BigIneger的对象,如果多次获取不会重新穿件对象
#### 常用方法
```java
public BigInteger add(BigInteger val)					//加法
public BigInteger subtract(BigInteger val)				//减法
public BigInteger multiply(BigInteger val)				//乘法
public BigInteger divide(BigInteger val)				//除法
public BigInteger[] divideAndRemainder(BigInteger val)	 //除法，获取商和余数
public  boolean equals(Object x) 					    //比较是否相同
public  BigInteger pow(int exponent) 					//次幂、次方
public  BigInteger max/min(BigInteger val) 				//返回较大值/较小值
public  int intValue(BigInteger val) 					//转为int类型整数，超出范围数据有误
```
代码实现：
```java
import java.math.BigInteger;

public class BigIntegerDemo1 {
    public static void main(String[] args) {
        /*
            public BigInteger(int num, Random rnd) 获取随机大整数，范围:[0~ 2的num次方-11
            public BigInteger(String val) 获取指定的大整数
            public BigInteger(String val, int radix) 获取指定进制的大整数

            public static BigInteger valueOf(long val) 静态方法获取BigInteger的对象，内部有优化

            细节:
            对象一旦创建里面的数据不能发生改变。
        */


        //1.获取一个随机的大整数
        /* Random r=new Random();
            for (int i = e; i < 100; i++) {
            BigInteger bd1 = new BigInteger(4,r);
            System.out.println(bd1);//[@ ~ 15]}
            }
        */

        //2.获取一个指定的大整数，可以超出long的取值范围
        //细节:字符串中必须是整数，否则会报错
        /* BigInteger bd2 = new BigInteger("1.1");
            System.out.println(bd2);
        */

        /*
            BigInteger bd3 = new BigInteger("abc");
            System.out.println(bd3);
         */

        //3.获取指定进制的大整数
        //细节:
        //1.字符串中的数字必须是整数
        //2.字符串中的数字必须要跟进制吻合。
        //比如二进制中，那么只能写日和1，写其他的就报错。
        BigInteger bd4 = new BigInteger("123", 2);
        System.out.println(bd4);

        //4.静态方法获取BigInteger的对象，内部有优化
        //细节:
        //1.能表示范围比较小，只能在long的取值范围之内，如果超出long的范围就不行了。
        //2.在内部对常用的数字: -16 ~ 16 进行了优化。
        //  提前把-16~16 先创建好BigInteger的对象，如果多次获取不会重新创建新的。
        BigInteger bd5 = BigInteger.valueOf(16);
        BigInteger bd6 = BigInteger.valueOf(16);
        System.out.println(bd5 == bd6);//true


        BigInteger bd7 = BigInteger.valueOf(17);
        BigInteger bd8 = BigInteger.valueOf(17);
        System.out.println(bd7 == bd8);//false


        //5.对象一旦创建内部的数据不能发生改变
        BigInteger bd9 =BigInteger.valueOf(1);
        BigInteger bd10 =BigInteger.valueOf(2);
        //此时，不会修改参与计算的BigInteger对象中的借，而是产生了一个新的BigInteger对象记录
        BigInteger result=bd9.add(bd10);
        System.out.println(result);//3

    }
}

```

```java
import java.math.BigInteger;

public class BigIntegerDemo2 {
    public static void main(String[] args) {
        /*
            public BigInteger add(BigInteger val) 加法
            public BigInteger subtract(BigInteger val) 减法
            public BigInteger multiply(BigInteger val) 乘法
            public BigInteger divide(BigInteger val) 除法，获取商
            public BigInteger[] divideAndRemainder(BigInteger val) 除法，获取商和余数
            public boolean equals(Object x) 比较是否相同
            public BigInteger pow(int exponent) 次幂
            public BigInteger max/min(BigInteger val) 返回较大值/较小值
            public int intValue(BigInteger val) 转为int类型整数，超出范围数据有误
        */

        //1.创建两个BigInteger对象
        BigInteger bd1 = BigInteger.valueOf(10);
        BigInteger bd2 = BigInteger.valueOf(5);

        //2.加法
        BigInteger bd3 = bd1.add(bd2);
        System.out.println(bd3);

        //3.除法，获取商和余数
        BigInteger[] arr = bd1.divideAndRemainder(bd2);
        System.out.println(arr[0]);
        System.out.println(arr[1]);

        //4.比较是否相同
        boolean result = bd1.equals(bd2);
        System.out.println(result);

        //5.次幂
        BigInteger bd4 = bd1.pow(2);
        System.out.println(bd4);

        //6.max
        BigInteger bd5 = bd1.max(bd2);


        //7.转为int类型整数，超出范围数据有误
        /* BigInteger bd6 = BigInteger.valueOf(2147483647L);
         int i = bd6.intValue();
         System.out.println(i);
         */

        BigInteger bd6 = BigInteger.valueOf(200);
        double v = bd6.doubleValue();
        System.out.println(v);//200.0
    }
}

```
### BigDecimal
- 用于小数的精确运算
- 用来表示很大的小数
#### 构造方法
| 方法                                    | 说明                              |
|:----------------------------------------|:--------------------------------|
| `public BigDecimal(double val)`         | 通过传递double类型的小数来创建对象(可能不精确,不建议) |
| `public BigDecimal(String val)`         | 通过传递String类型的小数来创建对象            |
| `public BigDecimal valueOf(double val)` | 通过静态方法获取对象                      |  
1. 如果要表示的数字不大,没有超过double的取值范围,使用静态方法更好
2. 如果超过了double的取值范围,使用构造方法更好
3. 如果我们传递的是0~10之间的整数,包含0和10,静态方法会返回已经创建好的对象,不会重新new
#### 常用方法
```java
public BigDecimal add(BigDecimal value)				// 加法运算
public BigDecimal subtract(BigDecimal value)		// 减法运算
public BigDecimal multiply(BigDecimal value)		// 乘法运算
public BigDecimal divide(BigDecimal value)			// 触发运算
```

```java
public class BigDecimalDemo01 {

    public static void main(String[] args) {

        // 创建两个BigDecimal对象
        BigDecimal b1 = new BigDecimal("0.3") ;
        BigDecimal b2 = new BigDecimal("4") ;

        // 调用方法进行b1和b2的四则运算，并将其运算结果在控制台进行输出
        System.out.println(b1.add(b2));         // 进行加法运算
        System.out.println(b1.subtract(b2));    // 进行减法运算
        System.out.println(b1.multiply(b2));    // 进行乘法运算
        System.out.println(b1.divide(b2));      // 进行除法运算

    }

}
```

运行程序进行测试，控制台输出结果如下：

```java
4.3
-3.7
1.2
0.075
```
如果使用BigDecimal类型的数据进行除法运算的时候，得到的结果是一个无限循环小数，那么就会报错：ArithmeticException。 如下代码所示：

```java
public class BigDecimalDemo02 {

    public static void main(String[] args) {

        // 创建两个BigDecimal对象
        BigDecimal b1 = new BigDecimal("1") ;
        BigDecimal b2 = new BigDecimal("3") ;

        // 调用方法进行b1和b2的除法运算，并且将计算结果在控制台进行输出
        System.out.println(b1.divide(b2));

    }

}
```

运行程序进行测试，控制台输出结果如下所示：

```java
Exception in thread "main" java.lang.ArithmeticException: Non-terminating decimal expansion; no exact representable decimal result.
	at java.base/java.math.BigDecimal.divide(BigDecimal.java:1716)
	at com.itheima.api.bigdecimal.demo02.BigDecimalDemo02.main(BigDecimalDemo02.java:14)
```

针对这个问题怎么解决，此时我们就需要使用到BigDecimal类中另外一个divide方法，如下所示：

```java
BigDecimal divide(BigDecimal divisor, int scale, int roundingMode)
```

上述divide方法参数说明：

```
divisor:			除数对应的BigDecimal对象；
scale:				精确的位数；
roundingMode:		取舍模式；
取舍模式被封装到了RoundingMode这个枚举类中，在这个枚举类中定义了很多种取舍方式。最常见的取舍方式有如下几个：
UP(直接进1) ， FLOOR(直接删除) ， HALF_UP(4舍五入),我们可以通过如下格式直接访问这些取舍模式：枚举类名.变量名
```

接下来我们就来演示一下这些取舍模式，代码如下所示：

```java
public class BigDecimalDemo02 {

    public static void main(String[] args) {

        // 调用方法
        method_03() ;

    }

    // 演示取舍模式HALF_UP
    public static void method_03() {

        // 创建两个BigDecimal对象
        BigDecimal b1 = new BigDecimal("0.3") ;
        BigDecimal b2 = new BigDecimal("4") ;

        // 调用方法进行b1和b2的除法运算，并且将计算结果在控制台进行输出
        System.out.println(b1.divide(b2 , 2 , RoundingMode.HALF_UP));

    }

    // 演示取舍模式FLOOR
    public static void method_02() {

        // 创建两个BigDecimal对象
        BigDecimal b1 = new BigDecimal("1") ;
        BigDecimal b2 = new BigDecimal("3") ;

        // 调用方法进行b1和b2的除法运算，并且将计算结果在控制台进行输出
        System.out.println(b1.divide(b2 , 2 , RoundingMode.FLOOR));

    }

    // 演示取舍模式UP
    public static void method_01() {

        // 创建两个BigDecimal对象
        BigDecimal b1 = new BigDecimal("1") ;
        BigDecimal b2 = new BigDecimal("3") ;

        // 调用方法进行b1和b2的除法运算，并且将计算结果在控制台进行输出
        System.out.println(b1.divide(b2 , 2 , RoundingMode.UP));

    }

}
```
小结:后期在进行两个数的除法运算的时候，我们常常使用的是可以设置取舍模式的divide方法.