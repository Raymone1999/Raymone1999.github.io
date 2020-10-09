# CSS
## Cascading Style Sheets层叠样式表
### CSS使用的三个方式 demo12
 1.可以将CSS样式编写到元素的style属性当中
* 内联样式：
     >将样式直接写到style属性中，这种样式称为内联样式
     >内联样式只对当前元素中的内容起作用	
     >内联样式不方便复用
     >内联样式属于结构和表现耦合，不方便后期维护，不推荐使用
 2. 可将CSS样式编写到head标签中的style标签里
    > ```<style type="text/css">```
    >>type="text/css"默认 为了兼容一些老浏览器

    >可以同时为这些元素一起设置样式，这样使得样式进一步复用
    >将样式表编写到style标签中，也可以使表现和结构进一步分离（推荐）
    
3. 可以将CSS样式写在外部CSS文件中
   >这样外部CSS应用到当前页面
   >完全使得结构和表现分离，可以使得样式表在不同页面上使用
   >最大限度的使样式表进行复用，利用link标签引入，可以利用浏览器缓存，加快用户访问速度
   >开发中最推荐
     
   
```
<link rel="stylesheet" type="text/css" href="style.css">
   rel和type属性都是默认值
```
  
***
### CSS基本语法
>style标签里全都是CSS的代码 不能使用html的（包括注释）
    >>CSS注释：
```
/* 注释 */
```
#### CSS的语法
##### 选择器 声明块

>选择器:
>>通过选择器可以选中页面中的元素
>>并且将声明块中的样式应用到选择器对应的元素上

>声明块：
>>声明块紧跟着选择器后面，使用一对{}括起来
>>实际上就是一组一组名值对结构
>>在一个声明块中可以写多个声明，多个声明用;隔开

```
P{
    color:red;
    font-size:50px;
}
```

* * *
### 常见选择器demo13

#### 元素选择器
>作用：通过元素选择器选择所有指定元素
>语法：标签名{}
```

		p{
			color: red;
		}
        
		h1{
			color: green;
		}
```

* * *
#### id选择器
>通过元素id值选择
>语法：#id属性值{}
```
   <p id="p1">锄禾日当午</p>
   
   #p1{
			color: green;
			font-size: 100px;
		}
```
* * *
#### class类选择器
>通过元素class属性选择
>语法：.class属性值{}
>可以同时为一个元素设置多个class，空格隔开
```
<p class="p2 p3">锄禾日当午</p>

.p2{
			color: blue;
			font-size: 50px;
		}
```

* * *
#### 选择器分组
>为id为p1，class为p2，还有h1同时设置
>通过选择器分组可以同时选中多个选择器对应元素
>语法：选择器1，选择器2，选择器n{}
       
```
#p1,.p2,h1{
			background-color: yellow;
		}
```

* * *
#### 通配选择器
>选择页面中所有元素
>语法：*{};


* * *
#### 交集选择器（复合选择器）
>作用：可以选中同时满足多个选择器的元素
>语法：选择器1选择器2选择器n{}
```
span.p2{
			background: purple;
		}
```

* * *
#### 后代元素选择器
>作用：选中指定元素的指定后代元素
>语法：祖先元素 后代元素{}
```
div span{

}
```
#### 子元素选择器
>作用：只选中子元素
>语法：父元素>子元素
>IE6及以下不支持
* * *

#### 伪类选择器demo14
>伪类专门表示元素一种特殊状态
>比如：访问过的链接，获取焦点的文档

>链接：
>>a:link正常链接
>>a:visited访问过的(只能定义字体颜色)
>>a:hover鼠标滑过(可以给除了a绑定)
>>a:active正在点击(可以给除了a绑定)

*浏览器通过历史记录判定是否访问过*

>其他：
>>focus 获取焦点后 :focus
>>selection 选中 ::selection

```
<input type="text" />
input:focus{
			background: yellow;
		}
```
```
p::selection{
			background-color: red; 
		}
```

* * *
#### 伪元素选择器 demo15
>使用伪元素来表示元素中特殊的位置
>:first-letter第一个字
>:first-line第一行
>:before元素最前部分 一般结合content样式一起使用（不可选中）
>:after元素最后部分 同上


* * *
#### 属性选择器 demo16
***title属性：任何标签，鼠标移上显示***
>可以根据属性或属性值来选择

>语法：
1.有属性title的
```
p[title]{
			background-color: yellow; 
		}
```
2.title属性值为hello
```
p[title="hello"]{
			background-color: green;
		}
```
3.title属性值以ab开头
```
p[title^="ab"]{
			background-color: blue;
		}
```
4.title属性值以c结尾
```
p[title$="c"]{
			background-color: orange;
		}
```
5.title属性值包含z的
```
p[title*="z"]{
			background-color: purple;
		}
```

* * *
#### 子元素选择器 demo17
>p:firstchild 既是p元素又是第一个子元素
>>body>p:firstchild指定了body的子元素
>
>p:lastchild 同上 最后一个
>
>p:nth-child(3) 第三个 even表示偶数 odd表示奇数

>p:first-of-type 所有p元素第一个
>p:last-of-type
>p:nth-of-type


* * *
#### 兄弟元素选择器
* 为span后的p元素设置
>span+p 选中紧挨着的后一个

* span后面所有p元素
>span~p


* * *
#### 否定伪类
>语法 :not（选择器）
* 为所有p元素设置除了class值为hello的
>p:not(.hello)


* * *
#### 样式的继承
>祖先元素上的样式会被后代元素继承
>利用继承，将一些基本的设置给祖先元素  
>但不是所有都会被继承 比如background相关
>

* * *

#### 选择器的优先级
>当使用不同选择器选中同一个元素时，并且相同样式
>这时产生冲突，由选择器的优先级（权重）决定

>优先级:

| 名称 | 优先级 |
| --- | --- |
| 内联样式 | 1000 |
| id选择器 | 100 |
| 类和伪类 | 10 |
| 元素选择器 | 1 |
| 通配选择器 | 0 |
| 继承 | 无优先级 |

>当选择器包含多种选择器 相加比较
>优先级一样用靠后的
>可以在样式最后添加！important 获得最高优先级 避免使用


* * *
#### 伪类的顺序
* link
* visited
* hover
* active

>优先级一样
>hover必须写在active前面
>link visited 必须在hover和active前面
>

* * *

### 字体样式
#### 字体属性
>color 颜色
>font-size 字体大小（px） 设置的是看不见的框的大小
>font-family 字体 可以同时指定多个字体，使用逗号分开，浏览器优先使用前面的字体，如果没有用下一个
>浏览器使用的字体默认是计算机中的字体（客户机）


* * *
#### 字体分类
>在网页中字体分5类
>>serif 衬线字体
>>sans-serif 非衬线字体
>>monospace 等宽字体
>>cursive 草书字体
>>fantasy 虚幻字体

>浏览器会自动选择一种使用

#### font-style
>normal 默认
>italic 斜体
>oblique 倾斜
* 大部分浏览器都不会对倾斜和斜体做区分，一般用italic

#### font-weight
>normal默认
>bold加粗显示
>*100-900 9个值* 不一定有那么多字体

#### font-variant
>normal
>small-caps 文本小型大写字母

#### font
>提供一个font设置所有样式
>font: italic small-caps bold 60px "微软雅黑"
>斜体加粗小大字母 无顺序要求 可不写
>大小 字体必写 倒数一二
>这样写 **性能比较好**


* * *
### 行间距
* 设置行高来设置间距
* 行间距=行高-字体大小
#### 行高 line-height
>line-height:40px;
>line-height:百分数或数值 (相对于字体大小)
>线与线之间的距离 
>文字默认在行高中垂直居中

* * *
#### font 30px/50px
>字体中设置行高
>如果先line-height再font，会用默认值覆盖之前设置的行高
* * *

### 文本修饰
#### text-transform
>none 默认
>capitalize 单词首字母大写 空格识别单词
>uppercase 全大写
>lowercase 全小写

#### text-decoration
>none 默认
>underline 下划线
>overline 上划线
>line-through 删除线

* 超链接a默认值为underline 


#### letter-spacing
>可以指定字符间距
>letter-spacing:10px;

#### word-spacing
>可以指定单词间距
>实际是设置词与词之间空格大小。中文没什么意义。
>word-spacing:10px;

#### text-align
>文本对齐方式
>left 默认值，靠左对齐
>right 靠右
>center 居中
>justify 两端对齐 -通过调节文本空格大小

#### text-indent
>用于设置首行缩进大小
>text-indent:20px
>text-indent:2em 	两个字体大小


* * *
### 盒子模型（框）
*** 内容区（content）内边距（padding）边框（border）外边距（margin）***
* 盒子大小=内容区+边框+内边距

#### 内容区（content)
>height 
>weight
>内容区大小，而不是整个盒子的大小
***
#### 边框（border）
>border-width:10px; 宽度
>border-color:red; 颜色
>border-style:solid;样式
>缺一不可 大部分浏览器width color有默认值 style默认值none

>分别设计四边宽度
>>border-width:10px 20px 30px 40px;
>>上 右 下 左 顺时针方向
>>如果指定三个值： 上 左右 下
>>如果指定两个值： 上下 左右 
**这个规则适用于其他**
>设计一边：border-top-width,border-bottom-width,border-left-width,border-right-width

##### 边框样式border-style
>none 默认
>solid 实线
>dotted 点状虚线
>dashed 虚线
>double 双线

##### 边框简写属性
1. 指定四个边
>border:10px solid red;
>没有顺序要求

2. 分别设置
>border-xxx:10px solid red;

3. 去掉某边
>border-xxx:none;
***

#### 内边距（padding）
>内边距指盒子内容区与盒子边框之间的距离
>padding-xxx设置四个方向内边距
>内边距会影响课件框的大小，背景会延伸到内边距

##### 内边距简写属性
>padding:100px;	
>padding:100px 200px;
>padding:100px 200px 300px;
>padding:100px 200px 300px 400px;
***

#### 外边距（margin）
* 外边距指当前盒子与其他盒子的距离
* 影响盒子的位置，不影响大小
* 可以理解为最小值
* 可以为负值，反方向移动	

>margin-xxx:100px;
>设置上和左，改变自身位置
>设置下和右，改变其他盒子位置	

>margin还可以设置为auto，水平方向自动
>如果只指定左或者右，则设置为最大
>如果同时设置为auto，这两侧设置为相同的值，就可以使子元素在父元素中水平居中	

##### 外边距简写属性
>margin:10px;
>margin:10px 20px;
>margin:10px 20px 30px;
>margin:10px 20px 30px 40px;


* * *

##### 垂直相连外边距
>在**垂直**方向上，**相邻**兄弟元素设置外边距会取最大值而不是求和
>如果父子元素垂直外边距相邻，子元素设置的上边距会传递给父元素
* 解决方法
1.
>可以放个东西隔开（border，padding）

2. 
>父元素设置内边距来实现子元素的外边距

***

#### 浏览器默认样式
* 浏览器在页面没有样式时，为了更好地显示效果，设置默认样式
* 这些默认样式，正常情况下不需要使用
* 往往需要把默认的margin和padding去掉

```
	*{
		margin:0;
		padding:0;
	}
```

***

#### 内联元素的盒子
* 内联元素不能设置width和height
* 可以设置内边距 但垂直内边距不会影响布局
* 可以设置边框，垂直边框不会影响布局
* 可以设置外边距，水平方向外边距不重叠（求和。不支持垂直外边距。

* * *
### display和visibility属性
#### display
>可以将内联元素设置成块元素
>属性display可选值：
>>inline：设为内联元素
>>block：设置为块元素
>>inline-block:设置为行内块元素 既有行内元素的特点又有行内元素的特点
>>>即可以设置宽高，又不会独占一行
>>none:隐藏元素，不显示，不占位置

#### visibility
>属性visibility可选值：
>>visible:可见
>>hidden:隐藏

* display:none和visibility:hidden区别
*display:none:隐藏元素，不显示，不占位置*
*visibility:hidden隐藏元素，不显示，占位置*

***
### overflow
* 子元素理论最大等于父元素内容区大小
* 如果超出的部分称为溢出的内容，父元素默认溢出显示
* 通过overflow可以设置父元素如何处理溢出内容

>可选值：
>>visible 默认溢出
>>hidden 溢出内容修剪，不被现实
>>scroll 滚动条（不溢出双方向滚动条也在）
>>auto 会根据需求自动添加滚动条
***

### 文档流
* 文档流处在网页最底层，它表示一个页面中的位置
* 创建的元素默认在文档流中

#### 元素在文档流中的特点
1. 块元素
>独占一行，自上向下排列
>默认宽度是父元素的100%
>默认高度是被内容（子元素）撑开
2. 内联元素
>只占本身大小，自左向右排列，一行放不下自动换到下一行
>宽度高度默认被内容撑开


* * *

### 浮动
* 希望div横着排
* 使用float属性使元素浮动，脱离文档流
>float可选值：
>>none,默认 在文档流中排列
>>left 元素脱离文档流向页面左侧浮动
>>right 元素脱离文档流向页面右侧浮动


* 当设置浮动（float非none），元素立即脱离文档流，下面的元素立即向上移动，尽量向左上或者右上漂浮，直到遇到父元素边框或其他浮动元素

* 如果浮动元素上是一个没有浮动的块元素，不会超过块元素
* 浮动元素不会超过它兄弟元素，最多并排

* 浮动元素不会盖过文字，通过浮动可以设置文字环绕图片的效果
* 块元素脱离文档流后，高度和宽度都被内容撑开
* 内联元素脱离文档流会变成块元素


* * *
### 简单布局 demo18
***
### 脱离文档流的问题

#### 高度塌陷
> 在文档流中，父元素默认被子元素撑开
>子元素多高，父元素就多高

>但当为子元素设置浮动以后，子元素会完全脱离文档流，此时将会导致子元素无法撑起父元素的高度，导致父元素高度塌陷。
>导致页面布局混乱，开发中一定要避免

#### 解决高度塌陷 demo19
1. 可以但不推荐的方案：父元素固定高度

2. 
>根据W3C标准，在页面中元素有一个隐含属性 Block Formatting Context 简称BFC
>BFC默认关闭
>>BFC开启：
>>1. 父元素的垂直外边距不会和子元素重叠
>>2. 开启BFC的元素，不会被浮动元素所覆盖
>>3. 开启BFC的父元素可以包含浮动的子元素
* 如何开启元素BFC：
	* 设置元素浮动： --不好，会导致宽度丢失。导致下面元素上移	
	* 设置元素绝对定位	 --同上
	* 设置元素为inline-block --也会导致宽度丢失，不推荐
	* **将元素的BFC设为非visible的值 overflow:hidden; --副作用最小**

*IE6及以下不支持BFC*



* * *
#### 导航条练习 demo20

* * *
#### 清除其他元素浮动的影响
>clear可以清除其他浮动元素对当前元素的影响
>>可选值：
>>none 默认值，不清楚
>>left 清除左侧元素浮动的影响
>>right 清除右侧元素浮动的影响
>>both 清除两侧元素浮动的影响（对他影响最大的)

* 清除浮动后，回到浮动之前的位置

#### 解决高度塌陷 （二） demo21
>直接在高度塌陷的父元素最后添加一个空白div 设置clear清除浮动。基本没有副作用
>虽然可以解决问题但是会添加多余的结构，问题不大，W3C也推荐的方式
>html添加

#### 解决高度塌陷 （三） demo22
>用CSS在最后添加
>可以通过after伪类，向父元素最后添加一个空白块元素，然后对其清除浮动
>IE6不支持after
>最推荐使用的一种方式
***
#### 练习 demo23
***

### 相对定位
#### 定位
* 定位指的是把元素摆放到页面任意位置
>通过position属性来设置元素的定位
>>position可选值：
>>static 默认值，没有开启定位
>>relative 开启元素相对定位
>>absolute 开启元素的绝对定位
>>fixed 开启元素固定定位（绝对的一种）

*只要非static就叫开启定位*
>当开启定位，可以通过设置left，right，top，bottom设置元素偏移量

##### position:relative 相对定位demo24
1. 开启相对定位不设置偏移量时，无任何变化
2. 相对定位是相对于元素在文档流中，相对于原来位置移动
3. 相对定位的元素不会脱离文档流
4. 相对定位元素会提升一个层级
5. 通常偏移量只需要使用两个

##### position:absolute 绝对定位demo24
1. 开启绝对定位，脱离文档流
2. 不设置偏移量，位置无变化
3. 相对于离他最近的开启了祖先元素进行定位的
4. 如果所有祖先元素都没有开启，则相对于浏览器窗口进行定位
5. 一般开启子元素的绝对定位都要开启父元素的相对定位
6. 绝对定位会使元素提升1个层级
7. 绝对定位会改变元素性质：内联元素变成块元素，块元素宽度和高度默认被内容撑开。

##### position:fixed 固定定位
1. 脱离文档流
2. 一种绝对定位，大部分特点一样
3. 不同的是固定定位永远相对于浏览器窗口
4. 不随着滚动条滚动，固定在某个位置（小广告 弹窗 回到顶部）
5. IE6不支持

*** 

### 元素层级
* 如果元素层级一样，下面盖住上面的（结构）

#### z-index
>可以用z-index设置元素层级
>层数越高，优先显示 
>z-index大的在上
>没有开启定位的不能使用z-index
>父元素的层级再高也不会盖住子元素

#### 设置元素透明背景 opacity
>opacity属性可以设置元素透明
>取值0到1
>0完全透明 1不透明
>opacity 在IE8及以下的浏览器不支持（filter:alpha(opacity=50)）

***

### 背景
#### 背景颜色
>background-color
#### 背景图片
>background-image 设置背景图片
>background-image:url(#);

>如果背景图大于元素大小，默认只显示左上角
>如果背景图小于元素大小，则默认背景平铺以充满元素

>背景颜色和背景图片可以同时设置，背景颜色作为背景图片的底色
>一般都会同时指定

#### 背景图片重复  background-repeat
>设置背景图片重复方式
>>可选值：
>>repeat 默认值，双方向重复
>>no-repeat 不重复
>>repeat-x 水平重复
>>repeat-y 垂直重复

#### 背景图片位置 background-position
>设置背景图像开始位置
1. 可选值1：
>top right left bottom center 中两个值来设置
>如果只给一个值，第二个值默认是center
>但只能设置九个位置，不灵活

2. 可选值2:
>水平偏移量 垂直偏移量:100px 0px;
>可正可负

#### 背景图像固定或滚动 background-attachment
>设置背景图像是否随着页面一起滚动

>>可选值：
>>scroll:默认值，随着窗口滚动
>>fixed: 背景图片固定，不随着页面滚动

*attachment设置为fixed后，定位永远相对于浏览器窗口*
*不随窗口滚动的图片一般设置给body，不给其他元素*

***

### demo25 按钮练习
* 第一切换图片时会有个非常快的闪烁
1. 产生原因
>外部资源加载进网页的，三次请求不是同时发
>浏览器在资源被使用时才加载资源
>当hover active时才会被加载，加载有时间差
2. 解决方法
>三个图放在同一个图上
>图片整合技术（CSS-sprite） 雪碧图

***

### background简写属性
>同时设置所有背景相关样式
```
backgroud:#bfa url(#) no-repeat;
```
>无顺序，数量要求，不设置就是默认值

***
### 表格 ```<table>``` demo26 demo27
> table标签创建一个表格
> ```<tr>```标签标示表格的一行
> ```<td>```标示表格一行中的一个单元格
> ```<th>```表头，就是一个特殊td

>td属性colspan横向合并单元格的数量
>td属性rowspan纵向合并单元格的数量

>table是块元素 

* td边框和table边框默认有个距离用border-spacing设置
* border-collapse: collapse设置表格边框合并
* 如果设置合并，spacing自动失效

***

### 长表格 demo28
> 有时候表格长，需要分为三个部分
> 表头thead 表格主体tbody 表格底部tfoot
>thead永远显示在最上 tfoot永远显示在最下
*如果表格中没有tbody，浏览器会自动添加tbody*
*所以tr不是table的子元素，而是tbody子元素*

***
### 空table
> 使用空table可以阻止父子元素外边距重叠的问题

```
<!-- 解决父子元素外边距重叠 -->
.box:before{
	content:"";
	display:table;	
}
```
#### 经过修改后的clearfix：
**既可以解决高度塌陷，又可以确保父元素和子元素的垂直外边距不会重叠**
```
.clearfix:befor,
.clearfix:after{
	content:"";
	display:table;
	clear:both;
}
```
***

### 表单 demo29
* 表单的作用是将用户信息提交给服务器，比如百度搜索框，注册，登录

#### form标签
> 属性：
>1. action,指向服务器地址

##### 单行文本框 input type="text" 
>input标签 用来创建一个文本框，它的type属性是text
```<input type="text" name="username">```
>会发给服务器：url地址?username=sunwukong；
>属性名=属性值&属性名=属性值&属性名=属性值&属性名=属性值......

##### 提交按钮 input type="submit"
```<input type="submit" name="" value="这是value">```
>提交按钮
>value值是显示的内容

##### 密码 input type="password"
```<input type="password" name="password">```
>密码

##### 单选按钮 input type="radio"
```
		<input type="radio" name="gender" value="male">男
		<input type="radio" name="gender" value="female">女
```
>单选按钮
>通过name属性分组
>需要选择的，但是不需要写入内容的表单项，还必须指定一个value。
>被选中的value值提交给服务器	
>checked="checked" 默认选中某项

##### 多选按钮 input type="checkbox"
```
		<input type="checkbox" name="hobby" value="zq">足球
		<input type="checkbox" name="hobby" value="lq">篮球
		<input type="checkbox" name="hobby" value="ymq">羽毛球
		<input type="checkbox" name="hobby" value="ppq">乒乓球
```
>cheakbox
>checked="checked" 默认选中某项

##### 下拉菜单 select option
```
		 <select name="star">
		 	<option value="fbb">范冰冰</option>
		 	<option value="zbs">赵本山</option>
		 	<option value="lxr">林心如</option>
		 </select>
```
>分组name指定给select value指定给option
>selected="selected" 默认选中某项
>给select添加multiple="mytiple" 可多选
>optgroup实现分组

##### 文本域 多行文本框
		 ```<textarea name="info"></textarea>```	

##### 重置按钮
```		<input type="reset" name="">
```
>表单内容回复默认

##### 按钮
```		<input type="button" value="单纯按钮1" name="">
or
		<button type="button">单纯按钮2</button>
```
>结合js使用

##### 表单提示文字 label标签
```<label for="id"></label>```
>id 文字绑定输入框，点字也可以

##### fieldset 表单分组	
***

#### CSS Hack
>只在某些浏览器执行的代码
>条件Hack只会对IE有效，其他会当成注释

##### 条件Hack
```
 <!--[if IE]>
 	\*只在IE中显示*\
 <![endif]-->
```

```
 <!--[if IE 6]>
 	\*只在IE6中显示*\
 <![endif]-->
```

```
 <!--[if lt IE 9]>
 	\*在IE9以下显示 lt小于 gt大于 lte小于等于 gte大于等于 !除了*\
 <![endif]-->
```

##### 属性Hack
>属性前加
>> _ 下划线：IE6及以下
>> * 星号：IE7及以下

* * *
### 图标字体
1. css和webfonts文件夹引入
2. link all.css
3. i标签class fas或fab




























