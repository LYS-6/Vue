1. HelloVuejs
如何开始学习Vue，当然是写一个最简单的demo，直接上代码。此处通过cdn <script src="https://cdn.jsdelivr.net/npm/vue@2.6.10/dist/vue.js"></script>获取vuejs。

vue是声明式编程，区别于jquery的命令式编程。

1.1。命令式编程
原生js实践（命令式编程）

创建div元素，设置id属性
定义一个变量叫消息
将message变量放在div元素中显示
修改message数据
将修改的元素替换到div
1.2。声明式编程
vue写法（声明式）

创建一个div元素，设置id属性
定义一个vue对象，将div挂载在vue对象上
在vue对象内定义变量message，并绑定数据
将message变量放在div元素上显示
修改vue对象中的变量消息，div元素数据自动更改
<！DOCTYPE html >
 < html  lang =“ en ” > 
< head > 
  < meta  charset =“ UTF-8 ” > 
  < meta  name =“ viewport ” content =“ width = device-width，initial-scale = 1.0 ” > 
  < meta  http-equiv =“ X-UA-Compatible ” content =“ ie = edge ” > 
  < 脚本 src =“ https：//cdn.jsdelivr。net/npm/vue@2.6.10/dist/vue.js “> </ 脚本> 
  < 标题> HelloVuejs </ 标题> 
</ 头> 
< 正文> 
  < div  id =“ app ” > 
      < h2 > {{message}} </ h2 > 
      < p > {{name}} </ p > 
  </ div > 
  < 脚本>
    // let变量/ const常量
    //编程范式：声明式编程
    const  app  =  new  Vue （{ 
      el：“ #app” ，//用于挂载要管理的元素
      数据：{ //定义数据
        消息：“ HelloVuejs” ，
        名称：“ zzz” 
      } 
    }} ）
  </ 脚本> 
</ 正文> 
</ html >
在谷歌浏览器中按F12，在开发者模式中控制台控制台，更改vue对象的消息值，页面显示也随之改变。

{{message}}表示将变量信息输出到标签H2中，所有的VUE语法都必须在VUE对象挂载的DIV元素中，如果在DIV元素外使用是不生效的。el:"#app"表示将ID为应用程序的DIV挂载在VUE对象上，data表示变量对象。

2. vue列表的展示（v-for）
开发中常用的大量有数据，需要全部展示或部分展示，在原生JS中需要使用以循环遍历顺序替换div元素，在vue中，使用v-for可以简单遍历生成元素数组。

<！DOCTYPE html >
 < html  lang =“ en ” > 
< head > 
  < meta  charset =“ UTF-8 ” > 
  < meta  name =“ viewport ” content =“ width = device-width，initial-scale = 1.0 ” > 
  < meta  http-equiv =“ X-UA-Compatible ” content =“ ie = edge ” > 
  < 脚本 src =“ https：//cdn.jsdelivr。net/npm/vue@2.6.10/dist/vue.js “> </ 脚本> 
  < title > vue列表展示</ title > 
</ head > 
< body > 
  < div  id =“ app ” > 
      < h2 > {{message}} </ h2 > 
      < ul > 
        < li  v-for = “ （项目，索引）在电影 ” ：键 =“ 索引 ” > {{项}} </ 李> 
      </ ul > 
  </ div> 
  < 脚本> 
    const  app  =  new  Vue （{ 
      el：“ #app” ，//用于挂载要管理的元素
      data：{ //定义数据
        消息：“你好啊” ，
        电影：[ “星际穿越” ，“海王” ，“大话西游” ，“复仇者联盟” ] //定义一个
      副本} 
    } ）
  </ script > 
</ body > 
</ html >
显示结果如图所示：



<li v-for="(item, index) in movies" :key="index">{{item}}</li>项目表示当前遍历的元素，指数表示元素索引，为了给Vue的一个提示，以便它能跟踪每个节点的身份，从而重用和重新排序现有元素，需要你为每项提供一个唯一key属性。建议尽可能在使用v-for时提供key属性，除非遍历输出的DOM内容非常简单，或者是刻意依赖依赖行为以获取性能上的提升。

因为它是Vue识别识别的一个通用机制，key并且同时与v-for特别关联。

不要使用对象或副本之类的非基本类型值作为v-for的key。请使用字符串或数值类型的值。

3. vue案例-计数器
使用vue实现一个小计数器，点击+按钮，计数器+1，使用-按钮计数器-1。

<！DOCTYPE html >
 < html  lang =“ en ” > 
< head > 
  < meta  charset =“ UTF-8 ” > 
  < meta  name =“ viewport ” content =“ width = device-width，initial-scale = 1.0 ” > 
  < meta  http-equiv =“ X-UA-Compatible ” content =“ ie = edge ” > 
  < 脚本 src =“ https：//cdn.jsdelivr。net/npm/vue@2.6.10/dist/vue.js “> </ 脚本> 
  < title > vue计数器</ title > 
</ head > 
< body > 
  < div  id =“ app ” > 
      < h2 >当前计数：{{count}} </ h2 > 
      <！-<按钮v-on：click =“ count-”>-</ button> 
      <button v-on：click =“ count ++”> + </ button>-> 
      < 按钮 v-on：click =“ sub（） ” > - </ 按钮>
      < 按钮 @click =“add（） “ > + </ 按钮> 
  </ div > 
  < 脚本> 
    const  app  =  new  Vue （{ 
      el：” #app“ ，//用于挂载要管理的元素
      data：{ //定义数据
        计数：0 
      } ，
      方法：{ 
        添加：功能（）{ 
          控制台。日志（“添加” ）
          此。计数++ 
        }，
        sub：function （）{ 
          控制台。记录（“ sub” ）
          此。count - 
        } 
      } ，
    } ）
  </ 脚本> 
</ body > 
</ html >
定义vue对象并初始化一个变量count = 0

定义两个方法add和sub，用于对count ++或count--

定义两个按钮对象，给按钮添加上点击事件

在vue对象中使用方法表示方法集合，使用v-on:click的关键字给元素绑定监听单击事件，给按钮分别绑定上点击事件，并绑定触发事件后变量函数add和sub。也可以在其中方法中直接使用表达式。例如：count++和count--。asassas11
