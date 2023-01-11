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
**对象一旦创建,内部记录的值不能发生改变**