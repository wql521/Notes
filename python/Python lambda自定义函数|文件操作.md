# Python lambda自定义函数|文件操作
## lambda结构
> lambda [参数列表]:表达式
# 英文语法格式
lambda [arg1[,arg2,arg3....argN]]:expression
语法格式中有一些注意事项：

* lambda 表达式必须使用 lambda 关键字定义；
* lambda 关键字后面，冒号前面是参数列表，参数数量可以从 0 到任意个数。多个参数用逗号分隔，冒号右边是 lambda 表达式的返回值。

## 文件
### os 模块与 os.path 模块

在 Python 中操作文件路径，使用 os 模块，os.path 模块是 os 模块内部的一个子模块，首先导入该模块。

`import os`
### 获取当前 Python 文件的目录

getcwd 方法可以获取当前 Python 文件所在的工作目录，就是当前文件在那个文件夹中，获取到的是绝对地址，例如下述代码。
```
import os
print(os.getcwd())
```
**获取绝对路径 os.path.abspath**

os.path 模块中的 abspath 方法可以返回绝对路径，可以先通过 help 函数，查看该方法使用方式。
```
import os

help(os.path.abspath)
```
注意学习返回结果

> Help on function abspath in module ntpath:

abspath(path)
    Return the absolute version of a path.
abspath 方法需要一个参数 path，即一个路径，基于该路径在返回绝对路径。

例如通过该代码返回 demo4.py 文件的绝对路径
```
import os

ret = os.path.abspath("demo4.py")
print(ret)
```
**获取相对路径 os.path.relpath**
绝对路径返回的是一个从根目录开始的路径值，但是相对路径不一样，该方法既然叫做相对，那需要有一个相对对象，所以该方法的语法格式如下：

os.path.relpath(path,start)
path 就是要获取绝对路径的地址值，描述起来比较绕，一会看代码；
start 相对的对象值。
```
import os

ret = os.path.relpath("D:\\")
print(ret)
```
获取 D:\\ 该目录的相对地址，相对于谁的地址，没写 start 参数就相对于当前工作目录，即 Python 文件所在的目录，你已经知道当前 Python 文件所在的目录是 D:/gun/2。

先认为的推断一下 D:\\ 相对于 D:/gun/2 怎么获取，应该是父级目录的父级目录，那用代码怎么表示，已经学习了父级（上一层文件夹）目录表示方式 ..，所以写作 ..\.. ，整理完逻辑之后，发现跟代码得到的效果一致。

..\..
将 path 参数修改为跟 Python 文件目录一致的值，看一下是不是得到相对路径是一个 .，表示当前目录。
```
import os

ret = os.path.relpath("d:\\gun\\2")
# 或者写成下面这个样子
# ret = os.path.relpath("d:/gun/2")
print(ret)
```
结果输出为 . ，没错是期望值。

### 路径检查方法

检查路径主要是为了检查文件或者文件夹是否存在，或者判断一个路径对应的是一个文件夹还是一个文件。

exists(path) 如果 path 文件或文件夹存在返回 True，否则返回 False；
isabs(path) path 是绝对路径返回 True，否则返回 False；
isdir(path) path 是文件夹返回 True，否则你懂；
isfile(path) path 是文件返回 True。
以上四个方法都在 os.path 模块下，具体代码比较简单，自己尝试一下即可。

### 目录操作

以下几个方法在 os 模块中，执行如下操作建议先通过 os.path.exists 判断目录是否存在。

mkdir(path) 创建目录；
rmdir(path) 删除目录；
chdir(path) 切换当前工作目录到 path；
remove(path) 删除文件，注意如果 path 是一个目录，删除会报错，权限不足，删除目录请使用 rmdir。
以上四个方法实际编码也非常简单，导入模块之后，用就完了，橡皮擦自己就先不浪费篇幅了。

### 获取文件大小

该内容只需要调用 getsize 方法即可。
```
import os
print(os.path.getsize("demo4.py"))
```
注意得到的是字节大小。

### 获取指定目录下面的所有内容

通过 os.listdir 方法可以获取指定目录下的所有内容，包括文件与文件夹。
```
import os
print(os.listdir("."))
```
输出的内容：
```
['demo1.py', 'demo2.py', 'demo3.py', 'demo4.py', 'demo5.py', 'dog_module.py', '__pycache__']
```
可以与文件进行一下比对。

### Python 读取文件

Python 在读写文件的时候首先要做的是打开文件，然后可以一次性读取文件或者一行行的读取，打开文件使用 open 函数。

### 读取文件所有内容

使用 open 函数打开文件之后，可以通过 read 读取文件内容，该方法相当于将文件的内容一次性的读取到了程序的一个字符串中，非常强大。

test.txt 文件内容

梦想橡皮擦
是一个大佬
真的是一个大佬
我自己都信了
读取代码如下：
```
# 文件地址，注意提前在当前目录新建一个 test.txt 文件
file = "test.txt"
# 打开文件
f = open(file, encoding="utf-8")
# 读取文件全部内容
read_str = f.read()
# 关闭文件
f.close()
print(read_str)
```
第一点需要注意的是使用 open 打开文件时，必须在文件使用完毕之后通过 close 关闭文件。
第二点需要注意，上述代码中 file = "test.txt" 该文件名并不是一个完整的路径，这种情况下表示该文件和当前的 Python 文件在一个目录，如果在不同目录，需要用到前文讲到的路径相关知识了。

例如，在上一级目录 ../test.txt。

上述代码如果运行出现编码 BUG，注意修改以下 open 函数部分代码，通过 encoding = “utf-8” 设置文件打开时的编码。

### 打开文件
f = open(file, encoding="utf-8")
逐行读取文件内容

通过循环调用文件对象，可以逐行输出文件内容。
```
# 文件名
file = "test.txt"
# 打开文件
f = open(file, encoding="utf-8")
# 循环逐行读取
for line in f:
	print(line)
# 关闭文件
f.close()
```
在这里逐行读取多了一个换行，原因是在 txt 文件中，每行的末尾默认有一个换行，print 函数输出也会带一个换行，所以出现 2 个回车符，解决办法，可以使用 print 函数的第二个参数。
```
# 文件名
file = "test.txt"
# 打开文件
f = open(file, encoding="utf-8")
# 循环逐行读取
for line in f:
	print(line,end="")
# 关闭文件
f.close()
```
### 逐行读取方法 readlines

使用 readlines 方法可以将数据一次性读取到一个列表中，例如下述代码。
```
# 文件名
file = "test.txt"
# 打开文件
f = open(file, encoding="utf-8")
# 逐行读取
data = f.readlines()
# 关闭文件
f.close()
print(data)
```
输出内容中，可以看到每行读取到的字符串都带一个 \n 换行符。
```
['梦想橡皮擦\n', '是一个大佬\n', '真的是一个大佬\n', '我自己都信了']
with 上下文
```
在 Python 中为了防止忘记打开文件之后，在进行关闭，提供了一个 with 关键词解决该问题，语法格式如下：

with open(待打开文件) as 文件对象:
	文件操作代码块
有了该语法之后，前文的代码可以修改为：
```
file = "test.txt"
# 打开文件
with open(file,encoding="utf-8") as f:
    # 读取文件全部内容
    read_str = f.read()
    print(read_str)
```
读取文件还包含其它的几个方法，可以自行尝试。

### 写入文件

写入文件，泛指写入到本地硬盘上。

在学习写入文件之前，需要先扩展一下 open 函数，该函数目前已经掌握 2 个参数，第一个是操作的文件，第二个是文件的编码 encoding，在补充一个文件打开模式 mode 参数，open 函数中该参数的默认值是 r ，代码写作 open("text.txt",mode="r",encoding="utf-8") 表示以只读的方式打开文件，如果想要向文件中写入内容，需要将 mode 参数设置为 w。关于 mode 参数还有其它值，不要着急，后续会学习到，先记住 2 个即可。

文件写内容的语法格式为：

文件对象.write(待写入内容)
具体案例代码：
```
# 文件地址，注意提前在当前目录新建一个 test.txt 文件
file = "test.txt"
# 打开文件
with open(file, mode="w", encoding="utf-8") as f:
    # 写入文件内容
    f.write("我是即将被写入的内容")
```
注意，待写入的内容需为字符串类型，其它类型写入会报错。该种方式写入内容之后，原内容会被覆盖，如果想要在文件中追加数据，用到的是 mode = a。

###写入多行数据
通过 write 方法可以写入单行数据，如果想要写入多行数据，可以在 with 代码块中，写上多个 write 方法即可。注意 write 方法默认在行尾不添加换行符，如果希望加上换行符，需手动添加。

例如下述代码：
```
file = "test.txt"
# 打开文件
with open(file, mode="w", encoding="utf-8") as f:
    # 写入文件内容
    f.write("我是即将被写入的内容\n")
    f.write("我是即将被写入的内容")
```
### 文件复制

使用该模块中 shutil 对象的 copy 方法可以对文件进行复制操作。

shutil.copy(旧文件,新文件)
书写成真实代码如下：
```
import shutil

shutil.copy("test.txt","aaa.txt")
shutil.copy("test.txt","../aaa.txt") # 不同目录拷贝
```
### 目录复制

copytree 方法语法格式与 copy 一致，只不过该方法是用来复制目录的，如果目录下面有子目录或文件一起复制。
```
import shutil
# 第一个参数是旧目录，第二个参数是新目录
shutil.copytree("../1","a4")
```
执行代码时，需要确定新目录不存在，如果存在会报错。

### 多用的 move 方法

使用 move 方法可以移动文件。

shutil.move(旧文件，新文件)
移动文件一定要确保旧文件存在，移动之后旧文件将移动到新文件位置。

使用 move 方法可以修改文件名，在移动文件的过程中，如果新旧文件名称不一致，可实现移动文件并重命名的效果。

使用 move 方法还可以移动目录，移动目录时会将该目录下的所有文件一起移动。当然如果新旧目录名称不一致，还可以实现移动目录并重命名的效果。

删除有数据的目录

使用 rmtree 可以删除有数据的目录，相当于直接清空该目录下的所有目录和文件，再顺便把该目录也删除了。具体内容自行测试即可。

文件模块扩展知识

### zipFile 模块

通过该模块可以直接对文件进行压缩与解压操作。后续滚雪球中将补充该部分知识。

### 认识编码

open 函数中的 encoding 参数，我们将该参数的值设置为了 utf-8，在很多程序中设置为该值可以解决很多潜在的编码 BUG。

* UTF-8 这几个字母的写法你要记住，大小写都可以；
* UTF-8 中有个 BOM 文件头，这里不细说，如果发现 UTF-8 解决不了编码问题，那就设置为 utf-8-sig 尝试解决。
