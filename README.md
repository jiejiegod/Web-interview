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
1. JavaScript 是一门单线程语言，异步操作都是放到事件循环队列里面，等待主执行栈来执行的，等主线程中任务全部完成后，再回来把异步队列中任务放到主程序中运行，这样反复的循环
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

# 组件间传参的方式
1. props 父传子
2. $emit 子传父
3. vuex
4. eventBus事件总线、\$parent和\$children
5. localStorage、sessionStorage 使用缓存传参
6. $refs

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

# cookie localstroge  sessionstroge的区别
1. cookie：存储在客户端，大小4kb，有过期时间
2. localstroge：存储在本地，大小5M，永久存储，
3. sessionstroge：存储在本地，大小5M，关闭浏览器就会清除，
   
# MVC、MVP和MVVM的区别
MVC：Model-View-Controller，模型-视图-控制器， <br>他确实做到了Model和View的分层，但是缺点也很明显，数据流会很混乱，不好维护

MVP：Model-View-Presenter，模型-视图-展示器，<br> 他解决了两者的耦合问题，但是缺点就是各种交互操作都在Presenter层，太臃肿了，难以维护

MVVM：Model-View-ViewModel，模型-视图-视图模型， <br>他不仅解决了耦合问题，还减少了大量代码和DOM操作，就比如我们在以前的模式上修改代码，我们需要做很多DOM操作来映射，但是现在我们有数据响应式，我们不需要关心怎么映射到视图，只需要修改数据就可以了，数据改变之后我们有虚拟DOM，有diff算法高效判断最小差异，在减少操作的同时还可以优化性能，代码维护起来也很简单

