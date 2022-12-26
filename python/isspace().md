## isspace()

该函数虽然是为空格而生，但无论语法还是用法上跟其它函数依然是一样的，并且也是用于判断字符串组成的，下面来看下具体用法：
* 用途：isspace用于判断一个字符串中，是否只包含空格，如果是返回True否则返回False
* 语法：isspace()
* 用法：xxx.isspace()
```
mystr = 'helloworld'
print(mystr.isspace())
#输出结果
False

mystr = 'hello world'
print(mystr.isspace())
#输出结果
False

mystr = ''
print(mystr.isspace())
#输出结果
False

mystr = ' '
print(mystr.isspace())
#输出结果
True

mystr = '      '
print(mystr.isspace())
#输出结果
True
```