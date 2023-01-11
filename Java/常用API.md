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
