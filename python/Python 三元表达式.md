# Python三元表达式
## 列表推导式结构
`[表达式 for 迭代变量 in 可迭代对象 [if 条件表达式]]`
例题：
```
old_list=[1,2,3]
new_list=[i*2 for i in old_list]
print(new_list)
```
## 字典推导式结构
`{键:值 for 迭代变量 in 可迭代对象 [if 条件表达式]}`
例题：
```
my_dict = {key: value for key in range(3) for value in range(2)}
print(my_dict)
```
得到的结果如下：
`{0: 1, 1: 1, 2: 1}`
## 元祖推导式结构
```
my_tuple = (i for i in range(10))
print(my_tuple)
```
运行之后产生的结果：
`<generator object <genexpr> at 0x0000000001DE45E8>`
使用元组推导式生成的结果并不是一个元组，而是一个生成器对象，需要特别注意下，这种写法在有的地方会把它叫做生成器语法，不叫做元组推导式。
## 集合推导式结构
```
my_set = {value for value in 'HelloWorld'}
print(my_set)
```
因为集合是无序且不重复的，所以会自动去掉重复的元素，并且每次运行显示的顺序不一样，使用的时候很容易晕掉。
## 三元表达式结构：
`表达式（1）为 True 执行语句 if 条件表达式（1） else 表达式（1）为 False 执行语句`
例题：
```
age = 20
cn = "成年" if age >= 18 else "未成年"
print(cn)
```
## 返回多个语句
```
age=20
cn='成年','大于等于18岁' if age>=18 else '未成年'
print(cn)
```
返回的值将以元祖的方式进行显示（'成年'和'大于等于18岁'之间只能用逗号隔开，不能使用分号，分号只会返回第一个值）
