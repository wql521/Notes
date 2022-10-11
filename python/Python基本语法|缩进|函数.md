# Python基本语法|缩进|**函数**
## 缩进规则
* 物理行：代码编辑器中显示的代码，每一行是一个物理行。

![](https://img-blog.csdnimg.cn/20201209140621167.png#pic_center)

* 逻辑行：Python解释器对代码进行解释，一个语句是一个逻辑行。

![](https://img-blog.csdnimg.cn/20201209140610399.png#pic_center)

**可以使用";"号将多个逻辑行合并成一个物理行。**

![](https://img-blog.csdnimg.cn/a0410db3a98244f7859b656201930746.png)

**可以使用"\"对一个逻辑行进行换行，书写为多个物理行。**

![](https://img-blog.csdnimg.cn/8b4ccbbfc1684865beaed672e99ffa59.png)

**字典、列表等变量赋值语句，是可以直接换行，书写为多个物理行的。**

![](https://img-blog.csdnimg.cn/20201209150158521.png)

1. 逻辑行的“首行”需要顶格，即无缩进（也就是一份源码的第一个逻辑行）
2. 相同逻辑层（同一个代码块）保持相同的缩进量
3. **":"标记一个新的逻辑层**
while循环、if分支、函数声明、类定义等等

## **函数**
在Python语言中，函数通常是由函数名、参数列表以及一系列语句组成的函数体构成的。函数定义的一般格式如下：
```
def 函数名(参数列表)：
    函数体
    
def hello():
    print("hello")
    print("world!")
```

下列代码定义了一个计算矩形面积的函数area()和一个欢迎信息打印函数welcome()。
```
# 计算矩形面积的函数area()
def area(width, height):
    return width * height


# 输出汉英信息的函数
def welcome(name):
    print("Welcome ", name)


# 调用welcome函数
welcome('张三')
# 调用area函数
w = 4
h = 9
print("with=", w, "height=", h, "area=", area(w, h))
```
上述代码中，首先定义了area()和welcome()两个函数，其中函数area()提供了width（宽）和height（高）两个参数，函数welcome()函数只提供了一个参数name。然后，分别调用了area()和welcome()函数，在控制台输出了相应的结果，结果如下：
```
Welcome  张三
with= 4 height= 9 area= 36
```

以下代码定义了无任何操作的空函数nop()。
```
def nop():
    pass
```

* 函数代码块**以def关键字开头**，后接函数标识符名称和形参列表；
* 任何传入的**参数和自变量必须放在圆括号内**；
* 函数的第一行语句可以选择性地使用文档字符串（即函数说明）；
* 函数内容以冒号起始，并且严格统一缩进；
* **函数都有返回值，默认返回None。**

### 形参和实参
在编程语言中，函数定义时用的是形参，调用时用的是实参
> 形参（parameter），全称为"形式参数"，不是实际存在的变量，又称虚拟变量。形参是在定义函数名和函数体的时候使用的参数，目的是用来接收调用该函数时传入的参数。

实参(argument)，全称为"实际参数"，是在调用时传递给函数的参数。实参可以是常量、变量、表达式、函数等。无论实参是何种类型的量，在进行函数调用时，它们都必须具有确定的值，以便把这些值传送给形参。

形参和实参的功能是数据传送。

在调用函数时，实参将赋值给形参。必须注意实参的个数、类型应与形参要一一对应，并且实参必须要有确定的值。形参的作用域一般仅限函数体内部，而实参的作用域根据实际设置而定。

以计算面积的函数为例：
```
# 计算矩形面积的函数area()
def area(width, height):
    return width * height


# 调用area函数
w = 4
h = 9
print("with=", w, "height=", h, "area=", area(w, h))
```
上述代码中，函数area()定义处的width和height就是形式参数，函数体外定义的变量w和h是实际参数。可以看到，把实参w和h传入函数体后，就把相应的值赋值给了形参width和height。形参width和height的作用域只限于area()函数体内，而实参w和h作用域则根据外部调用处的设置而定。

对于函数形参列表，默认情况下函数调用时的参数值与参数列表声明中定义的顺序是一致。Python语言也允许函数调用时参数顺序与声明时不一致，即显示指明关键字参数，并根据参数的指定进行赋值。
```
def func(x, y):
    print('x+y=', x + y)
    print('x*y=', x * y)


# 等效于func(x=3,y=2)，也等效于func(3,2)
func(y=2, x=3)
```
上述代码中，函数func()定义时形式参数的顺序是func(x, y)，但是调用时实际参数的顺序确是func(y = 1, x = 2)。这是因为Python语言中提供了一种关键字参数的机制，可以给开发者提供更大的灵活性。

### 函数返回值
> 函数的返回值是函数执行完成后，系统根据函数的具体定义返回给外部调用者的值。

在实际开发中，有时不仅仅要执行某个函数的功能，而且还需要把该函数的执行结果作为其他函数或功能的计算单元。所以，函数返回值是非常有用的

在Python语言中，当函数运行到return语句时即执行完毕，同时将结果返回。因此，可以在函数内部通过条件判断和循环设置实现较复杂的逻辑，并返回预期的结果。如果没有return语句，函数体内所有语句执行完毕后默认返回None。

```
# 函数定义
def add(x, y):
    print('x+y=', x + y)
    return x + y


# 函数调用
result = add(y=1, x=2)
print(result)
```
上述代码中，定义的add()函数返回“x+y”的运算结果。可以看到，调用该函数后，把该函数的返回值赋值给了变量result ，最后输出了变量result 的值。

另外需要注意的是，在Python语言中，函数也可以有多个返回值，例如：
```
# 函数定义
def add(x, y):
    print('x+y=', x + y)
    print('x*y=', x * y)
    return x + y, x * y


# 函数调用
a, b = add(y=1, x=2)
print(a, b)
```
上述代码中，定义的add()函数有连个返回值，分别是“x+y”和“x*y”。可以看到，调用该函数后，把该函数的返回值分别赋值给变量a，b，最后输出了变量a和变量b的值。
注意： 返回值和接收变量的对应关系，是按照顺序一一对应的

### 内置函数

![](https://img-blog.csdnimg.cn/370218a1ee13497aa9e14a75430aadc1.png)

### 自定义函数
```
from test import hello

hello()
```
上述代码演示了函数的定义和调用不在一个文件的情形。首先，将hello()函数定义好并保存为test.py文件，然后使用Python语言的import指令“from test import hello”将该文件导入，可以调用hello()函数了。导入时需要注意test是文件名并且不含.py扩展名。

### 参数种类
函数参数分为可变类型和不可变类型，其调用结果是不同的。
（1）可变类型：类似c++的引用传递，如列表、字典等。如果传递的参数是可变类型，则在函数内部对传入参数的修改会影响到外部变量。
（2）不可变类型：类似c++的值传递，如整数、字符串、元组等。如果传递的参数是不可变类型，则在函数内部对传入参数的修改不会影响到外部变量。

不可变类型参数实例：
```
def change_int(a):
    a = 10


b = 2
change_int(b)
print(b)  # 结果是2
```
上述实例中，有int类型的对象2，指向它的变量是b。在传递给change_int（）函数时，按传值方式复制了变量b，a和b都指向了同一个int对象。在a=10时，则新生成一个int值对象10，并让a指向它。
一个更详细的例子，用id打印出变量的内存地址，可以看出函数内核函数外的内存发生了变化，说明用的是不同的内存单元，存放不同的数据：

![](https://img-blog.csdnimg.cn/031e421428784982b326daacfa6f8378.png)

可变类型参数实例：
```
def change_int(my_list):
    "修改传入的列表"
    my_list.append([1, 2, 3])
    print("函数内修改后的变量：", my_list)


my_list = [10, 20, 30]
change_int(my_list)
print("函数外变量的值：", my_list)
```
在调用函数时，如果传入的参数是可变类型，则外部变量也会被更改。在上述例子中，传入函数的list对象和在末尾添加新内容的mylist对象用的是同一个引用。
从下图中内存地址可以看出，变量的内存地址没有发生变化，说明是用的同一块内存：

![](https://img-blog.csdnimg.cn/2263aa50072b4c66a3b767f38099e5a2.png)

* 在定义函数时，开发者把参数的名字和位置确定后，函数的接口定义就完成了。
* Python语言的函数定义非常简单，但灵活度却非常大。
* 函数定义中可能包含多个形参，因此函数调用中也可能包含多个实参。
* 想让函数传递实参的方式有很多，可使用位置实参，要求传入参数和定义参数的顺序相同；也可使用关键字实参，每个实参都由变量名和值组成

### 位置参数
调用函数时，Python语言必须将函数调用中的每个实参都关联到函数的相应形参。最简单的关联方式是基于实参的顺序，这种关联方式被称为位置实参。下面代码显示学生信息的函数，该函数输出学生的名字及年龄。
```
def describe_student(person_name, student_age):
    "函数功能：显示学生的信息"
    print("my name is ", person_name)
    print(person_name + "is" + student_age + "years old")


describe_student('Jack', '24')
```
输出:
```
my name is  Jack
Jackis24years old
```
上述函数describe_student()的定义表明，它需要姓名和年龄两个参数。调用describe_student()函数时，需要按顺序提供姓名和年龄参数。函数调用时，实参’Jack’ 存储在形参person_name中，而实参’24’ 存储在形参student_age 中。

定义了函数后，开发者可以根据需要多次调用函数。如果需要再描述一名学生，只需再次调用describe_student() 即可，如下代码所示。
```
def describe_student(person_name, student_age):
    "函数功能：显示学生的信息"
    print("my name is ", person_name)
    print(person_name + "is" + student_age + "years old")


describe_student('Jack', '24')
describe_student('Bob', '17')
```
结果：
```
my name is  Jack
Jackis24years old
my name is  Bob
Bobis17years old
```
调用函数是一种效率极高的开发方式。如在上例中，开发者只需在函数中编写描述学生的代码一次，以后需要描述新学生时，都可调用这个函数，并向它提供新的学生信息。即便描述全校的学生，依然只需使用一行调用函数的代码，就可实现所需功能。

在函数中，可根据需要使用任意数量的位置实参。Python语言将按顺序将函数调用中的实参关联到函数定义中相应的形参。但要注意的是，在使用位置实参来调用函数时，如果实参的顺序不正确，结果可能出乎意料，如下代码所示。
```
def describe_student(person_name, student_age):
    "函数功能：显示学生的信息"
    print("my name is ", person_name)
    print(person_name + "is" + student_age + "years old")


describe_student('18', 'Jack')
```
结果：
```
my name is  18
18isJackyears old
```
在上述函数调用中，开发者先指定名字，再指定学生年龄。由于实参’18’ 在前，这个值将存储到形参person_name中；同理，‘Jack’ 将存储到形参student_age中。在实际开发中，如果执行结果和预期不一致，请核查函数调用中实参的顺序与函数定义中形参的顺序是否一致。

### 默认参数

编写函数时，可给每个形参指定默认值。在调用函数时，如果给形参提供了实参，Python语言将使用指定的实参值；否则，将使用形参的默认值。给形参指定默认值后，可在函数调用中省略相应的实参。使用默认值可简化函数调用，还可清楚地指出函数的典型用法。如下方式调用describe_student（）函数会出现错误。
```
def describe_student(person_name, student_age):
    "函数功能：显示学生的信息"
    print("my name is ", person_name)
    print(person_name + "is" + student_age + "years old")


describe_student('Jack')
```
提示错误信息：
```
Traceback (most recent call last):
  File "D:/python_demo/demo_2.py", line 88, in <module>
    describe_student('Jack')
TypeError: describe_student() missing 1 required positional argument: 'student_age'
```
上述代码中，提示的错误信息很明确，就是调用函数describe_student()时缺少了一个位置参数student_age。这个时候，默认参数就排上用场了

若大部分学生的年龄为18岁，开发者可以把第二个参数student_age的默认值设定为18，这样，当开发者调用describe_student(Jack)时，相当于调用describe_student(Jack,18) ，如下代码所示。
```
def describe_student(person_name, student_age='18'):
    "函数功能：显示学生的信息"
    print("my name is ", person_name)
    print(person_name + "is" + student_age + "years old")


describe_student('Jack')
describe_student('Jack', '18')
```
结果：
```
my name is  Jack
Jackis18years old
my name is  Jack
Jackis18years old
```
对于年龄不是18岁的学生，就必须明确地传入student_age，如describe_student(‘Herbie’,19)。从上面的例子可以看出，默认参数可以简化函数的调用。

要注意的是，设置默认参数时，必选参数在前，默认参数在后，否则Python语言的解释器会报错。使用默认参数最大的好处是能降低调用函数的难度。编写一个学生注册的函数，需要传入name和gender两个参数。
```
def enroll(name, gender):
    "注册学生的信息"
    print("name:", name)
    print("gender:", gender)


enroll('Jack', 'F')
```
结果：
```
name: Jack
gender: F
def enroll(name, gender, age='18', city='Beijing'):
    "注册学生的信息"
    print("name:", name)
    print("gender:", gender)
    print("age:", age)
    print("city:", city)


enroll('Sarah', 'F')
print('-' * 70)
enroll('Sarah', 'M', '17')
```
结果：
```
name: Sarah
gender: F
age: 18
city: Beijing
----------------------------------------------------------------------
name: Sarah
gender: M
age: 17
city: Beijing
```
默认参数降低了函数调用的难度，而一旦需要更复杂的调用时，又可以传递更多的参数来实现。无论是简单调用还是复杂调用，函数只需要定义一个；当有多个默认参数时，调用时可以按顺序提供默认参数。

默认参数很有用，但使用时要牢记一点，默认参数必须指向不可变对象，否则会出现错误，如下代码所示。
```
def test_add(a=[]):
    a.append('END')
    return a


print(test_add([1, 2, 3]))
print(test_add(['a', 'b', 'c']))
print(test_add())
print(test_add())
print(test_add())
```
结果：
```
[1, 2, 3, 'END']
['a', 'b', 'c', 'END']
['END']
['END', 'END']
['END', 'END', 'END']
```
从上述代码可以看出，默认参数是空列表[]，但是函数test_add()似乎每次都“记住了”上次添加了’END’后的list。这是因为在Python语言中，函数在定义的时候，默认参数H的值就被计算出来了，即[]。因为默认参数H也是一个变量，它指向对象[]。每次调用该函数，如果改变了H的内容，则下次调用时，默认参数的内容就变了，不再是函数定义时的[]了。

开发者也可以用None这个不可变对象来解决报错问题，如下代码所示。
```
def test_add(H=None):
    if H is None:
        H = []
    H.append('END')
    return H


print(test_add())
print(test_add())
```
结果：
```
['END']
['END']
```
对于str、None等类似的不可变对象一旦创建，其内部数据就不能修改，这样就减少了由于修改数据导致的错误。
此外，由于对象不变，多线程环境下同时读取对象不需要加锁，同时读也没有问题。开发者在编写程序时，如果可以设计一个不可变对象，就尽量设计成不可变对象。

### 不定长参数

在Python语言中，函数还可以定义不定长参数，也叫可变参数。给定一组数字a，b，c……，请计算a+b+c+ ……。要定义出这个函数，必须确定输入的参数。开发者可以把a，b，c……作为一个list或tuple传进来。
```
def calc(numbers):
    sum = 0
    for n in numbers:
        sum = sum + n
    return sum


print(calc([1, 2, 3])) # 结果是6
print(calc([1, 2, 3,4])) # 结果是10
```
对于以上定义的求和函数，调用的时候，需要先组装出一个list或tuple；在Python语言中，可以在函数参数前面添加“*”号把该参数定义为不定长参数；可以看出，不定长参数的使用使得calc()函数定义和调用都变得简洁，实例如下所示：
```
def calc(*numbers):
    sum = 0
    for n in numbers:
        sum = sum + n
    return sum


print(calc(1, 2, 3, 4))
print(calc())
num = [1, 2, 3]
print(calc(*num))
```
结果：
```
10
0
6
2.3.5 关键字参数
```
关键字实参是传递参数时使用“名称–值”对的方式，在实参中将名称和值关联起来。
关键字实参让开发者无需考虑函数调用中的实参顺序，清楚地指出了函数调用中各个值的用途。
关键字参数有扩展函数的功能。

### 命名关键字参数

如果要限制关键字参数的名字，可以用命名关键字参数。和关键字参数**kw不同，如果没有可变参数，命名关键字参数就必须加一个“”号作为特殊分隔符。如果缺少“”，Python语言解释器将无法识别位置参数和命名关键字参数。例如，若只接收age和city作为关键字参数，可以采用如下形式。
```
def enroll(name, gender, *, age, city):
    print(name, gender, age, city)


enroll('Jack', 'M', age='18', city='Beijing')
```
输出：
```
Jack M 18 Beijing
def enroll(name, gender, *grade, age, city):
    print(name, gender, age, city)


enroll('Jack', 'M', '18', 'Beijing')
```
结果报错：
```
Traceback (most recent call last):
  File "D:/python_spider/python_demo/demo_2.py", line 119, in <module>
    enroll('Jack', 'M', '18', 'Beijing')
TypeError: enroll() missing 2 required keyword-only arguments: 'age' and 'city'
def enroll(name, gender, *, age='18', city):
    print(name, gender, age, city)


enroll('Jack', 'M', city='Beijing') # 结果是：Jack M 18 Beijing
```
注意：
*表示不定长参数
**表示不定长的关键字参数

### 参数组合

在Python语言中定义函数，开发者可以组合使用这些参数（必选参数、默认参数、可变参数、关键字参数和命名关键字参数）。注意参数定义是有顺序的。定义的顺序必须是：必选参数、默认参数、可变参数、命名关键字参数和关键字参数。比如要定义一个函数，包含上述若干种参数，如下代码所示。
```
def func(a, b, c=0, *args, **kw):
    print('a=', a, 'b=', b, 'c=', c, 'args=', args, 'kw=', kw)


print(func(1, 2))  
# 输出结果：a= 1 b= 2 c= 0 args= () kw= {}
print(func(1, 2, c=3))  
# 输出结果：a= 1 b= 2 c= 3 args= () kw= {}
print(func(1, 2, 3, 'a', 'b'))  
# 输出结果：a= 1 b= 2 c= 3 args= ('a', 'b') kw= {}
print(func(1, 2, 3, 'a', 'b', x=4))  
# 输出结果：a= 1 b= 2 c= 3 args= ('a', 'b') kw= {'x': 4}
args = (1, 2, 3, 4)
kw = {'x': 5}
print(func(*args, **kw))  
# 输出结果：a= 1 b= 2 c= 3 args= (4,) kw= {'x': 5}
```
### 函数式编程

函数式编程是一种编程范式，是面向数学的抽象，其将计算描述为一种表达式求值。
函数式编程中的“函数”不是指计算机中的函数，而是指数学中的函数，即自变量的映射。
函数式编程的一个特点就是，允许把函数本身作为参数传入另一个函数，还允许返回一个函数。
Python语言对函数式编程提供部分支持。由于允许使用变量，所以说Python语言不是纯函数式编程语言。
### 高阶函数

接受函数为参数，或者把函数作为结果返回的函数称为高阶函数。例如，若要根据单词的长度排序，只需把len函数传给key参数。
```
fruits=['strawberry','fig','apple','cherry','raspberry','banana']
print(sorted(fruits,key=len))
# 输出结果如下：
# ['fig', 'apple', 'cherry', 'banana', 'raspberry', 'strawberry']
fruits = ['strawberry', 'fig', 'apple', 'cherry', 'raspberry', 'banana']


def reverse(word):
    return word[::-1]


print(reverse('testing'))  # 结果是：gnitset

print(sorted(fruits, key=reverse))
# 输出结果如下：
# ['banana', 'apple', 'fig', 'raspberry', 'strawberry', 'cherry']
```
注意，上述例子中列表里的单词没有变，开发者只是把反向拼写当作排序条件，因此各种浆果（berry）都排在一起。在函数式编程范式中，最为人熟知的高阶函数有map、filter、reduce 和apply。其中，apply函数在Python2.3中标记为过时，在Python3已移除。

### 匿名函数

所谓匿名函数，即不再使用def语句这样标准形式定义的函数。Python语言经常使用lambda来创建匿名函数。lambda 只是一个表达式，函数体比def定义的函数体要简捷。lambda函数的语法如下所示。
```
lambda [arg1[,arg2],....argn]]:expression
```
举例：
```
sum = lambda arg1, arg2: arg1 + arg2
print(sum(1, 2)) # 结果是：3
```
上述代码中，第一行定义了一个lambda函数，执行两个数的和运算，并且把该lambda函数命名为sum。会面的代码通过sum（）函数即实现了调用lambda函数的功能。

