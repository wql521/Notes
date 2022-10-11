# Python 基础知识|程序设计思想
Python 是**解释型语言**： 开发过程中没有了编译这个环节。类似于PHP和Perl语言。
Python 是**交互式语言**： 可以在一个 Python 提示符 >>> 后直接执行代码。
Python 是**面向对象语言**: Python支持面向对象的风格或代码封装在对象的编程技术。
python 是一门**脚本语言**,它不需要编译,它的执行只与解释器有关
## 字符串的编码格式
Python3.0 默认采用**Unicode编码**对字符串进行编码。

## 输出和输入方面
Python3.0 使用 **print()** 函数输出，比如：print("Hello")。
Python3.0 使用 **input()** 函数输入，比如：name=input("请输入你的名字：")。

## 格式化字符串的方式
Python3.0 用 **format()** 函数，比如：”Hello,{}“.format("World")。

## 原文件的编码格式
Python3.0 默认采用**utf-8**。

## Python 编译和运行过程
<div class="mermaid">
graph LR
    1[python源码 .py] ===> 2[python解释器] ===> 3[python字节码 .pyc] ===> 4[PVM python虚拟机] ===> 5[在线终端输出结果]
</div>

> 首先将Python源代码（.py文件）编译生成Python字节码（Python Byte Code，字节码文件的扩展名一般是.pyc），然后再由Python虚拟机（Python Virtual Machine，简称PVM）来执行Python字节码，最后在终端输出运行结果。
> 
python是一种解释型语言,解释python字节码.

## Python字节码（.pyc）
Python中的字节码(bytecode) 是一种数据类型， Python代码的编译结果就是bytecode对象。bytecode对象可以由虚拟机加载后直接运行，而pyc文件就是bytecode在硬盘上的保存形式。

假如有个test.py文件需要执行，那么它会先生成.pyc文件，一般可能的情况如下：

执行 python test.py 会对test.py进行编译成字节码并解释执行，但不会生成test.pyc。
如果test.py中加载了其他模块，如import urllib2，那么python会对urllib2.py进行编译成字节码，生成urllib2.pyc，然后对字节码解释执行。
如果想生成test.pyc，可以使用python内置模块**py_compile**来编译，也可以执行命令 **python -m py_compile test.py** 这样，就生成了test.pyc。
加载模块时，如果同时存在.py和.pyc，python会使用.pyc运行，如果.pyc的编译时间早于.py的时间，则重新编译 .py文件，并更新.pyc文件。

## 程序设计思想
### 基本的程序设计模式
任何的程序设计都包含IPO，它们分别代表如下：
> I：Input 输入，程序的输入
P：Process 处理，程序的主要逻辑过程
O：Output 输出，程序的输出

因此如果想要通过计算机实现某个功能，那么基本的程序设计模式包含三个部分，如下：
> 确定IPO：明确需要实现功能的输入和输出，以及主要的实现逻辑过程；
编写程序：将计算求解的逻辑过程通过编程语言进行设计展示；
调试程序：对编写的程序按照逻辑过程进行调试，确保程序按照正确逻辑正确运行。

### 解决复杂问题的有效方法：自顶向下（设计）
#### 自顶向下-分而治之
如果要实现功能的逻辑比较复杂的时候，就需要对其进行模块化设计，将复杂问题进行分解，转化为多个简单问题，其中简单问题又可以继续分解为更加简单的问题，直到功能逻辑可以通过模块程序设计实现，这也是程序设计的自顶向下特点。总结如下：
>将一个总问题表达为若干个小问题组成的形式
使用同样方法进一步分解小问题
直至，小问题可以用计算机简单明了的解决

#### 举例1：体育竞技分析
##### 程序总体框架
>printlnfo()                步骤1:打印程序的介绍性信息                    
getlnputs()              步骤2:获得程序运行参数：proA, proB, n         
simNGames()         步骤3:利用球员A和B的能力值，模拟n局比赛         
printSummary()      步骤4:输出球员A和B获胜比赛的场次及概率     

##### 程序设计
```
# 导入python资源包
from random import random
 
# 用户体验模块 
def printIntro():
    print("这个程序模拟两个选手A和B的某种竞技比赛")
    print("程序运行需要A和B的能力值（以0到1之间的小数表示）")
 
# 获得A和B的能力值与场次模块 
def getIntputs():
    a = eval(input("请输入A的能力值（0-1）："))
    b = eval(input("请输入B的能力值（0-1）："))
    n = eval(input("模拟比赛的场次："))
    return a, b, n
 
# 模拟n局比赛模块 
def simNGames(n, probA, probB):
    winsA, winsB = 0, 0
    for i in range(n):
        scoreA, scoreB = simOneGame(probA, probB)
        if scoreA > scoreB:
            winsA += 1
        else:
            winsB += 1
    return winsA, winsB
 
# 判断比赛结束条件 
def gameOver(a, b):
    return a == 15 or b == 15
 
# 模拟n次单局比赛=模拟n局比赛 
def simOneGame(probA, probB):
    scoreA, scoreB = 0, 0
    serving = "A"
    while not gameOver(scoreA, scoreB):
        if serving == "A":
            if random() < probA:
                scoreA += 1
            else:
                serving = "B"
        else:
            if random() < probB:
                scoreB += 1
            else:
                serving = "A"
    return scoreA, scoreB
 
# 打印结果模块 
def printSummary(winsA, winsB):
    n = winsA + winsB
    print("竞技分析开始，共模拟{}场比赛".format(n))
    print("选手A获胜{}场比赛，占比{:0.1%}".format(winsA, winsA / n))
    print("选手B获胜{}场比赛，占比{:0.1%}".format(winsB, winsB / n))
 
 
def main():
    printIntro()    
    probA, probB, n = getIntputs()                # 获得用户A、B能力值与比赛场次N
    winsA, winsB = simNGames(n, probA, probB)     # 获得A与B的场次
    printSummary(winsA, winsB)                    # 返回A与B的结果
 
 
main()
```
#### 举例2：的斐波那契数列
##### 程序设计
```
cache = {}

def fib(number):
    if number in cache:
        return cache[number]
    if number == 0 or number == 1:
        return 1
    else:
        cache[number] = fib(number - 1) + fib(number - 2)
    return cache[number]

if __name__ == '__main__':
    print(fib(35))
```
>14930352

### 逐步组建复杂系统的有效测试方法：自底向上（执行）
#### 自底向上-模块化集成
自底向上（执行）就是一种逐步组建复杂系统的有效测试方法。首先将需要解决的问题分为各个三元进行测试，接着按照自顶向下相反的路径进行操作，然后对各个单元进行逐步组装，直至系统各部分以组装的思路都经过测试和验证。
自底向上分析思想：
任何时候栈中符号串和剩余符号串组成一个句型，当句柄出现在栈顶符号串中时，就用该句柄进行归约，这样一直归约到输入串只剩结束符、栈中符号只剩下开始符号，此时认为输入符号串是文法的句子，否则报错。
>自底向上是⼀种求解动态规划问题的方法，它不使用递归式，而是直接使用循环来计算所有可能的结果，往上层逐渐累加子问题的解。在求解子问题的最优解的同时，也相当于是在求解整个问题的最优解。其中最难的部分是找到求解最终问题的递归关系式，或者说状态转移方程。

#### 举例：0-1背包问题
##### 问题描述
你现在想买⼀大堆算法书，有一个容量为 V 的背包，这个商店⼀共有 n 个商品。问题在于，你最多只能拿 W kg 的东西，其中 wi 和 vi 分别表示第 i 个商品的重量和价值。最终的目标就是在能拿的下的情况下，获得最大价值，求解哪些物品可以放进背包。

对于每⼀个商品你有两个选择：拿或者不拿。
##### 自底向上分析
⾸先要做的就是要找到“子问题”是什么。通过分析发现：每次背包新装进⼀个物品就可以把剩余的承重能力作为⼀个新的背包来求解，⼀直递推到承重为0的背包问题。

用 m[i,w] 表示偷到商品的总价值，其中 i 表示⼀共多少个商品，w 表示总重量，所以求解 m[i,w]就是子问题，那么看到某⼀个商品i的时候，如何决定是不是要装进背包，需要考虑以下：
1. 该物品的重量大于背包的总重量，不考虑，换下⼀个商品；
2. 该商品的重量小于背包的总重量，那么尝试把它装进去，如果装不下就把其他东西换出来，看看装进去后的总价值是不是更高了，否则还是按照之前的装法；
3. 极端情况，所有的物品都装不下或者背包的承重能力为0，那么总价值都是0；

由以上的分析，可以得出m[i,w]的状态转移方程为：
>m[i,w] = max{m[i-1,w], m[i-1,w-wi]+vi}

##### 程序设计
```
# 循环的⽅式，自底向上求解
cache = {}
items = range(1,9)
weights = [10,1,5,9,10,7,3,12,5]
values = [10,20,30,15,40,6,9,12,18]
# 最⼤承重能⼒
W = 4

def knapsack():
    for w in range(W+1):
        cache[get_key(0,w)] = 0
    for i in items:
        cache[get_key(i,0)] = 0
        for w in range(W+1):
            if w >= weights[i]:
                if cache[get_key(i-1,w-weights[i])] + values[i] > cache[get_key(i-1,w)]:
                    cache[get_key(i,w)] = values[i] + cache[get_key(i-1,w-weights[i])]
                else:
                    cache[get_key(i,w)] = cache[get_key(i-1,w)]
            else:
                cache[get_key(i,w)] = cache[get_key(i-1,w)]
    return cache[get_key(8,W)]

def get_key(i,w):
    return str(i)+','+str(w)

if __name__ == '__main__':
    # 背包把所有东西都能装进去做假设开始
    print(knapsack())
```
>29

### 代码编码格式
* 一般来说，声明编码格式在脚本中是必需的。
* 国际惯例，文件编码和 Python 编码格式全部为 utf-8 。例如：在 Python 代码的开头，要统⼀加上如下代码：
`# -- coding: utf-8 --`
* 如果Python源码文件没有声明编码格式，Python解释器会默认使用ASCII编码。但出现非ASCII编码的字符，Python解释器就会报错，因此非 ASCII 字符的字符串，请需添加u前缀。
* 若出现 Python编码问题，可按照以下操作尝试解决：
```
import sys
reload(sys)
sys.setdefaultencoding('utf-8')
```

### 注释
#### 行注释
* 注释由#和一个空格开始
```
n = input()
m = input()
t = n / 2     # t是n的一半

# 循环，条件为t*m/n 小于n
while (t * m / (n + 1) < n):
    t = 0.5 * m + n / 2     # 重新计算t值
print(t)
```

#### 块注释
```
# We use a weighted dictionary search to find out where i is in
# the array.  We extrapolate position based on the largest num
# in the array and the array size and then do binary search to
# get the exact number.
```

#### 文档注释
* 要为所有的公共模块，函数，类和方法编写文档说明
* 非公共的方法没有必要，但是应该有一个描述方法具体作用的注释。这个注释应该在def那一行之后
* 多行文档注释使用的结尾三引号应该是自成一行
```
class SampleClass(object):
    """Summary of class here.

    Longer class information....
    Longer class information....

    Attributes:
        likes_spam: A boolean indicating if we like SPAM or not.
        eggs: An integer count of the eggs we have laid.
    """

    def __init__(self, likes_spam=False):
        """Inits SampleClass with blah."""
        self.likes_spam = likes_spam
        self.eggs = 0

    def public_method(self):
        """Performs operation blah."""
```

### 空格使用规则
* 在**二元运算符两边各空一格**，比如赋值(=)、比较(==, <, >, !=, <>, <=, >=, in, not in, is, is not), 布尔(and, or, not)，算术操作符两边的空格可灵活使用，但两侧务必要保持一致
* **不要在逗号、分号、冒号前面加空格**，但应该**在它们后面加**（除非在行尾）
* **函数**的参数列表中，**逗号之后要有空格**
* **函数**的参数列表中，**默认值等号两边不要添加空格**
* 左括号之后，右括号之前不要加添加空格
* 参数列表， 索引或切片的左括号前不应加空格
* 当'='用于指示关键字参数或默认参数值时，不要在其两侧使用空格

### 函数命名
* 函数名应该小写，如有多个单词，用下划线隔开。
* 大小写混合仅在为了兼容原来主要以大小写混合风格的情况下使用，保持向后兼容。
* 私有函数在函数前加一个**下划线_**。
```
def run():
    pass

def run_with_env():
    pass


class Person():
    def _private_func():
        pass
```

### 模块导入规则
* 导入应该放在文件顶部，位于模块注释和文档字符串之后，模块全局变量和常量之前。
* 导入应该按照从最通用到最不通用的顺序分组：标准库导入、第三方库导入、应用程序指定导入，分组之间空一行。
* 模块名称要短，使用小写，并避免使用特殊符号， 比如点和问号。
* 尽量保持模块名简单，以无需分开单词最佳（不推荐在两个单词之间使用下划线）。
* **每个导入应该独占一行。**
```
import os
import numpy
import sys

from types import StringType, ListType 
```

### Main
主功能应该放在一个main()函数中。
在Python中，pydoc以及单元测试要求模块必须是可导入的。代码应该在执行主程序前总是检查 `if __name__ == '__main__'，` 这样当模块被导入时主程序就不会被执行。
```
def main():
      ...

if __name__ == '__main__':
    main()
```

## 模块管理
### sys.modules
sys.modules 是一个 将模块名称（module_name）映射到已加载的模块（modules） 的字典。可用来强制重新加载modules。Python一启动，它将被加载在内存中。
当我们导入新modules，sys.modules将自动记录下该module；当第二次再导入该module时，Python将直接到字典中查找，加快运行速度。

它是个字典，故拥有字典的一切方法，如sys.modules.keys()、sys.modules.values()、sys.modules[‘os’]。但请不要轻易替换字典、或从字典中删除某元素，将可能导致Python运行失败。
```
import sys
print(sys.modules)#打印，查看该字典具体内容。
```
