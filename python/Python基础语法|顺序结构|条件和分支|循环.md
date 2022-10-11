# Python基础语法|顺序结构|条件和分支|循环
**程序有三种基本的控制结构：顺序结构、选择结构、循环结构。**
## 顺序结构
顺序结构是最简单也是最常见的一种结构，采用顺序结构的程序通常按照由前到后的顺序执行各个语句，直到程序结束，结构如下所示：
顺序结构：
![](https://img-blog.csdnimg.cn/59f690f25e9b419b86eaa4f6386fdbec.png)
```
a = 2
b = 3
c = a + b
d = c * 24
print(a, b, c, d)
```

## 条件和分支
条件语句是通过判断条件是否成立，根据条件表达式的结果做出决策，控制不同代码块的执行。
### 条件表达式
条件表达式由运算符和操作数组成

例如：a<4，其中a、4都是操作数，小于符号<是运算符

判断条件可以是具有布尔属性的任意元素，包括数据、变量或由变量与运算符组成的表达式，若其布尔属性为True，条件成立；若布尔属性为False，条件不成立。
除了非空常量外，Python还常使用关系操作符和成员运算符构成判断条件 。

条件表达式常用的运算符有：
算术运算符：+、-、*、/、//、%、**
关系运算符：
![](https://img-blog.csdnimg.cn/aae4d68d5b2043f6967990c610567bcd.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBA5biD6KGj5Lmm55SfLVB5dGhvbg==,size_17,color_FFFFFF,t_70,g_se,x_16)
Python支持通过保留字not、and和or对判断条件进行逻辑组合：

* not，表示单个条件的“否”关系。如果“条件”的布尔属性为True，“not 条件”的布尔属性就为False；如果“条件”的布尔属性为False，“not 条件”的布尔属性就为True。
* and，表示多个条件之间的“与”关系。当且仅当使用and连接的所有条件的布尔属性都为True时，逻辑表达式的布尔属性为True，否则为False。
* or，表示多个条件之间的“或”关系。当且仅当使用or连接的所有条件的布尔属性都是False时，逻辑表达式的布尔属性为False，否则为True。

### 单分支结构
![](https://img-blog.csdnimg.cn/f14fef2e3b854c2aa2b1ffb91f858e6b.png)
* 若if语句中的判断条件成立，执行if语句后的代码段；
* 若判断条件不成立，则跳过if语句后的代码段。
* 单分支结构中的代码段只有“执行”与“跳过”两种情况。
示例：使用单分支结构判断当天是否是星期天。
```
day = int(input("今天是工作日吗（请输入整数1~7）？"))
if day in [1,2,3,4,5]:
	print("今天是工作日。")
if day in [6,7]:
	print("今天非工作日。")
```

### 双分支结构
![](https://img-blog.csdnimg.cn/ad9f942df1524da9899e4a8ba7c4076b.png)
* 若if语句中的判断条件成立，执行代码段1
* 若判断条件不成立，则执行代码段2
示例：使用二分支结构判断当天是否是工作日。
```
day = int(input("今天是工作日吗（请输入整数1~7）？"))
if day in [1,2,3,4,5]:
	print("今天是工作日。")
else:
	print("今天非工作日。")
```
### 多分支选择结构
![](https://img-blog.csdnimg.cn/2cf973c864744f0c9de89eeba858753a.png)
![](https://img-blog.csdnimg.cn/3bd587570bcb43f29bd6bffc77a8a78d.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBA5biD6KGj5Lmm55SfLVB5dGhvbg==,size_13,color_FFFFFF,t_70,g_se,x_16)
### 选择结构的嵌套
选择结构的嵌套是指选择结构的内部包含选择结构
![](https://img-blog.csdnimg.cn/730f1dbf91ca4f4bb1ea8e31000c4fe5.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBA5biD6KGj5Lmm55SfLVB5dGhvbg==,size_8,color_FFFFFF,t_70,g_se,x_16)
![](https://img-blog.csdnimg.cn/c77765c0c52a4244986bd8ca551c7e34.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBA5biD6KGj5Lmm55SfLVB5dGhvbg==,size_12,color_FFFFFF,t_70,g_se,x_16)

### 三元表达式
python中没有c语言中的三目运算符，但是可以通过以下的形式实现三目运算符的功能
格式：条件判断为真时的结果 if 判断条件 else 条件为假时的结果
示例：x=x-1 if x>0 else x=x+1
等价于：
```
if x > 0:
    x = x - 1
else:
    x = x + 1
```
我们可以利用三元表达式来实现裴波那契数列：
```
def fun(n):
    return n if n < 2 else fun(n - 1) + fun(n - 2)
还有一种用法，用bool方法选择相应的值，例如：

x = 1
print([2, 3][bool(x)])
x = 0
print([2, 3][bool(x)])
```
结果：
```
3
2
```

## 循环结构
在实际应用中有些需要重复进行的操作，可以用循环语句实现。

循环语句有：
while、do while、for

### while循环
![](https://img-blog.csdnimg.cn/4b01bac47d1f4f3e84ff002de253e57b.png)
* 若循环条件为True，则循环执行while循环中的代码段；
* 若循环条件为False，终止while循环。
* 若while循环的条件总是True，这种情况叫做死循环 。
例如：使用while循环实现计算n的阶乘
```
n = int(input("请输入一个整数："))
fact = 1
i = 1
while i<= n:
	fact = fact*i
	i = i + 1
print("n!={}".format(fact))
```

### while else循环
Python的while循环也支持使用保留字else产生分支。

示例2：使用while-else循环实现计算n的阶乘
```
n = int(input("请输入一个整数："))
fact = 1
i = 1
print("n!计算中……")
while i<= n:
	fact = fact*i
	i = i + 1
else:
	print("n!计算完成 ，循环正常结束")
print("n!={}".format(fact))
```

### for循环
![](https://img-blog.csdnimg.cn/d898c790ad4543a8922375100c76af9e.png)
* 目标可以是字符串、文件、range()函数或组合数据类型等；
* 循环变量用于保存本次循环中访问到的遍历结构中的元素；
* for循环的循环次数取决于遍历的目标元素个数。
示例1：遍历字符串中的每个字符
```
string = input("请输入一个字符串：")
for c in string:
	print(c)
```

### for else循环
for…else循环的具体实现形式：
```
for 循环变量 in 目标:
    循环体
else:
    代码块
```
用法与while…else相同，如果循环体结束后没有碰到break语句，就会执行else语句块，如果结束之前碰到了break语句，就会跳出整个for循环，因此else语句块也就不会执行。

### 循环控制语句
在循环语句中，有时候需要达到中断循环，或者跳过本次循环，执行下次循环的情况，因此就需要有循环控制语句

python中使用break、continue语句控制循环的执行过程

break用于跳出整个循环
continue用于跳出本次循环，继续执行下次循环
#### break语句
![](https://img-blog.csdnimg.cn/2518d2761a5e433a99ad88796236a05d.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBA5biD6KGj5Lmm55SfLVB5dGhvbg==,size_9,color_FFFFFF,t_70,g_se,x_16)
![](https://img-blog.csdnimg.cn/4274a72546b84f39be54688d3387bb6e.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBA5biD6KGj5Lmm55SfLVB5dGhvbg==,size_11,color_FFFFFF,t_70,g_se,x_16)
#### continue语句
![](https://img-blog.csdnimg.cn/090910fe5b8d4a8986e9a17c36b6ef5c.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBA5biD6KGj5Lmm55SfLVB5dGhvbg==,size_9,color_FFFFFF,t_70,g_se,x_16)
![](https://img-blog.csdnimg.cn/39ce4980fad94842824d72456b0ee1a4.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBA5biD6KGj5Lmm55SfLVB5dGhvbg==,size_10,color_FFFFFF,t_70,g_se,x_16)
#### pass语句
pass的意思是过，pass掉就是淘汰掉的意思。

在python中，pass的意思是空语句，pass语句不做任何事情，只是为了保持程序结构的完整性。