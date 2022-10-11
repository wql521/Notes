# Python基础语法|类
![](https://img-blog.csdnimg.cn/0a17759ef20a4e97a38ccf45878b71ae.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBA5biD6KGj5Lmm55SfLVB5dGhvbg==,size_18,color_FFFFFF,t_70,g_se,x_16)
* 面向过程语言
> 面向过程就是分析出解决问题所需要的步骤，然后用函数把这些步骤一步一步实现，使用的时候再依次调用，类似流水线的工作原理。

* 面向对象语言
> 面向对象是把构成问题事务分解成各个对象，依靠各个对象之间的交互推动程序执行，进而实现问题的解决。建立对象的目的不是为了完成一个步骤，而是为了描叙某个事物在完整解决问题步骤中的行为。

## 类的创建
Python语言中，使用class关键字来创建类，其创建方式如下：
```
class ClassName(bases):
    # class documentation string 类文档字符串，对类进行解释说明
    class_suite
```
class是关键字，bases是要继承的父类，默认继承object类。
class documentation string是类文档字符串，一般用于类的注释说明。class_suite是类体，主要包含属性和方法。

类、属性和方法的命名约定惯例如下：
* 类名表示实例的抽象，命名时首字母大写；
* 属性使用名词作为名字，比如name、age、weight等；
* 方法名一般指对属性的操作，其命名规则一般采用动词加属性名称形式，如updataName、updataAge、updataWeight等。 举例如下图：
```
# 类定义
class People:  # 类名
    name = "张三"  # 属性名

    def undate_name(self, name):# 方法名
        self.name = name  
```
Python3.x中类定义的默认方式，必须继承object方法，其典型定义方式如下图：
```
# 新式类是指继承object的类
class A(object):
    pass
```

## 对象的创建
类创建完之后，就应该创建该类的实例或对象了，该过程称之为实例化。当一个对象被创建后，就包含标识、属性和方法这三个方面的对象特性了。其中，对象标识用于区分不同的对象，属性和方法与类中的成员变量和成员函数相对应
```
people = People("李四", 20, "50kg")  # 实例化一个对象
```
如例子所示，对象标识符为people，属性为括号中内容，方法为类中方法

## 类的属性
Python语言中，属性分为类级别和实例级别两种。实例级别的属性值默认共享类级别的属性值。除非显式进行赋值操作。下面举一个例子来说明。
```
class A():
    age = 10


obj2 = A()
obj3 = A()
```
如例子所示，存在三个实例，分别是类实例A和对象实例obj2、obj3。
在情形1中，obj2和obj3这两个对象实例共享类实例A的属性age；
```
# 情形1
print(obj2.age, obj3.age, A.age)
```
在情形2中，显示修改了对象实例obj1的属性aaa；
```
# 情形2
obj2.age+=2
print(obj2.age, obj3.age, A.age)
```
在情形3中，修改了类实例A的属性aaa。
```
# 情形3
A.age+=3
print(obj2.age, obj3.age, A.age)
```
结果如图所示:
```
情景1:
10 10 10
情景2:
12 10 10 
情景3:
12 13 13
```
在情形2中已经修改了对象实例obj2的属性值age，其属性值和类实例A的属性值已经独立。而对象实例obj3的属性从来没有修改过，所以它还是和类实例A的属性值保持一致。

Python语言对于属性的设置采用“类.属性 = 值”或“实例.属性 = 值”的形式。如上例中obj2.age += 2等价于obj2.age = obj2.age + 2，该语句包含了属性获取及属性设置两个操作。

Python语言中的属性操作遵循三个规则：
（1）属性的获取是按照从下到上的顺序来查找属性；
（2）类和实例是两个完全独立的对象；
（3）属性设置是针对实例本身进行的。

类的定义由属性和方法组成，属性是对数据的封装，方法则是对类行为的封装。属性按使用范围分为公有属性和私有属性，使用范围取决于属性名称。类的属性如下表所示。
![](https://img-blog.csdnimg.cn/352105197f3242ffbb601989c6dc94e8.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBA5biD6KGj5Lmm55SfLVB5dGhvbg==,size_20,color_FFFFFF,t_70,g_se,x_16)
内置属性如下表所示：
![](https://img-blog.csdnimg.cn/c3e0d2718e524c2ca1a666eb38af1229.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBA5biD6KGj5Lmm55SfLVB5dGhvbg==,size_12,color_FFFFFF,t_70,g_se,x_16)
![](https://img-blog.csdnimg.cn/79a2e50031964e95b64de072a4195e7c.png)

## 类的方法
类方法也包括公有方法、私有方法、类方法和静态方法。如下表介绍：
![](https://img-blog.csdnimg.cn/9e3716ec00fc4e7d9855c6d08eee4d8e.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBA5biD6KGj5Lmm55SfLVB5dGhvbg==,size_20,color_FFFFFF,t_70,g_se,x_16)
类的方法举例如图所示：
![](https://img-blog.csdnimg.cn/39f273d5f46e4c0e92d7a0f76fabb9e6.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBA5biD6KGj5Lmm55SfLVB5dGhvbg==,size_20,color_FFFFFF,t_70,g_se,x_16)
类方法和静态方法原理上有以下区别：
（1）静态方法不能使用self的方式调用。
（2）静态方法调用时会预先将类中用到的属性和方法进行加载，而类方法则是随调随用。因此，类方法相比静态方法具有不占资源的优势，但是速度不及静态方法。
（3）静态方法调用类中的属性时需要使用“类名.属性”的格式。

## 内部类
内部类：类的内部定义的类，主要目的是为了更好抽象现实世界。
一般情况下不使用内部类，这样会使程序结构复杂，但是理解内部类有助于理解模块的调用。
![](https://img-blog.csdnimg.cn/069e71b2750f49c6a5eba4b07f9257c4.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBA5biD6KGj5Lmm55SfLVB5dGhvbg==,size_13,color_FFFFFF,t_70,g_se,x_16)
下面例子中，People类中又定义了Father类和Mother类两个内部类。创建内部类的实例化对象，可以通过外部类的实例化对象调用内部类完成，如Lisi = Zhangsan.Father()；也可以直接使用外部类名调用内部类，如Liming = People.Mother()。
```
class People():
    code = 0

    class Father():
        code = 1

    class Mother():
        code = 2


zhangsan = People()
lisi = zhangsan.Father()  # 第一种实例化方法
print(lisi.code)  # 输出结果：1
liming = People.Mother()  # 第二种实例化方法
print(liming.code)  # 输出结果：2
```
从例子可以看出，内部类调用有两种方式。
（1）直接使用外部类调用内部类；
（2）先对外部类进行实例化，然后再实例化内部类。

## 魔术方法
>在Python语言中，所有以双下划线“__”包起来的方法，都统称为“魔术方法”。
这些方法在实例化时会自动调用，
比如“_str__()”、“__init__()”、“__del__()”等。
使用魔术方法可以构造出非常优美的代码，比如将复杂的逻辑封装成简单的API等。
魔术方法中的“__init__()”方法一般叫做构造函数，用于初始化类的内部状态和参数。
如果不提供，Python语言会给出一个默认的“__init__()”方法
魔术方法中的“__ del __()”函数叫做析构函数，用于释放对象占用的资源。“__del__()”函数是可选的，
如果不提供，Python语言会在后台提供默认析构函数。
魔术方法中，有些可以实现属性访问控制的功能，如“__getattr__(self,name)”,
“__setattr__(self,name,value)”方法等。

魔术方法举例：
```
class People():
    name = "人"

    def __init__(self, n="非洲人"):
        self.name = n
        print("我是构造函数", self.name)  # 重写构造函数

    def __del__(self):
        print("我是析构函数", self.name)  # 重写析构函数


zhangsan = People()
lisi = People("欧美人")
zhangsan.__del__()  # 调用析构函数
print(zhangsan)
del zhangsan
# print(zhangsan) 出现错误，因为del后，对象就不存在了
```
结果如下:
```
我是构造函数 非洲人
我是构造函数 欧美人
我是析构函数 非洲人
<__main__.People object at 0x000001EAF4D09358>
我是析构函数 非洲人
我是析构函数 欧美人
```
如例子所示，对于这些魔术方法，在创建对象时可以自动执行。当对象自动执行析构函数“A.del()”后，对象仍然存在，但是在调用“del A”,后，对象就已经被回收删除，无法再次使用。

## 类间关系
### 依赖关系
用实例方法执行某个功能时，如果需要使用另一个类的实例的方法来完成，则称这两个类之间存在关联关系。下面是个例子
```
class Person():
    def play(self, tools):
        tools.run()
        print("很开心，能玩游戏了")


class Computer():
    def run(self):
        print("电脑开机，可以运行")


class Phone():
    def run(self):
        print("手机开机，可以运行")


c = Computer()
phone = Phone()
p = Person()
p.play(phone)
```
结果：
```
手机开机，可以运行
很开心，能玩游戏了
```
例子定义了Person、Computer、Phone三个类，在Person类的play()方法中，可以使用Computer类或Phone类的实例作为参数。因为在Person类方法中实现时需要Phone类实例调用方法完成，所以这两个类之间存在依赖关系。

### 关联关系
一个类的属性类型是另外一个类的类型，则称这两个类之间存在关联关系。根据属性是单值或多值，关联关系又分为一对一关联、一对多关联等。一对一关联举例如下。
![](https://img-blog.csdnimg.cn/d24ed5537d6646cebf9892f08893de1c.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBA5biD6KGj5Lmm55SfLVB5dGhvbg==,size_14,color_FFFFFF,t_70,g_se,x_16)
例子中表示的是一对一关联，Boy类中的属性girlFriend是Girl类的实例，这两个类之间存在一对一关联关系。
一对多关联：
![](https://img-blog.csdnimg.cn/439dbdd270ce4e288d3c1d5e8589a0f9.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBA5biD6KGj5Lmm55SfLVB5dGhvbg==,size_11,color_FFFFFF,t_70,g_se,x_16)
例子中表示的是一对多关联，School类中的属性teach_list是Teacher类的实例集合，这两个类之间存在一对多关联关系。

### 继承关系
类继承是在已有类基础上构建新类的机制，该新建类也成为子类。子类可以增加新的属性或功能，也可以继承父类的功能。继承所描述的是“is-a”的关系。
通过继承机制，可以复用以前代码，大大提高开发效率。
![](https://img-blog.csdnimg.cn/18a3c8f374fe4664a353f9b971d0600c.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBA5biD6KGj5Lmm55SfLVB5dGhvbg==,size_18,color_FFFFFF,t_70,g_se,x_16)
如图所示，可以说人是动物，也可以说人继承动物。人、猪、狗是继承者称之为子类或者派生类。动物是被继承者称之为父类或者超类。
![](https://img-blog.csdnimg.cn/d56375c74b5f4ab5a22cf00d99984839.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBA5biD6KGj5Lmm55SfLVB5dGhvbg==,size_18,color_FFFFFF,t_70,g_se,x_16)
例子中，首先定义了一个People类，接着从该类派生出两个子类Japan和China，然后同时以这两个类为父类，派生出类Ren。一般来说，为防止出现歧义，尽量在类定义时候避免多继承。

在Python语言中使用继承机制时，有以下几点需要注意：
>（1）子类拥有父类的属性和方法。
（2）子类可以创建自己属性和方法。
（3）子类可以对父类的方法进行覆盖实现。
（4）子类可重新定义父类中的属性。
（5）一个父类可由多个子类继承，一个子类也可继承多个父类。
（6）如果父类定义了__init__()方法，子类也定义了自己的__init__()方法并且还要使用父类的__init__()方法，
子类需要显式调用父类的__init__()方法。如果子类需要扩展父类的初始化行为，可以添加__init__()方法参数。
（7）当继承的多个父类中有相同的属性或方法时，会使用最后一个继承父类的属性或方法。

继承机制的出现，导致父类和子类相同行为出现的可能，以及在实际运行中的动态结果，此为多态。
多态（是从定义角度出发）：同一类事物的多种形态，如动物的多种形态：猫、狗、猪等。
多态性（是从使用角度出发）：同一种调用方式，不同的执行效果。具有不同功能的函数可以使用相同的函数名，这样就可以用一个函数名调用不同内容的函数。
多态性依赖于继承机制，并且要定义统一的接口。

在程序语言中，多态实质就是定义了一个函数接口，在这个函数中定义了所有类中通用的功能。根据不同对象的相同调用接口，就得到不同的结果。下面例子是多态的实现。
```
class Animal():
    def run(self):
        raise AttributeError("子类必须实现这个方法")


class Cat(Animal):
    def run(self):
        print("猫在跑")


class Pig(Animal):
    def run(self):
        print("猪在跑")


class Dog(Animal):
    def run(self):
        print("狗在跑")
a=Cat()
b=Pig()
c=Dog()
a.run()
b.run()
c.run()
```
输出结果：
```
猫在跑
猪在跑
狗在跑
这种写法最大的问题就是接口不统一，有没有一种统一接口的写法呢？如下所示：
```
def func(n):
    n.run()


a = Cat()
b = Pig()
c = Dog()
func(a)
func(b)
func(c)
```

例子中演示了多态性定义和调用的两种方式。也体现了多态依赖的两个步骤。首先，多态来自同一个父类的继承；其次，为这些不同的子类定义相同的调用接口。
使用多态性有如下优点：
（1）以不变应万变，增加了程序的灵活性。不论对象千变万化，调用方式都相同。
（2）增加了程序的可扩展性。对于子类来说，使用者无需更改调用代码。


