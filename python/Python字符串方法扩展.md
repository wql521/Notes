# Python字符串方法扩展
### .find()
```
my_str = "都说冰糖葫芦儿酸"
a = my_str.find("糖")
print(a) # 输出内容为 3
```
查找 "糖" 这个小字符串在大字符串中的索引值
### .title()
```
my_str = "AaBbCcDd"
new_my_str = my_str.title()
print(new_my_str) # Aabbccdd
```
将字符串首字母大写
### .upper()和.lower()
```
my_str = "AaBbCcDd"
new_my_str = my_str.upper()
print(new_my_str) # AABBCCDD
```
.upper() 方法表示将字符串全部大写，全部小写是 .lower()
### count() 方法
语法格式如下所示：
```
my_str.count(sub_str[, start[, end]])
```
返回字符串 my_str 中子串 sub_str 出现的次数，可以指定从开始（start）计算到结束（end）。
```
print('abcaaabbbcccdddd'.count('a'))
```
### endswith()和 startswith()
方法原型如下
```
my_str.endswith(suffix[, start[, end]])
my_str.startswith(prefix[, start[, end]])
```
endswith() 检查字符串 my_str 是否以 suffix（可以是一个元组） 结尾，返回布尔值的 True 和 False。
startswith() 用来判断字符串 my_str 是否是以 prefix 开头。

### find(),rfind()和 index(),rindex()
函数原型如下所示：
```
my_str.find(sub[, start[, end]])
my_str.rfind(sub[, start[, end]])
my_str.index(sub[, start[, end]])
my_str.rindex(sub[, start[, end]])
```
find() 搜索字符串 my_str 中是否包含子串 sub，包含返回 sub 的索引位置，否则返回"-1"。

index() 和 find() 不同点在于当找不到子串时，抛出ValueError错误。

## 替换相关方法

### replace()
`my_str.replace(old, new[, count])`
将字符串中的 old 替换为 new 字符串，如果给定 count，则表示只替换前 count 个 old 子串。

## 分割和合并
### split()、rsplit()和 splitlines()
```
my_str.split(sep=None, maxsplit=-1)
my_str.rsplit(sep=None, maxsplit=-1)
my_str.splitlines([keepends=True])
```
split() 根据 sep 对 my_str 进行分割，maxsplit用于指定分割次数。splitlines() 用来分割换行符。

### join()
```
my_str.join(iterable)
```
将可迭代对象中的元素使用字符 my_str 连接起来。

## 修剪

### strip()、lstrip()和 rstrip()
```
my_str.strip([chars])
my_str.lstrip([chars])
my_str.rstrip([chars])
```
分别是移除左右两边、左边、右边的字符 char。默认移除空白（空格、制表符、换行符）。

## 字符串格式化
### .format()
```
# 多个大括号，format() 方法中需要多个值进行填充
my_str = "小爱同学，今天天气"
answer_str = "今天上午的天气是： {}，下午的天气是：{}".format("晴","多云")
print(answer_str)
```
# 大括号中有占位符
```
my_str = "小爱同学，今天天气"
answer_str = "今天上午的天气是： {shangwu}，下午的天气是：{xiawu}".format(shangwu="晴",xiawu="多云")
print(answer_str)
```

在 Python 中，字符串格式化有三种方式，分别为 % 占位符格式化，format() 方法格式化，以及 f-string
