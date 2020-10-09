# Vue
##  引入vue.js
### 官网
> https://cn.vuejs.org/
### 开发者版本
```
 <!-- 开发环境版本，包含了有帮助的命令行警告 -->
<script src="https://cdn.jsdelivr.net/npm/vue/dist/vue.js"></script>
```

### 生产环境版本
```
<!-- 生产环境版本，优化了尺寸和速度 -->
<script src="https://cdn.jsdelivr.net/npm/vue"></script>
```

### 语法
```     
            var app = new Vue({
              el: '#app',
              data: {
                message: 'Hello Vue!'
              }
            })
```
#### el挂载点
> el 内部可以任意使用{{ }} 
> 任意CSS选择器都可以，建议id选择器
> 不要把vue挂在到html和body
> 建议挂载到div

#### data
> 数据写在data中
> 支持复杂数据

#### Vue指令
##### v-text
> 替换标签中的内容
> 一般使用差值表达式

##### v-html
> 设置标签的innerHTML指令
> 可以解析html结构

##### v-on
> 为元素绑定事件，事件名不需要on
> v-on:click = "doit" 或 @click
> methods:{doit:function(){}}

***
##### v-show
> 根据表达式的真假，切换元素的显示和隐藏
> v-show = "isShow";
> isShow:false | isShow:true

##### v-if 
> 和v-show类似，操作dom元素，而show是修改display属性

##### v-bind
> 设置元素的属性 
```
	<img v-bind:src="imgSrc">		
	or
	<img :src="imgSrc">

```

##### v-for
> 根据数据生成列表结构
> v-for = "item in arr"
> arr:[1,2,3,4,5]
> (item,index) in arr 
> item是遍历的值，index是索引值

##### v-on补充
> 传递自定义参数，事件修饰符
> @keyup如果要特定某一个案件，js里需要事件对象
> 在Vue中直接 @keyup.enter表示回车
> @click="fun("abc",111)"

##### v-model
> 获取和设置表单元素的值（双向数据绑定）
> v-model:"msg" 




* * *

#### 网络请求库 axios
##### axios

######  首先导入axios
```
	<script src="https://unpkg.com/axios/dist/axios.min.js"></script>
```

###### get
> axios.get(地址?查询字符串key=value&key2=value2).then(function(response){},function(err){})

###### post 
> axios.post(地址,{key:value,key2:value2}).then(function(response){},function(err){})

##### axios + Vue
> 注意axios回调函数中this是改变了，要使用data，要先保存

##### 天气接口
```
    http://wthrcdn.etouch.cn/weather_mini
```

##### 音乐接口
```
    https://autumnfish.cn/search
```









