# CSS
# 什么是响应式布局 
就是页面的设计与开发根据用户的设备环境(系统平台、屏幕尺寸、屏幕定向等)进行相应的响应和调整<br>
<br>
<br>


# JavaScript
# 什么是事件代理（委托）
事件代理就是利用事件冒泡，比如ul下有很多li，我们可以给ul绑定一个click事件，然后通过事件对象的target属性来判断具体点击的是哪个li


# 数组常用方法
1. push()：向数组的末尾添加一个或多个元素，并返回新的长度
2. pop()：删除数组的最后一个元素，并返回该元素
3. shift()：删除数组的第一个元素，并返回该元素
4. unshift()：向数组的开头添加一个或多个元素，并返回新的长度
5. splice()：删除元素，并向数组添加新元素
6. slice()：返回数组的一部分
7. concat()：连接两个或多个数组
8. join()：把数组的所有元素放入一个字符串
9. reverse()：颠倒数组中元素的顺序
10. sort()：对数组的元素进行排序
11. indexOf()：返回数组中某个元素的索引



# ES6新特性？
let、const、模板字符串、扩展运算符、解构赋值、箭头函数、Promise、async await、数组新方法（find、findindex、includes)、引入module模块化概念（import和export）、proxy

# Promsie?
简单说就是一个容器，里面保存着某个未来才会结束的事件（通常是一个异步操作）的结果。
是一种异步编程的解决方案，可以解决地狱回调的问题

# async await？
Generator函数的语法糖


# 箭头函数和普通函数的区别?
1. 箭头函数不能当做构造函数
2. 箭头函数中this 的指向会指向离他最近的那个作用域
3. 写法更简单，

# 什么是闭包，有什么用
闭包就是能够读取其他函数内部变量的函数。闭包的特点：
1. 函数嵌套函数 
2. 内部函数可以引用外层的参数和变量 
3. 参数和变量不会被垃圾回收机制回收
   
优点：是可以保护和保存变量，能够实现封装和缓存等<br>
缺点：是消耗内存、使用不当会内存溢出。

# 防抖和节流
防抖：n秒内只执行一次，如果在这n秒内又被触发，则重新计时。<br>
```
function debounce(fn, wait) {
  let timeout = null;
  return function() {
    if(timeout !== null) clearTimeout(timeout);
    timeout = setTimeout(fn, wait);
  }
}
```
节流:规定一个单位时间，在这个单位时间内，只能有一次触发事件的回调函数执行。
```
function throttle(fn, wait) {
  let prev = Date.now();
  return function() {
    let now = Date.now();
    if(now - prev >= wait) {
      fn();
      prev = Date.now();
    }
  }
}
```

# 如何实现图片懒加载
1. 将真实地址放到自定义属性中
2. 监听滚动事件，判断图片是否进入可视区域
3. 如果进入可视区域，则将自定义属性中的真实地址赋值给src属性


# 什么是原型链
每个对象都有一个原型对象，而原型对象又有自己的原型，层层向上直到一个对象的原型为null。null没有原型，是原型链的最顶端。

# 什么是作用域链
主要是用来做变量查找的，我们访问一个数据的时候它会沿着这个作用域链一直往上面找，采用的是就近原则，这样就会形成一个作用域链。他可以保证对变量和函数的访问是有序的

# 获取原型的方法
1. Object.getPrototypeOf()
2. __proto__
3. constructor.prototype

# 深拷贝和浅拷贝
浅拷贝：只复制指向某个对象的指针，而不复制对象本身，新旧对象共享一块内存。<br>
` Object.assign()、Array.slice()、Array.concat()、...扩展运算符`<br>
深拷贝：复制并创建一个一模一样的对象，不共享内存，修改新对象，旧对象保持不变。
` JSON.parse(JSON.stringify())`

# 什么是JS事件循环
1. JavaScript处理异步操作的机制，异步操作都是放到事件循环队列里面，等待主执行栈来执行的，等主线程中任务全部完成后，再回来把异步队列中任务放到主程序中运行，这样反复的循环
2. 同步任务>微任务>宏任务

# 微任务和宏任务
微任务：Promise<br>
宏任务：定时器、事件绑定、ajax、回调函数

# 事件冒泡和事件捕获
事件冒泡：事件开始时由最具体的元素接收，然后逐级向上传播到较为不具体的节点。<br>
`阻止事件冒泡：event.stopPropagation()`<br> 
事件捕获：事件开始时由最不具体的元素接收，然后逐级向下传播到较为具体的节点。

# 事件委托
将事件绑定到目标元素的父元素上，利用冒泡机制触发该事件。这样可以优化性能

# null和undefined的区别
null：表示一个空对象，typeof null === 'object'<br>
undefined：表示一个未定义的值，typeof undefined === 'undefined'

# 检测数据类型的方式
1. typeof
2. instanceof
3. Object.prototype.toString.call()
4. constructor

# 使用new创建对象的过程是什么样的？
1. 创建一个新对象，将this指向这个新对象
2. 设置原型链，把新对象的__proto__指向构造函数的prototype属性
3. 执行构造函数中的代码并返回新对象

# 前端性能优化有哪些方式
1. 减少http请求
2. 代码压缩
3. 使用CDN加速
4. 使用缓存
5. 减少DOM操作
6. 使用懒加载
7. 防抖和节流
   
# 搜索引擎优化
1. 语义化标签
2. 设置img标签的alt属性
3. 页面层级嵌套不要太深
4. meta网页描述突出中心思想，不要超过160字
5. 所有的js、css采用外联方式，图片采用css精灵，减少请求次数。

# Get和Post的区别
1. post更安全
2. post发送的数据更大且数据类型更多
3. get请求会被浏览器缓存，post不会
4. post比get慢
5. get是从服务器上获取数据，post是向服务器传送数据

# vue2和vue3的区别
1. 数据双向绑定原理不同<br>
vue2采用的是Object.defineProperty()，vue3采用的是ES6原生的Proxy实现监听
2. 更快、diff算法不同
3. vue2只能有一个根节点，vue3可以有多个根节点
4. 体积更小，支持typeScript语法
5. 生命周期函数不同
6. 父子传参不同

# vue2的双向绑定原理
采用数据劫持结合发布者-订阅者模式的方式，通过Object.defineProperty()来劫持各个属性的setter和getter，在数据变动时发布消息给订阅者，触发相应的监听回调

# vue2组件间传参的方式
1. props 父传子
2. $emit 子传父
3. vuex
4. eventBus事件总线、\$parent和\$children
5. localStorage、sessionStorage 使用缓存传参
6. $refs

# vue3组件间传参的方式
1. props 父传子
2. emits 子传父
3. expose/ref 父传子
4. v-model 子传父
5. provide/inject 祖先传后代
6. 总线bus/vuex/pinia
7. 插槽

# vue路由传参的方式
1. query 传参用的是path 路径中显示参数
2. params 传参用的是name，路径中不显示参数

# v-for和v-if为什么不能一起使用
v-for的优先级比v-if高，所以会先执行v-for，然后再执行v-if，这样会导致性能问题<br>
解决方案：可以在外层包一个template标签，然后在template标签上使用v-if

# v-if和v-show的区别
v-if条件为真是会进行真正的dom渲染，而v-show是通过display来控制元素的显示和隐藏

# vue数据更新试图没更新的原因及解决方法
1. this.$set(obj,'属性','数值')
2. this.$forceUpdate()强制更新视图

# keep-alive的作用
缓存组件，组件切换时不会重新渲染，保留组件的状态
生命周期钩子：activated（激活）、deactivated(失活)

# nextTick的作用
在下次 DOM 更新循环结束之后执行延迟回调。在修改数据之后立即使用这个方法，获取更新后的 DOM。

# vue插槽
1. 默认插槽 
2. 具名插槽
3.  作用域插槽

让父组件可以向子组件指定位置插入html结构，也是一种组件间通信的方式

# Vue 项目中 key 的作用
为了在diff算法执行时更快找到对应的节点，更高效的更新虚拟dom

# computed与watch的区别
computed：是计算属性，依赖其他属性值，函数必须用return返回，第一次加载就监听<br>
watch：是监听属性值的变化，然后执行对应的回调，第一次加载不监听，`immediate：true`方法可以让第一次就监听

# 什么是虚拟dom
虚拟dom是利用js对象来表示一个dom树结构，然后经过一系列操作将这个对象映射在真实DOM树上。

# 为什么要用虚拟dom
无需手动操作dom，利用dom diff算法避免没必要的dom操作，从而提高性能

# 虚拟dom的原理
首先用 JS 对象模拟真实 DOM 树，虚拟DOM可以经过diff算法找出两个对象的最小差异,通过patch将两个虚拟 DOM 对象的差异应用到真正的 DOM 树。

# diff算法
diff算法就是进行虚拟节点对比，并返回一个patch对象，用来存储两个节点不同的地方，最后用patch记录的消息去局部更新Dom。

# vuex是什么
全局状态管理库，用来管理组件之间共享的数据<br>
数据传递流程：
1. 调用 dispatch 来触发 actions 里面的方法。
2. actions 里面的每个方法中都会 有一个 commit 方法，当方法执行时会通过 commit 来触发 mutations 里面的方法进行数据的修改。
3. mutations 里面 的每个函数都会有一个 state 参数，这样就可以在 mutations 里面进行 state 的 数据修改
4. 当数据修改完毕后，会传导给页面,页面也会发生改变

# vueRouter中hash模式和history模式的区别

hash模式：url中带有#号，兼容低版本浏览器<br>
history模式：url中不带#号，不兼容低版本浏览器<br>
原理不同
hash: 通过监听hashchange事件，改变页面的url
history: 通过pushState或者replaceState事件，改变页面的url

# vue和react的区别
### 相同点
react和vue大体上是相同的，比如都使用虚拟DOM高效的更新视图，都提倡组件化，都实现了数据驱动视图，都使用diff算法，也都对diff算法进行了优化，都有状态管理等等
### 不同点
1. vue是响应式的数据双向绑定系统，而react是单向数据流，没有双向绑定。
2. vue的语法较为简单，适用于小型项目创建，而react更适用于Web端和原生App的开发，侧重于大型应用。
3. React和Vue.js之间最大的区别在于模板的实现方式。react推荐把模板和逻辑写在一起，而vue推荐把模板和逻辑分离。

# cookie localstroge  sessionstroge的区别
1. cookie：一般浏览器生成，存储在本地，大小4kb，有过期时间
2. localstroge：存储在本地，大小5M，永久存储，
3. sessionstroge：存储在本地，大小5M，关闭浏览器就会清除，
   
# MVC、MVP和MVVM的区别
MVC：Model-View-Controller，模型-视图-控制器， <br>他确实做到了Model和View的分层，但是缺点也很明显，数据流会很混乱，不好维护

MVP：Model-View-Presenter，模型-视图-展示器，<br> 他解决了两者的耦合问题，但是缺点就是各种交互操作都在Presenter层，太臃肿了，难以维护

MVVM：Model-View-ViewModel，模型-视图-视图模型， <br>一种用于构建用户界面的软件架构模式，他不仅解决了耦合问题，还减少了大量代码和DOM操作，就比如我们在以前的模式上修改代码，我们需要做很多DOM操作来映射，但是现在我们有数据响应式，我们不需要关心怎么映射到视图，只需要修改数据就可以了，数据改变之后我们有虚拟DOM，有diff算法高效判断最小差异，在减少操作的同时还可以优化性能，代码维护起来也很简单

# vue的mixins
就是混合嘛，他可以复用组件内的方法，但是他有一个缺陷就是他的优先级会比较高一点，会造成命名冲突，我们在Vue3中用Composition API11里的hook就没有这个问题 

# v-model 的原理
v-model是双向绑定的语法糖，通过`v-bind`动态绑定一个value，然后通过`@input`方法动态获取input输入的值，然后重新赋值

# 组件中为什么data是一个函数
因为组件是可以复用的，如果data是一个对象，那么所有的组件都会共享这个对象，这样就会造成数据污染，所以我们需要用函数来返回一个新的对象，这样每个组件都会有自己的数据

# 简单介绍下webpack
webpack 是一种模块打包工具，可以将各类型的资源，例如 img、CSS、JS 等，转译成一个静态文件，减少了页面的请求次数，提高了页面的加载速度。



# Http
# 从浏览器地址栏输入 url 到请求返回发生了什么
1. DNS解析：将域名解析成ip地址
2. TCP连接：三次握手
3. 发起http请求
4. 服务器处理请求并返回http报文
5. 浏览器解析渲染页面
6. 断开连接：四次挥手

# http中的缓存
### 缓存过程
1. 浏览器发送http请求，浏览器首先判断本地是否有缓存，如果没有缓存则发送请求，如果有缓存，则判断是否过期，如果没有过期则直接从本地缓存中读取，如果过期则发送请求。

## 强缓存：
浏览器直接从本地缓存中读取，不会发请求
## 协商缓存：
浏览器会发请求，服务器会返回304状态码，表示资源未发生改变，可以继续使用缓存
## 缓存过程：
强缓存优先级高于协商缓存

# tcp三次握手
1. 客户端发送SYN报文到服务器，
2. 服务器接收到SYN报文，回复一个SYN+ACK报文，
3. 客户端接收到SYN+ACK报文，回复一个ACK报文，三次握手建立完成

# tcp四次握手
1. 客户端发送FIN报文到服务器，
2. 服务器接收到FIN报文，回复一个ACK报文，
3. 服务器也发送FIN报文到客户端，
4. 客户端接收到FIN报文，回复一个ACK报文作为应答，四次握手建立完成，连接关闭

# HTTP状态码
1xx：信息提示<br>
2xx：成功<br>
3xx：重定向<br>
4xx：客户端错误<br>
```
400：请求语法错误
401：未授权
403：服务器禁止访问
404：服务器没有请求资源
408：请求超时
```
5xx：服务器错误

# HTTP 与 HTTPS 区别
1. http明文传输  信息都是未加密，https是加密传输
2. http的端口是80，https的端口是443
3. http 页面响应速度比 https快,因为http三次握手交换3个包，而https加上ssl握手需要9个包，需要12个包，
4. https需要申请证书，http不需要

# websocket是什么
websocket是HTML5的一种新协议，允许服务器像客户端传递信息，实现浏览器和客户端双工通信。

# CSS
# 标准盒模型和ie盒模型的区别
标准盒模型：width = width + padding + border<br>
ie盒模型：width = width

# 如何实现响应式布局
1. 媒体查询
2. rem布局
3. vw、vh布局

# css选择器的优先级
!important > 行内样式>ID选择器 > 类选择器 > 标签选择器 > 继承 > 浏览器默认属性

# 长度单位px、em、rem、vh、vw的区别是什么
1. px：像素，绝对单位，不受任何因素影响
2. em：相对单位，相对于父元素的字体大小
3. rem：相对单位，相对于根`html`元素的字体大小
4. vh：视窗高度的百分比
5. vw：视窗宽度的百分比

# 如何让一个元素水平居中
1. 行内元素：text-align: center
2. 块级元素：margin: 0 auto
3. flex布局：justify-content: center
4. 绝对定位：left: 50%; transform: translateX(-50%)

# 如何让一个元素垂直居中
1. 行高：line-height: height
2. 假表格：display:table-cell; vertical-align: middle
3. 绝对定位：top: 50%; transform: translateY(-50%)
4. 弹性盒子布局：align-items: center
5. 子相父绝：父position: relative，子position: absolute，top: 50%

# 如何让元素垂直居中
1. flex布局：justify-content: center; align-items: center
2. 绝对定位：left: 50%; top: 50%; transform: translate(-50%,-50%)
3. 表格布局：display: table-cell; vertical-align: middle
4. grid布局：align-items: center; justify-content: center
5. absolute+margin: auto

# 如何清除浮动
1. 父元素添加overflow: hidden
2. 设置高度
3. 最后新增一个元素添加clear: both
4. 父元素添加伪元素after


# HTML
# HTML5语义化标签有哪些，有什么作用
1. header：头部
2. nav：导航
3. section：区域
4. article：文章
5. aside：侧边栏
6. footer：底部
7. main：主要内容
![语义化标签](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/7dcc9b4510214a0ca9bcc5eb1d87fb33~tplv-k3u1fbpfcp-zoom-in-crop-mark:1512:0:0:0.awebp '语义化标签')

# 什么是Doctype
文档类型声明，用来告诉浏览器使用哪种HTML或者XHTML规范来解析文档

# 伪类和伪元素的区别
伪类：用来描述元素的特殊状态，比如:hover、:active、:first-child<br>
伪元素：用来创建一些不在文档树中的元素，可以正常定义css，但无法使用JavaScript获取比如::before、::after
伪类用一个冒号`:`表示，伪元素用两个冒号`::`表示

# axios和ajax的区别
1. axios是基于promise的http库，ajax是对原生xhr的封装
2. axios可以拦截请求和响应，ajax不能
3. axios可以转换请求和响应数据，ajax不能
4. axios可以取消请求，ajax不能

# fetch
ES6新增api，使用了ES6中的promise对象。Fetch是基于promise设计的。fetch不是ajax的进一步封装，而是原生js，没有使用XMLHttpRequest对象。fetch是一个低层次的API，你可以把它考虑成原生的XHR，所以使用起来并不是那么舒服，需要进行封装。

# 如何中断promise
1. 在 then/catch 的最后一行返回一个永远 pending 的 promise 
2. 给网络请求设置超时时间，一但超时就中断

# 如何实现多个标签页之间的通信
1. localStorage 缺点： 存储大小限制只能监听非己页面跨域不共享
2. websocket缺点： 需要服务端配合增加服务器压力上手不易
3. cookie 缺点：有存储大小限制轮询消耗性能发请求会携带cookie

# call和apply和bind的区别
1. 都可以修改this指向
2. call和bind是列表传参，apply是数组传参
3. bind是返回一个新的函数，不会立即执行
4. call和apply是立即执行，bind是返回一个修改this指向的新函数

# css导入有哪几种方式？
1. 行内样式 
2. 内部样式
3. 外部样式
4. 导入样式
   
# BFC是什么
## Block Formatting Context：块级格式化上下文
BFC是一个完全独立的空间（布局环境），让空间里的子元素不会影响到外面的布局。
## 触发条件
1. overflow: hidden
2. position: absolute
3. position: fixed
4. display: inline-block
5. display: table-cell
6. display: flex

# 数组去重的方法
## 1. Set 
```
let newArr=[...new Set(arr)]
let newArr=[Array.from(new Set(arr))]
```
## 2. indexOf和includes
```JavaScript
const resultArr = [];
for (let i = 0; i < originalArray.length; i++) {
    if (resultArr.indexOf(originalArray[i]) < 0) {
        resultArr.push(originalArray[i]);
    }
}
console.log(resultArr);
indexOf没有处理NaN，includes处理了NaN
```
## 3.双重for循环去重
```JavaScript
let unique = (arr)=>{
    for(var i=0; i<arr.length; i++){
        for(var j=i+1; j<arr.length; j++){
            if(arr[i] === arr[j]){                
                arr.splice(j,1);
                j--;
            }
        }
    }
    return arr;
}
```

# 如何画一个三角形
```css
.triangle {
  width: 0;
  height: 0;
  border: 20px solid transparent;
    border-bottom-color: red;
}
```

# 	回流（重排）和重绘
## 回流
添加删除元素或当页面的元素的位置、尺寸等发生改变时，浏览器会重新计算该元素的几何属性,在将计算的结果绘制出来
## 重绘
当一个元素的样式被改变，浏览器会根据元素的新属性重新绘制，重绘不一定需要重排，重排必然会导致重绘
### 减少回流和重绘
1. 合并样式
2. 使元素脱离文档流（使用浮动( float )、绝对定位( position: absolute )）
3. 先设置display:none，然后设置display:block

# ajax原理
1. 创建XMLHttpRequest对象
2. 调用open方法，设置请求方式和请求地址
3. 调用send方法，发送请求
4. 监听onreadystatechange事件，处理返回的数据
5. 请求完成，处理返回的数据

# 如何理解 HTML 语义化？
1. 易读性
2. 有利于SEO
3. 有利于开发和维护

# vue项目如何部署，为什么部署后会出现刷新出现404
1. 前后端分离开发模式下，前后端是独立布署的，前端只需要将最后的构建物上传至目标服务器的web容器指定的静态目录下即可
2. 解决办法一：路由改为hash模式，<br>
  解决办法二: 后端配置

# 	link标签和@import的区别
1. 使用范围不同：link除了可用于引入css，还可以定义rel属性等，@import只能用于引入css
2. 加载方式不同：link是页面加载时同时加载，@import是页面加载完后加载
3. 操控不同：link可以通过js插入link标签改变样式，@import不行

# 你对webpack的理解
webpack 是一个用于现代JavaScript应用程序的静态模块打包工具
