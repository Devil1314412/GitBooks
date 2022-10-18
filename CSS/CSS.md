# CSS

### CSS语法规范

```
CSS规则由两个重要的部分构成：选择器以及一条或多条声明
```

### CSS字体属性

```
font-family 属性定义文本的字体属性
font-size 属性定义文本的字体大小
font-weight 设置文本的字体粗细		nomal(400) | bold(700) | bolder | lighter | number
font-style 设置文本的风格		nomal | italic(斜体)
```

```html
<!-- 
文字复合属性  不能更改属性顺序，属性之间以空格隔开 
必须保留 font-size 和 font-family 属性
-->
body {
	font: font-style font-weight font-size/font-height font-family;
}
body {
	italic 700 12px 'Microsoft yahei'
}
```

### CSS文本属性

```
color 属性定义文本的颜色
text-align 设置元素内文本内容的水平对齐方式
text-decoration 规定添加到文本的修饰  none | underline | overline | line-through(删除线)
text-indent 属性用来指定文本的第一行的缩进		10px/2em
line-height 属性设置行间距
```

### CSS引入方式

```
内部样式表		<style></style>
行内样式表		<div style="color: red; font-size: 12px;">xxx</div>
外部样式表		<link rel="stylesheet" href="css文件路径">
		rel定义当前文档与被链接文档之间的关系， stylesheet表示被链接的文档是一个样式表文件
		href定义所链接外部样式表文件的url，可以是相对路径，也可以是绝对路径
```

### CSS复合选择器

##### 后代选择器（较多）

```
元素1 元素2 {样式声明}
.nav li a {样式声明}	类选择器里li中a标签元素
```

##### 子选择器（较少）

```
元素1>元素2 {样式声明}
div>a {样式声明}	选择 div 里面所有最近一级 a 标签元素
```

##### 并集选择器（较多）

```
元素1，元素2 {样式声明}
div,
p,
.pig .peiqi {样式声明}		选择 div，p 和类选择器  .pig 中 .peiqi 类里面的内容
```

##### 链接伪类选择器（较多）

```html
a:link		选择所有未被访问的链接
a:visited	选择所有已被访问的链接
a:hover		选择鼠标指针位于其上的链接
a:active	选择活动链接（鼠标按下未弹起的链接）
实际开发中按照 LVHA 的顺序进行书写
<!-- 鼠标经过的时候，链接由原来的灰色变成了红色 -->
a {
	color: gray;
}
a:hover {
	color: red;		
}
```

##### focus伪类选择器

```
用于选取获得焦点的表单元素
input: focus {
	bacjground-color: yellow;
}
```

### CSS元素显示模式

##### 块元素

```
<h1>~<h6>|<p>|<div>|<ul>|<ol>|<li>
特点：
 1.独占一行
 2.高度、宽度、外边距以及内边距都可以控制
 3.宽度默认是容器的100%
 4.是一个容器盒子，里面可以放行内元素或者块元素（文字类标签里面不能再放块级元素）
```

##### 行内元素

```
<a>|<strong>|<b>|<em>|<i>|<del>|<s>|<ins>|<u>|<span>
特点：
 1.相邻行内元素在一行上，一行可以显示多个
 2.高、宽直接设置是无效的
 3.默认宽度就是它本身内容的宽度
 4.行内元素只能容纳文本或其他行内元素
 <a>里面可以放块级元素，但是给<a>转换一下块级模块最安全
```

##### 行内块元素

```
<img>|<input>|<td>
特点：
 1.和相邻行内元素在一行上，但它们之间会有空白缝隙，一行可以显示多个
 2.默认宽度是它本身内容的宽度
 3.高度、行高、外边距以及内边距都可以控制
```

##### 元素显示模块转换

```
转换为块元素：display: block;
转换为行内元素：display: inline;
转换为行内块元素：display: inline-block;
```

### CSS的背景

##### 背景颜色

```
background-color: transparent(透明)|color(颜色值)
```

##### 背景图片

```
background-image: none|url
```

##### 背景平铺

```
background-repeat: repeat(平铺)|no-repeat(不平铺)|repeat-x(横向平铺)|repeat-y（纵向平铺）
```

##### 背景图片位置（重要）

```
background-position: x y;
参数值：
 length 百分数|由浮点数字和单位标识符组成的长度值（x y有顺序）
 position  top|center|bottom|left|center|right 方位名词（x y无顺序）
```

##### 背景图像固定（背景附着）

```
background-attachment: scroll(随对象内容滚动)|fixed(固定)
```

##### 背景复合写法(没有特定书写顺序)

```
background: 背景颜色  背景图片地址  背景平铺  背景图像滚动  背景图片位置
background: transparent url("../static/img_src/猫猫.jpg") no-repeat fixed top;
```

##### 背景色半透明

```
background: rgba(0, 0, 0, 0.3);
```

### CSS三大特性

```
层叠性  继承性  优先级
```

##### 选择器权重

```
继承<元素选择器<类选择器<id选择器<行内样式style=""<!important
继承的权重： 0, 0, 0, 0
元素选择器： 0, 0, 0, 1
类选择器是： 0, 0, 1, 0
id选择器是： 0, 1, 0, 0
行内样式style: 1, 0, 0, 0
!important: 无穷大
```

### 盒子模型

```
Box Model组成：
border边框
content内容（盒子里面的内容）
padding内边距（内容与盒子边框的距离）
margin外边距（盒子与盒子之间的距离）
```

##### 边框border

```
border: border-width(边框的粗细，单位px)|border-style(边框样式)|border-color|
border-style: dotted(点线)|dashed(虚线)|solid(实线)
none(无边框)|hidden(隐藏边框)|double(双线)
```

###### 边框复合写法

```
border: 1px solid red;(没有顺序)
```

###### 边框分开写法

```
border-top: 1px solid red;
```

##### 单元格边框

```
border-collapse: collapse;(相邻边框合并在一起)
```

##### 内外边距

```
padding: 5px(四边)	padding: 5px 10px(上下，左右)	padding: 5px 10px 20px(上，左右，下)
padding: 5px 10px 15px 20px(上，右，下，左)
margin 写法与 padding 一致
```

### 圆角边框（重点）

```
border-radius: length;(数值或百分比都可以)
后跟两个 length，则设置的是两个对角
后跟四个 length，则设置的是顺时针四个角
分开写：border-top-left-radius\border-top-right-radius\border-bottom-right-radius\border-bottom-left-radius
```

### 盒子阴影（重点）

```
box-shadow: h-shadow v-shadow blur spread color inset;
盒子阴影属性：水平阴影位置|垂直阴影位置|模糊距离|阴影尺寸|阴影颜色|外部阴影（outset）或内部阴影（inset）
```

### 文字阴影（了解）

```
text-shadow: h-shadow v-shadow blur color;
文字阴影属性：水平阴影位置|垂直阴影位置|模糊距离|阴影颜色
```

### CSS浮动（难点）

#### 1.标准流（普通流/文档流）

```
(1)块级元素会独占一行，从上向下顺序排列
(2)行内元素会按照顺序，从左到右顺序排列，碰到父元素边缘则自动换行
```

#### 2.浮动

```
选择器{float: 属性值;}
属性值: none | left | right
```

##### 浮动特性（重难点）

```
1.浮动元素会脱离标准（脱标），浮动的盒子不再保留原先的位置
2.如果多个盒子都设置了浮动，浮动的元素会一行内显示并且元素顶部对齐，盒子之间没有空隙
3.浮动的元素会具有行内块元素的特性，如果盒子没有设置宽度，默认宽度和父级一样，但添加浮动后，它的宽度根据内容多少来决定
4.浮动和标准流的父盒子搭配
5.一个元素浮动了，理论上其余的兄弟元素也要浮动
```

##### 清除浮动

###### clear闭合浮动

```
选择器{clear: 属性值;}
属性值： left | right | both(最常用)
```

###### 给父级添加overflow属性

```
将其属性值设置为 hidden | auto | scroll
```

###### 给父元素添加after属性

```html
.clearfix:after {
    content: "";
    display: block;
    height: 0;
    clear: both;
    visibility: hidden;
}
.clearfix {
    *zoom: 1;
}
```

###### 给父元素添加双伪元素清除浮动

```html
.clearfix:before,.clearfix:after {
    content: "";
    display: table;
}
.clearfix:after {
    clear:both;
}
.clearfix {
    *zoom: 1;
}
```

#### 3.定位=定位模式+边偏移

```
position: static | relative | absolute | fixed
		   静态定位 | 相对定位 | 绝对定位 | 固定定位
边偏移属性: top | bottom | left | right
示例： 
选择器 {position: relative;
		top: 80px;
		left: 20px;
		}
```

###### 相对定位relative

```
移动位置的时候参照点是自己原来的位置，不脱标，继续保留原来的位置
```

###### 绝对定位absolute

```
绝对定位是元素在移动位置的时候，相对于它祖先元素来说的
如果没有祖先元素或者祖先元素没有定位，则以浏览器为准；如果祖先元素有定位（相对、绝对、固定定位），则以最近一级的有定位祖先元素为参考点移动位置，且脱标，不再占有原来的位置
```

###### 固定定位fixed

```
固定定位是元素固定于浏览器可视区的位置（主要场景：可以在浏览器页面滚动时元素的位置不会改变），且固定定位不占有原先的位置
固定在版型的右侧：
1.让固定定位的盒子 left: 50% 走到浏览器可视区的一半位置
2.让固定定位的盒子 margin-left: 版型宽度的一半距离 
```

##### 定位叠放次序z-index

```
选择器 {z-index: 1;}
数值可以是正整数、负整数或0，默认是auto，数值越大，盒子越靠上；如果属性值相同，则后来者居上；只有定位的盒子才有 z-index 属性
```

##### 定位的拓展

###### 绝对定位的盒子居中

```
加了绝对定位的盒子不能通过 margin: 0 auto 水平居中，但是可以通过以下计算方法实现水平和垂直居中
（1）left: 50%;	让盒子的左侧移动到父级元素的水平中心位置
（2）margin-left: -100px;	   让盒子向左移动自身宽度的一半
```

###### 定位特殊特性

```
绝对定位和固定定位也和浮动类似
（1）行内元素添加绝对或者固定定位，可以直接设置高度和宽度
（2）块级元素添加绝对或者固定定位，如果不给宽度或者高度，默认大小是内容的大小
```

###### 脱标的盒子不会触发外边距塌陷

```
浮动元素、绝对定位（固定定位）元素都不会触发外边距合并的问题
```

###### 绝对定位（固定定位）会完全压住盒子

```
浮动元素只会压住它下面标准流的盒子，但是不会压住下面标准流盒子里面的文字（图片）
绝对定位或固定定位会压住下面标准流所有的内容
浮动产生的目的最初就是为了做文字环绕结果的，文字会围绕浮动元素
```

### 元素的显示与隐藏

##### display  显示隐藏

```
display: none;		隐藏对象
display: block;		除了转换为块级元素之外，同时还有显示元素的意思
diaplay隐藏元素后，不再占有原来的位置
```

##### visibility  显示隐藏

```
visibility: inherit | visible | hidden | collapse
inhreit: 继承上一个父对象的可见性
visible: 对象可视
hidden: 对象隐藏
collapse: 主要用来隐藏表格的行或列，隐藏的行或列能够被其它内容使用
visibility 隐藏元素后，元素继续占有原来的位置
```

##### overflow  溢出显示隐藏

```
overflow: visible | auto | hidden | scroll
visible: 不剪切内容也不添加滚动条
hidden: 不显示超出对象尺寸的内容
scroll: 不管内容是否超出，总显示滚动条
auto: 超出自动显示滚动条，不超出不显示滚动条
如果是有定位的盒子，慎用 overflow: hidden 因为它会隐藏多余的部分
```

### CSS三角

```html
```

