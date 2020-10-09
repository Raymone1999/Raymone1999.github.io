# JavaScript
### 三个部分
1. ECMASCRIPT DOM BOM

### 解释型语言	

### script标签
* 所有JS代码需要编写到script标签中
***

### 输出语句

#### alert demo01
> alert("hello world")
>控制浏览器弹出一个警告窗

#### document.write() demo01
>document.write("hello")
>在页面输出一个内容

#### console.log() demo01
>console.log("hl wd")
>向控制台输出一个内容

***

### JS编写位置
1. 编写到标签的onclick属性中，点击时执行js代码
```	<button onclick="alert('讨厌')">点我一下</button>
```
2. 编写到超链接herf属性中
> 虽然可以写在标签属性中，不方便维护，容易耦合
```	<a href="javascript:alert('点')";>超链接</a>
	<a href="javascript:;">超链接</a>
```
3. 可以写到head中script标签里

4. 可以写一个外部js文件，通过script标签引入
>可以在不同页面中同时应用，也可利用浏览器缓存机制，推荐使用。 
```	<script type="text/javascript" src="demo02.js"></script>
```

*script标签一旦用于引入外部文件就不能编写代码了，即使编写也会忽略*

***

### 基本语法
#### 注释
> /* */ 多行注释
> //  单行注释


#### 语法
1. JS中严格区分大小写
2. JS每一条语句以分号结尾
>不写分号，浏览器自动添加，会消耗系统资源，有些时候会加错分号。
3. JS会自动忽略多个换行和空格

#### 字面量和变量
1. 字面量
>比如：1 2 3 4 5 
>特点：不可变的，可以直接使用，但是不会直接使用字面量
2. 变量
>变量可以用来保存字面量，而且可以任意改变

#### 变量
1. 在js中使用var关键字来声明一个变量
> var a;
2. 为变量赋值
> a = 123;
3. 声明并赋值
>var b = 789;

#### 标识符
* 变量名 函数名 属性名

##### 命名规则
1. 标识符可以包含 字母 数字 下划线_ $ 
2. 不能以数字开头
3. 不能是关键字或保留字
4. 标识符一般采用驼峰命名法
>首字母小写，每个单词开头字母大写
5. JS底层用的是Unicode（utf-8） 

#### 数据类型
> 数据类型指字面量的类型
1. String 字符串
2. Number 数字
3. Boolean 布尔值
4. Null 空值
5. Undefined 未定义
6. Object 对象

* 前五个属于基本数据类型 Object属于引用数据类型*

***
***
***

##### 强制类型转换
1. 转化为String

>方法一
>>toString()方法
a.toString()

>>适用于 Number String Boolean

>方法二:
>>调用String()函数
String(a);

>>将被转换的数据作为参数传递给转化函数
>>使用String函数对于Number和Boolean实际上就是调用toString方法
>>但是对于null和undefined 不会调用toString，而是直接转换

2. 转换为Number

>方式一：使用Number()函数

* 转换情况
>纯数字直接转换
>有非数字内容转换为NaN
>空字符串或空格则转换为0
>true变为1 false变为0
>Null转为 0

>方式二：
>>parseInt()把字符串转成整数
>>parseFloat()把字符串转换为浮点数

* 可以将字符串中有效的整数内容取出来，转换成Number
*123px ==>123*
*123px456==>123*
*b123px==>NaN*

3. 转为Boolean
> 调用Boolean()函数
>123 true
>-123 true
>0 false
>NaN false
* 数字除了0和NaN都是true
* 字符串除了空都是true
* null和undefined都会转换成false
* 对象也会转换为true



##### 进制
* a=0x10;	//16 0x开头
* a=070;	//8 0开头
* a=0b10;	//2 0b开头

***


#### 运算符
* 也叫操作符，比如typeof

##### 算数运算符
>+ - * / %
>当对非Number类型运算时，会转成Number
>任何值和NaN运算都是NaN
>任何值和字符串做加法，都转换成加法
>字符串+字符串=拼串

##### 一元运算符
> + - typeof
>非Number转换为Number

##### 自增自减

```
a++;
a--;
++a;
--a;
```

***
##### 逻辑运算符
1. 非
* !a 

> 对非布尔值则会先转换成布尔值

2. 与
* &&

> true && true=true
> true && false=false
> false&& false=false

>如果第一个值为false不会看后面的值

3. 或
* ||

>true||true=true
>true||false=true
>false||false=false

> 可以对符号两侧的值进行运算或
> 第一个值为true不会看第二个

>非布尔值与运算
>>第一个值为true 则返回第二个值
>>第一个值是false这返回第一个值

>非布尔值或运算
>>第一个值为true返回第一个
>>第一个值为false返回第二个

##### 赋值运算符
* =

> 将符号右侧的值赋值给符号左侧变量

##### 关系运算符
>比较两个字符串是=时，比较的是字符串字符编码
>比较字符编码时一位一位比较，对英文排序
>比较两个字符串型的数字时一定要转型

***

#### 编码
>在字符串中使用转义字符输出unicode编码
> "\u2620"

#### 运算符的优先级
> 运算符优先级表


*** 

### 语句

#### if判断
> if(a>10) console.log("a比10大");
> if(){}

> if(){} else{}

> if(){} else if(){} else if(){} else{}

#### prompt();
> 类似于alert 可以弹出一个带输入框的提示框
> 函数返回值是用户输入的内容

#### switch语句
> switch(){
	case 表达式:
	语句...
	break;
	case 表达式:
	语句...
	break;
	case 表达式:
	语句...
	break;
	default:
	语句...
	break;	
}

#### while 语句
> while(条件表达式){
	语句...
}

>do{
	语句...
}while();


#### for循环
>for(初始化表达式;条件表达式;更新表达式){
	语句...
}

> 可以为循环语句创建一个标签 标志当前循环
>使用break label;结束指定循环
>label: for(){break label;}


* * *
#### Object对象
##### 基本数据类型的不足
> 基本数据类型都是单一的值，值与值之间没有任何联系。
> 对象是一种复合的数据类型，在对象中可以保存多个不同数据类型的属性

##### 对象的分类:
1. 内建对象
> 由ES标准中定义的对象，在任何ES都可以使用，
> 比如：Math String...

2. 宿主对象

> 由JS运行环境，目前由浏览器 
> 比如BOM DOM 

3. 自定义对象

> 由开发人员自己创建的


##### 创建对象
```
var obj=new Object();
```
> 使用new调用构造函数

##### 向对象中添加属性
> 语法：对象.属性名=属性值
```
	obj.name="Sunwukong";
```

##### 读取对象中的属性
> 对象.属性名

##### 属性名
> 对象的属性名不强制要求遵守标识符的规范，乱七八遭的都可以
> 如果需要用特殊的属性名
```
	obj["123"]=789;
```
>读取也要使用这种方式


##### 属性值
> JS对象的属性值，可以是任意的数据类型，也可以是一个对象

##### in 运算符
> 通过检查一个对象是否含有某个属性名
> 语法 ”属性名“ in 对象


* * *
##### 对象字面量
> 使用对象字面量，可以在创建对象时直接指定对象中的属性
> 语法：var obj={name:"zhubajie"};

***

### 函数
* 函数是一个对象 
```
	var fun = new Function("console.log("test")");
```

> 可以将封装的代码以字符串形式传递给构造函数（基本不用）
> 函数调用时执行

```
	fun();
```

> 一般使用：函数声明来创建一个函数
> 语法：function 函数名(){语句}


```
	function fun2(){

	}
```

```
	var fun3 = function(){
		console.log("创建匿名函数，并赋值给变量fun3")
	}
```

#### 函数参数
> 可以在函数括号里指定一个或多个形参，形参相当于在函数内部声明对应变量（不赋值）
```
	function sum(a,b){

	}
```

> 调用时不会检查实参类型
> 多余参数不会被赋值
> 少参数则没有传入的变undefined

> return 设置返回值 后面的语句都不会执行
> 默认返回undefined
> 可以返回任意类型的值

#### 立即执行函数
```
	(function(){})();
```
* 最外面加大括号
> 最后加括号立即调用


***

### for...in语句
```
	for(var n in obj){

	}
```
* 对象中有几个属性对象就循环几次
* n是对象中属性名字

***

### this
> 解析器在调用函数每次会向函数内部传递一个隐含的参数this
> 调用方式不同指向，不同对象
1. 函数形式调用 this永远是window
2. 以方法形式调用，this指向方法的对象


*** 

### 工厂方法创建对象
```
	function createpeople(name,age){
		var obj=new Object();
		obj.name=name;
		obj.age=age;
		return obj;
	}

	var obj1=createpeople("zj",20);
```
 
***

### 构造函数
> 工厂函数创建的对象都是Object
> 构造函数就是普通函数，一般首字母大写

```
	function Person(name,age){
		this.name = name;
		this.age = age;
	}

	var per = new Person("zj",20);
```
* 构造对象执行流程
1. 立刻创建一个新对象
2. 将新建对象设置为函数中的this
3. 逐行执行函数中代码
4. 将新建对象返回值返回

* 使用同一个构造函数创建的对象，称为一类对象，也将一个构造函数称为一个类
* 创建的对象称为类的实例

#### instanceof 
* 检查对象是否是一个类的实例
* 对象 instanceof 构造函数
* 任何对象都是Object的后代 instanceof都返回true


#### 构造函数改进
> 在构造函数里写方法，每创建一个对象定义一次方法
> 占用资源，没有必要，可以共享
> 将函数定义到全局作用域中


* * *

### 原型 
* 我们说创建的每一个函数，解析器都会向函数中添加一个属性prototype
* 对应原型对象
* 当普通函数形式调用时，没有任何作用
* 当构造函数调用时，它所创建的对象中都会有一个隐含的属性	
* 指向原型对象，可以通过__proto__来访问该属性

***

*原型对象是一个公共的区域，所有实例都可以访问*
> 可以将对象中公有的属性添加进prototype
> 现在对象中找，再从原型对象中找
> 构造函数时，公用的属性和方法添加到prototype中

***

* 使用in检查对象中有没有属性时，如果原型中有也返回true 
> 所以只检查对象本身时用per.hasOwnProperty("age");

** 原型对象也有原型对象 **
* hasOwnProperty方法在原型的原型里 
* Object对象的原型没有原型，如果Object中已然没有找到，这返回undefined *

### toString()方法
> 当我们直接在页面打印一个对象时，事件是输出的对象的toString()方法的返回值 

***

### 垃圾回收（GC）
* 当一个对象没有任何的变量或属性对它引用，这个对象称为垃圾
* 在JS中有自动垃圾回收机制
* 只需要把不再使用的对象设置为null

*** 
### 内建对象

#### 数组（Array）
* 数组也是一个对象
* 索引 <-> 值

1. 创建数组对象
```
	var arr = new Array();
```

2. 向数组中添加元素
* 语法：
> 数组[索引] = 值;
```
	arr[0]=10;
	arr[1]=33;
```

3. 读取
```
	var a1 = arr[1];
```
4. 数组长度
```
	arr.length;
```
* 大小是最大索引+1

> 修改length
> arr.length = 10;
> 如果修改长度大于原长度，会空出来;反之则会删除


* * *
##### 使用字面量来创建数组
```
	var arr = []; 
```

* 可以在创建时就指定数组中的元素
``` 
	var arr1 = [1,2,3];
	var arr2 = new Array(1,2,3);
```

> 注意:当只传一个值时（new Array（10）） 被当做长度。

##### 数组的四个方法
1. push方法
> 向数组末尾添加一个或多个元素，并返回数组新的长度 
```
	arr.push(1,2,3);
```

2. pop方法
> 删除并返回数组的最后一个元素
```
	arr.pop();
```
3. unshift方法
>向数组开头添加一个或多个元素，并返回新的数组长度 
```
	arr.unshift(1,2,3);
```
4. shift方法
> 删除数组的第一个元素，并将被删除的元素作为返回值返回
```
	arr.shift();
```

##### 遍历数组
1. for循环
```
	for(var i=0;i<arr.length;i++){
		console.log(arr[i]);
	}
```

2. forEach()方法
> 只支持IE8 以上浏览器
>需要一个函数作为参数，回调函数
>数组有几个元素，函数就执行几次，每次执行时，浏览器会将遍历道德元素以实参传递进来
>>传递三个参数
>>第一个参数是数组中的元素值
>>第二个参数是索引值
>>第三个元素是就是正在遍历的数组
```
	arr.forEach(function(value,inder,obj){});
```


##### 数组方法
1. slice()方法
> 可以用来从数组中提取指定元素
> 参数：开始位置索引(包含)，结束位置索引(不包含) （左闭右开）
> 第二个参数可以不写，默认到最后
> 负值是倒数第几的意思
> 将截取到的元素封装到新数组返回

2. splice()方法
> 可以用于删除数组中的指定元素，被删除的元素作为返回值返回
> 参数：开始位置索引，删除的数量。 第三个及以后传递新元素，到开始位置索引前面

##### 数组方法-三
1. concat()
> 连接两个或多个数组并返回一个新数组
```
	newArr = arr1.concat(arr2,arr3);
```

2. join()
> 可以将一个数组转化成一个字符串,使用逗号连接
```
	result=arr.join();
```
> 可以传参数，替换逗号作为连接符

3. reverse()
> 翻转数组，直接修改原数组。

4. sort()
> 可以用来对数组中元素进行排序，影响原数组，默认按照unicode编码（错误如11<2这种）
> 可以自己定义排序规则
> 定义一个回调函数，如果返回值大于0，交换位置；小于或等于都不换
> 升序a-b，降序b-a

***

#### 函数的方法
* call() apply()
> 当函数调用call和apply都会执行函数

> 当在调用call和apply可以将一个对象指定为第一个参数，this指向这个对象
> call方法在对象后传参
> apply方法在对象后以数组形式传参数

***

#### arguments
> 在调用函数时，浏览器每次都会传递两个隐含参数
> 1. this
> 2. arguments
* arguments 封装实参的对象，类数组对象和数组很像
* arguments.callee 对应的函数对象就是当前正在执行的函数

***

#### Date对象
```
	var d = new Date();
```
* 直接使用构造函数，封装为当前代码执行的时间。
* 日期的格式："月份/日/年 时:分:秒"

1. getDate()
> 获取当前对象是几日
2. getDay()
> 获取当前日期对象是周几 0-6 周日-周一
3. getMonth()
> 获取当前时间对象的月份 0-11
4. getTime()
> 获取当前对象的时间戳，距离标准时间1970年1月1日00：00：00到当前的毫秒数

5. Date.now()
> 当前语句时的时间戳

***

#### Math对象
* 不是一个构造函数，而是在里面封装了一些数学函数
1. Math.PI 圆周率 等常量
2. Math.abs() 计算绝对值  
3. Math.ceil() 向上取整
4. Math.floor() 向下取整
5. Math.round() 四舍五入
6. Math.random() 返回一个0-1之间的随机数不包括0和1 
7. Math.max() Math.min() 返回n个数的最大最小值
8. Math.por(x,y) x的y次幂
9. Math.sqrt() 开方运算
 


* * *
#### 包装类
> 包装类可以将基本数据类型的数据转换成对象
1. String()
2. Number()
3. Boolean()

```
	var num = new Number(3);
	//将基本数据类型的3转换成对象
```

* 不会这样使用，如果这样使用会造成一些不可预期的结果
* 浏览器底层自己用的，例如toString()方法。基本数据类型不能存方法，所以浏览器临时转换为对象。

#### 字符串相关方法
1. str.length 字符串长度
2. str[0] ...字符串第几字符
3. charAt() 返回指定位置的字符 和[]类似
4. charCodeAt() 返回指定位置的Unicode编码
5. String.fromCharCode() 可以通过字符编码去获取字符(是String调的)
6. concat() 连接字符串（和数组的类似）
7. indexof() 检索一个字符串是否含有指定内容，并返回第一次出现的索引位置或-1表示没找到，第二个可以参数指定开始查找的位置
8. lastindexof() 从后往前 同上
9. slice() 截取字符串中指定内容 参数1：开始索引 参数2：结束索引 不会影响字符串，而是将截取到内容返回
10. substring() 和 slice基本相同 不同的是，这个方法不能接受负数
11. split() 可以将一个字符串拆分成一个数组 参数是一个字符串，作为分隔符拆分
12. toUpperCase() toLowerCase() 大小写（不影响原字符串）


* * *
### 正则表达式
* 正则表达式用于定义一些字符串规则

#### 创建正则表达式对象
1.
```
	var 变量 = new RegExp("正则表达式" , "匹配模式");
```

2.
```
	var 变量 = /正则表达式 /匹配模式  （不要引号） 
```

#### test()
```
	reg.test(str);
```
#### 匹配模式
1. "i" 忽略大小写
2. "g" 全局匹配，并不是找到第一个停止

#### 正则语法
1. 检查字母或字符串:"a" "ab" ...
2. 检查a或b:  a|b
3. 是否有字母: [a-z]小写 [A-Z]大写 [A-z]任意字母
4. 检查是否有abc 或 adc 或 aec : a[bde]c
5. 除了 :[^ab] [^0-9]



#### 字符串和正则相关方法
1. split()
> 将一个字符串拆分为数组 ，可以用正则表达式拆分
> 默认全局

2. search()
> 可以搜索字符串是否有指定内容

3. match()
> 从字符串中把复合条件的内容提取
> 将匹配到的内容封装到数组，即使只查询到一个

4. replace()
> 替换 第一个参数：被替换内容 第二个参数：新内容(可空)

#### 量词
1. 连续出现3次a： a{3}
2. 连续出现3次ab：(ab){3}
3. 连续出现1-3次a：a{1,3}
4. 连续出现3次以上a：a{3,}
5. 至少一个a ：a+ <===> a{1,}
6. 0个或多个a： a* <===> a{0,}
7. 0个或一个a： a? <===> a{0,1}
8. 以a开头： ^a
9. 以a结尾： a$
10. 以a开头或以a结尾： ^a|a$

#### 元字符
1. 点表示任意字符,找点需要转义
2. \w 任意字母，数字，下划线
3. \W 除了字母数字下划线
4. \d 任意数字
5. \D 除了数字
6. \s 空格
7. \S 除了空格
8. \b 单词边界 独立单词\bapple\b
9. \B 除了单词边界

***
### DOM
* Document Object Model 文档对象模型

#### 节点
* 浏览器已经为我们提供文档节点，是window的属性，代表整个网页
> document

##### getElementById()方法
> 获取元素对象
```
	var btn = document.getElementById("btn");
```

> 修改按钮的文字
```
	btn.innerHTML = "I'm a button";
```

#### 事件
* 用户和浏览器之间的交互行为

##### 处理事件
* 可以在事件对应属性中设置js代码
> 这种写法结构行为耦合，不推荐使用
1. onclick
2. ondblclick
3. onmousemove ...

* 可以为按钮对应事件绑定处理函数的形式来响应事件
1. 获取按钮对象
```
	var btn = document.getElementById("btn");
```

2. 绑定处理函数
```
	//单击响应函数
	btn.onclick = function(){
		alert("111");
	}
```

#### 文档加载
* 如果在script标签写在页面head，在执行代码时页面还没加载，DOM对象也没有加载
* 确保页面加载完成再执行,把js代码写到window.onload里
> window.onload = function(){...}

#### DOM方法
##### 1.通过document对象调用
1. getElementById() 
>	id 一个
2. getElementsByTagName()
>  标签名 一组
3. getElementsByName()
>  name属性 一组

##### innerHTML用来获取内部html代码
> 对于自结束标签没有意义

##### innerText
* 和innerHTML 类似会把标签去除


##### 元素.属性
> class属性不能采取这种方式 要用className

##### 2.通过元素节点调用
> 元素名.getElementsByTagName();

###### 子节点 
1. childNodes属性会获取包括文本节点所有的节点（含空白）

2. children属性可以获取当前元素的所有子元素

3. firstChild属性获取当前节点第一个子节点（含空白）lastChild同

4. firstElementChild属性获当前节点第一个子元素（不支持IE8及以下）

###### 父节点和兄弟节点
1. parentNode 父元素
2. previousSibling 前一个兄弟节点 (可能空白)
3. previousElementSibling 前一个兄弟元素 不包含空白 


* * *
##### DOM查询其他方法
###### 获取body标签
```
	1.
	var body = document.getElementsByTagName("body")[0];
```
* document中有一个属性保存的是body的引用
```
	var body = document.body;
```
1. document.body body标签
2. document.Element html标签
3. document.all 页面里的所有元素

* getElementsByClassName 不支持IE8及以下

4. document.querySelector() IE8支持 
> 需要一个选择器的字符串作为参数，可以根据一个CSS选择器来查询一个元素节点对象
> 总会返回唯一的一个，如果多个只返回第一个

5. document.querySelectorAll("")
> 同querySelector 不同的是将所有符合条件的元素封装到数组返回 
> 即使只有一个，也会返回数组

***

#### DOM增删改
1. document.createElement("name") 创建元素节点
> 需要一个标签名作为参数，将会根据该标签名创建元素节点对象
> 创建的节点作为返回值

2. document.createTextNode()
> 可以用来创建一个文本节点对象
> 需要一个文本内容作为参数

3. appendChild()
> 向父节点中添加子节点
> 父元素.appendChild(子节点);

```
	var li = document.createElement("li");
	var gzText = document.createTextNode("广州");
	li.appendChild(gzText);
```

4. insertBefore()
> 在指定子节点前面插入新子节点
> 父节点调用
> 语法：父节点.insertBefore(新节点，旧节点);

5. replaceChild()
> 可以使用指定子节点替换已有子节点
> 父节点.replaceChild(新节点，旧节点);

6. removeChild()
> 可以删除一个子节点
> 父节点.removeChild(子节点);
> 子节点.parentNode.removeChild(子节点);  常用，不用获取父节点

7. 用innerHTML增加删除元素 
```
	 ul.innerHTML += "<li>shanghai</li>"
```
> 一般结合使用，3中TextNode可以用innerHTML添加


* * *
#### 添加删除记录  
* 在onclick最后return false 不执行a标签默认行为 

#### 使用DOM操作CSS

##### 操作内联样式 
> 通过JS修改元素样式
> 语法：元素.style.样式名 = 样式值;
> 注意：如果CSS样式名中含有 - ，在JS中是不合法的。需要将这种样式名修改成驼峰
> 改的是内联样式，内联样式有较高的优先级，通过JS修改的样式往往会立即显示
> style属性 设置和读取的都是内联样式，无法读取样式表中的样式

##### 读取元素当前样式
1. 语法: 元素.currentStyle.样式名
> 返回现在正在显示的样式
> 只有IE支持

2. 语法:getComputedStyle(元素,伪元素) 
> 第一个参数：要获取样式的元素 第二个参数:传递一个伪元素，一般null
> 返回一个对象，封装了CSS样式
> getComputedStyle(box1,null).width;
> 区别:如果获取的值没有设置，则会返回真实值而不是默认值

3. 自己写一个 通用浏览器的方法
> obj 要获取样式的元素
> name 要获取的样式名
```
	function getStyle(obj , name){
		//正常浏览器
		if(window.getComputedStyle){
			return getComputedStyle(obj,null)[name];
			}else{
		//IE8
			return obj.currentStyle[name];
			}
		
	}
```

##### 其他样式相关属性
1. clientWidth clientHeight
> 返回的是数字，不带px
> 获取元素高度和宽度包括内容、内边距
> 只读 不可写

2. offsetWidth offsetHeight
> 比1多了边框

3. offsetParent
> 会获取离当前元素最近的开启了定位的祖先元素

4. offsetLeft offsetTop
> 当前元素相对与其定位父元素的水平、垂直偏移量

5. scrollHeight scrollWidth 滚动高度、宽度
> 子元素超过父元素大小，开启滚动条的总大小

6. scrollTop scrollLeft
> 可以获取垂直、水平滚动条滚动的距离
*当scrollHeight - scrollTop == clientHeight 说明滚动条滚到底*


* * *
#### 事件对象
> 当时间的响应函数被触发时，浏览器每次都会将一个事件处理对象作为实参传递进响应函数
> 在该对象中封装一切信息，比如鼠标坐标，键盘按键
> IE8及以下不会传事件对象，而是window.event

##### onmousemove
> 鼠标移动后被触发

##### clientX clientY
> 鼠标水平坐标垂直坐标 
> 总是相对于可见窗口的坐标

##### pageX pageY
> 鼠标相对于当前页面的
> 但是在IE8中不支持

##### 滚动条
* chrome认为滚动条是body ?(现在改了？)
* 火狐等认为滚动条是html的

#### 事件冒泡（Bubble）
> 指事件向上传导，当后代元素处罚时，祖先元素相同事件也会触发。
> 在开发中 大部分情况是有用的
> 如果不需要，可以事件对象取消
```
	event.cancelBubble = true;
```
##### 冒泡应用 事件委派
> 只绑定一次，应用多个元素，即使是后添加的元素
> 将事件同一绑定给共同的祖先元素
> event.target 是触发对象

#### 事件绑定
> 用对象.事件 = 函数方式，会覆盖前面的。
> 所以可以addEventListener()
>> 参数：
>> 1. 事件的字符串：不要on
>> 2. 回调函数
>> 3. 是否在捕获阶段触发，一般false
> 可以为一个元素同一事件同时绑定多个函数，会依次执行
> 不支持IE8及以下 IE8（attachEvent）

#### 拖拽
1. 鼠标按下，开始 onmousedown
2. 鼠标移动，跟随移动	onmousemove
3. 鼠标松开，固定	onmouseup

#### 滚轮事件
> onmousewheel鼠标滚轮滚动的事件 火狐不兼容
> event.wheelDelta获取滚轮滚动的方向 向上正 向下负



* * *
#### 键盘事件
1. onkeydown onkeyup 键盘按下松开
> 键盘事件一般绑定给可以获取焦点的对象或document
> 对于onkeydown 按住不松手，会连续触发，连续触发时 第一次和第二次间隔稍长
> 通过event.keycode可以判断哪个案件被按下

> altkey ctrlkey shiftkey按下true 松开false

***

### BOM 浏览器对象模型
* BOM操作浏览器 DOM操作网页

#### BOM对象
1. window
> 代表整个浏览器窗口
2. Navigator
> 代表当前浏览器信息
3. Location
> 浏览器地址栏信息，可以获取地址栏信息，操作浏览器跳转
4. History
> 代表历史记录，由于隐私原因，不能获取具体历史记录，且当次访问有效
5. Screen
> 代表用户屏幕信息

##### navigator
1. appName
> 由于历史原因，Navigator对象中的大部分属性不能帮助我们识别浏览器
2. userAgent
> 一般使用userAgent来判断浏览器信息，字符串包含浏览器信息内容
> 如果userAgent不能判断，可以通过一些浏览器特有的对象来判断

##### history
* 可以操作浏览器向前向后
1. length 当前访问链接数量
2. back 可以回退到上一个，作用和浏览器返回按钮一样
3. forward 往前跳转下一个页面，作用和前进按钮一样
4. go 
>参数：
>> 1向前跳1个
>> 2向前跳2个

##### location
* 直接打印location当前页面完整路径
* 如果直接修改location，会自动跳转，并生成相应的历史记录
* assign() 和直接修改location一样
* reload()重新加载，刷新当前页面 传入true：强制清空缓存刷新
* replace()可以使用新页面替换当前页面，不会生成历史记录

##### window
1. setInterval() 定时调用
> 参数 1.回调函数
> 参数 2.时间间隔，ms
> 返回一个Nunber值，用来作为这个定时器的唯一标示

2. clearInterval()
> 用来关闭定时器，需要一个定时器标识




* * *
#### 切换图片练习
* clearInterval可以接受任意函数，如果是定时器则停止，否则什么都不做

#### 修改移动div练习

#### 延时调用
* setTimeout(function(),100);
>不马上执行，隔一段时间执行，只执行一次
* clearTimeout（）  

#### 类的操作
> 通过style属性修改元素样式，每修改一个样式，浏览器就需要重新渲染一次页面
> 不建议这么用
> 可以修改class属性来间接修改样式
> box.className = "box2"
> 加某些样式 box.className +=" box2";

***
### JSON
> 就是一个特殊格式的字符串，可以被任何语言识别，并且可以转换为任意语言的对象
> 主要用于数据交互
> JavaScript Object Notation
> 属性名必须加引号
> 数组 []
> 对象 {}
> 允许的属性值：字符串 数值 布尔值 null 对象 数组

#### 转化
1. 将JSON字符串转换成JS中的对象
> var o = JSON.parse(json);

2. 将js对象转换为JSON
> var str = JSON.stringify(obj)

*JSON对象在IE7及以下的浏览器不支持*
> 解决：eval()这个函数执行一段字符串形式的的JS代码
> var obj = evel("("+obj+")");
> 执行性能很差，具有安全隐患

> 如果需要兼容，引入一个JS文件























 














































