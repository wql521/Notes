# css代码样式

## 一.文本设置

### 字体属性

**字体属性：(font)**

大小 `{font-size: x-large;}`(特大) xx-small;(极小) 一般中文用不到，只要用数值就可以，单位：PX、PD

样式 `{font-style: oblique;}`(偏斜体) `italic;`(斜体) `normal;`(正常)

行高 `{line-height: normal;}`(正常) 单位：PX、PD、EM

粗细 `{font-weight: bold;}`(粗体) `lighter;`(细体) `normal;`(正常)

变体 `{font-variant: small-caps;}`(小型大写字母) `normal;`(正常)

大小写 `{text-transform: capitalize;}`(首字母大写) `uppercase;`(大写) `lowercase;`(小写) `none;`(无)

修饰 `{text-decoration: underline;}`(下划线)` overline;`(上划线)` line-through;`(删除线) `blink;`(闪烁)

常用字体：` (font-family)`

> "Courier New", Courier, monospace, "Times New Roman", Times, serif, Arial, Helvetica, sans-serif, Verdana

### 文字属性

color : #999999; ``/*文字颜色*/``

font-family : 宋体,sans-serif; ``/*文字字体*/``

font-size : 9pt; ``/*文字大小*/``

font-style:itelic; ``/*文字斜体*/``

font-variant:small-caps; ``/*小字体*/``

letter-spacing : 1pt; ``/*字间距离*/``

line-height : 200%; ``/*设置行高*/``

font-weight:bold; ``/*文字粗体*/``

vertical-align:sub; ``/*下标字*/``

vertical-align:super; ``/*上标字*/``

text-decoration:line-through; ``/*加删除线*/``

text-decoration: overline; ``/*加顶线*/``

text-decoration:underline; ``/*加下划线*/``

text-decoration:none; ``/*删除链接下划线*/``

text-transform : capitalize; ``/*首字大写*/``

text-transform : uppercase; ``/*英文大写*/``

text-transform : lowercase; ``/*英文小写*/``

text-align:right; ``/*文字右对齐*/``

text-align:left; ``/*文字左对齐*/``

text-align:center; ``/*文字居中对齐*/``

text-align:justify; ``/*文字分散对齐*/``

vertical-align属性``vertical-align:top; ``/*垂直向上对齐*/

``vertical-align:bottom; ``/*垂直向下对齐*/

 ``vertical-align:middle; ``/*垂直居中对齐*/

 ``vertical-align:text-top; ``/*文字垂直向上对齐*/

``vertical-align:text-bottom; ``/*文字垂直向下对齐*/

### CSS边框空白

``padding-top:10px; ``/*上边框留空白*/

 ``padding-right:10px; ``/*右边框留空白*/

``padding-bottom:10px; ``/*下边框留空白*/

``padding-left:10px;`` /*左边框留空白

### CSS符号属性

```css
list-style-type:none; /*不编号*/
list-style-type:decimal; /*阿拉伯数字*/
list-style-type:lower-roman; /*小写罗马数字*/
list-style-type:upper-roman; /*大写罗马数字*/
list-style-type:lower-alpha; /*小写英文字母*/
list-style-type:upper-alpha; /*大写英文字母*/
list-style-type:disc; /*实心圆形符号*/
list-style-type:circle; /*空心圆形符号*/
list-style-type:square; /*实心方形符号*/
list-style-image:url(/dot.gif); /*图片式符号*/
list-style-position: outside; /*凸排*/
list-style-position:inside; /*缩进*/
```



## 二、超链接设置

```css
text-decoration: 参数
```

主要用途是改变浏览器显示文字链接时的下划线。 

参数取值范围： 

- underline：为文字加下划线 
- overline：为文字加上划线 
- line-through：为文字加删除线 
- blink：使文字闪烁 
- none：不显示上述任何效果

### CSS连接属性

```css
a /*所有超链接*/
a:link /*超链接文字格式*/
a:visited /*浏览过的链接文字格式*/
a:active /*按下链接的格式*/
a:hover /*鼠标转到链接*/
```



## 三、背景

### 1、背景颜色

```css
background-color: 参数
background:transparent; /*透视背景*/
```

### 2、背景图片

```
background-image: url(URL)
```

- URL就是背景图片的存放路径，none表示无。

### 3、背景图片重复

```css
background-repeat: 参数
```

参数取值范围 ：

- no-repeat：不重复平铺背景图片
- repeat-x：使图片只在水平方向上平铺
- repeat-y：使图片只在垂直方向上平铺

如果不指定背景图片重复属性，浏览器默认的是背景图片向水平、垂直两个方向上平铺。

### 4、背景图片固定

背景图片固定控制背景图片是否随网页的滚动而滚动。如果不设置背景图片固定属性，浏览器默认背景图片随网页的滚动而滚动。为了避免过于花哨的背景图片在滚动时转移浏览者的注意力，一般都设为固定

```css
background-attachment: 参数
```

参数取值范围：

- fixed：网页滚动时，背景图片相对于浏览器的窗口而言，固定不动
- scroll：网页滚动时，背景图片相对于浏览器的窗口而言，一起滚动

### 5、指定背景位置

```css
background-position : 90% 90%; /*背景图片x与y轴的位置*/
background-position : top; /*向上对齐*/
background-position : buttom; /*向下对齐*/
background-position : left; /*向左对齐*/
background-position : right; /*向右对齐*/
background-position : center; /*居中对齐*/
```



## 四、区块

### 1、单词间距

```css
word-spacing: 间隔距离
```

### 2、字母间距 

```css
letter-spacing: 字母间距
```

### 3、文本对齐

```css
text-align: 参数
```

参数的取值：

- left：左对齐
- right：右对齐
- center：居中对齐
- justify：相对左右对齐

### 4、垂直对齐

- vertical-align: 参数
- top：顶对齐
- bottom：底对齐
- text-top：相对文本顶对齐
- text-bottom：相对文本底对齐
- baseline：基准线对齐
- middle：中心对齐
- sub：以下标的形式显示
- super：以上标的形式显示

#### 盒子居中

**html代码**

```html
<div class="parent">
	<div class="child">DEMO</div>
</div>
```

**公共css样式**

```css
.parent{
	width:200px;height:300px;
	background:#ddd;
}
	
.child{
	background:#666;
	color:#fff;
}
```

##### 盒子宽高 + 父相子绝 + [margin](https://so.csdn.net/so/search?q=margin&spm=1001.2101.3001.7020) 只适用于子盒子有宽度和高度的时候

父相子绝，子盒子：top：50%，left：50%；然后设置左外边距为自身宽度一半，上外边距为自身高度一半

```css
.parent {
	position: relative;
	width: 800px;
	height: 400px;
	border: 1px solid black;
}
        
.child {
    position: absolute;
    width: 400px;
    height: 200px;
    top: 50%;
    left: 50%;
    margin-top: -100px;
    margin-left: -200px;
    border: 1px solid red;
}
```

##### 父相子绝+margin: auto; 只适用于子盒子有宽度和高度的时候

设置margin自动适应,然后设置定位的上下左右都为0,就如四边均衡受力从而实现盒子的居中;

```css
.parent {
         position:relative;
	}

.child {
		widht: 100px;
		height: 100px;
		position: absolute;
		margin: auto;
		top: 0;
		left: 0;
		right: 0;
		bottom: 0;
      }
```

##### 父相子绝+位移 子盒子有或没有宽高的时候都适用

设置子盒子 top：50%，left：50%，再用CSS3属性transform: translate(-50%, -50%);

```css
.parent{
	position: relative;	
}
	
.child{
	position: absolute;
	left: 50%;	/* 父盒子宽度的50% */
	top: 50%;	/* 父盒子高度的50% */
	transform: translate(-50%,-50%);	/* 子盒子自身宽高的50% */	
}
```

##### 弹性盒子 display:flex 子盒子有或没有宽高的时候都适用

父盒子：display:flex;设置主轴居中，侧轴居中

```css
.parent{
	display: flex;
	justify-content: center;	/* 水平方向 居中*/ 
	align-items: center;		/* 垂直方向 居中*/
	}
```

##### table-cell+inline-block 子盒子有或没有宽度的时候都适用

将父盒子设置为table-cell(能够使元素呈单元格的样式显示)，并设置text-align: center(使内容水平居中)；vertical-align: middle(使内容垂直居中);。子盒子设置为inline-block可以使其内容变为文本格式，也可设置宽高；
```css
.parent{
	display: table-cell;	/*使标签元素以表格单元格的形式呈现*/
	text-align: center;	  /* 水平居中*/
	vertical-align: middle;	/* 垂直居中 */
}
	
.child{
	display: inline-block;	/* 将子盒子设置为行内块级（文本格式）*/
}
```

### 5、文本缩进

```css
text-indent: 缩进距离
```

12px相当于一个文字距离

### 6、空格

```css
white-space: 参数
```

- normal 正常
- pre 保留
- nowrap 不换行

### 7、显示样式 

```css
display: 参数
```

参数取值范围： 

- block：块级元素，在对象前后都换行 
- inline：在对象前后都不换行 
- list-item：在对象前后都换行，增加了项目符号 
- none：无显示

## 五、方框 

- height 高度
- width 宽度
- padding 内边距
- margin 外边距
- float（浮动）：可以让块级元素在一行中排列，例如横向菜单。 
- clear 清除浮动

## 六、边框

### 1、样式

```css
border-style 参数
```

边框样式的参数：

- none：无边框 
- dotted：边框为点线
- dashed：边框为长短线
- solid：边框为实线
- double：边框为双线
- groove /*立体内凸框*/
- ridge /*立体浮雕框*/
- inset /*凹框*/
- outset /*凸框*/

### 2、宽度

```css
border-width:参数
```

### 3、颜色

```css
border-color:参数
border-top-color : #369 /*设置上框线top颜色*/
border-top-width :1px /*设置上框线top宽度*/
border-top-style : solid/*设置上框线top样式*/
/*下左右框线一样*/
```

## 七、列表

```css
list-style-type:列表样式
```

不同浏览器的列表符可能不相同，可能会影响到网页，所以网页中的列表大多都是由背景图片显示。

控制用户界面的样式

## 八、鼠标

```css
cursor:鼠标形状参数
```

CSS鼠标形状参数表： 

鼠标形状：CSS代码

```css
style="cursor:hand" 　　　　　手形style="cursor:crosshair" 　　十字形style="cursor:text" 　　　　　文本形style="cursor:wait" 　　　　　沙漏形style="cursor:move" 　　　　十字箭头形：style="cursor:help" 　　　　　问号形style="cursor:e-resize" 　　　右箭头形style="cursor:n-resize" 　　　上箭头形style="cursor:nw-resize" 　　左上箭头形style="cursor:w-resize" 　　　左箭头形style="cursor:s-resize" 　　　下箭头形 style="cursor:se-resize" 　　右下箭头形 style="cursor:sw-resize" 　　左下箭头形
漏斗 cursor:wait
光标图案(IE6) p {cursor:url("光标文件名.cur"),text;}
```

## 八、边界样式

```css
margin-top:10px; /*上边界*/
margin-right:10px; /*右边界值*/
margin-bottom:10px; /*下边界值*/
margin-left:10px; /*左边界值*/
```

