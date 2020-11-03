### ECMAScript6
    1. Let、const和var的区别
        1.let,const不可以重复声明，var可以重复声明
        2.let,const不可以变量提升，var可以
        3.常量const,但是他在创建必须有初始值，并且不可以改变
        4.块级作用域
        5.在for循环中，条件的let相当于块级父作用域
        for(let i = 0;i<10;i++){
            // 循环体是子作用月
            let i =hello
        }
    2. 变量解构赋值（数组解构）
        解决的问题： 快速创建变量
        let [a,b,c] = [1,2,3]   数组对数组，值对值
    3. 变量解构赋值（对象解构）
        解决的问题：快速取值
        let { title } = { title:"名字",number:1}  对象对对象，取值拿属性，名字对名字
        <!-- vuex state同步的方法集合 -->
        state:{count:123,age:18},
        mutations:{
            changeCount({ count }) {
                
            }
        }
    4. 模板字符串
        语法：`string${变量}`
    5. 字符串扩展方法
        重复："hello".repeat()
        字符串包含："hello".includes("e")
        开始："hello".startsWith
    6. 函数扩展
        函数的默认值：
        let add = function(a = 0,b) {
            return a+b
        }
        扩展运算符 语法：...
        1. 浅拷贝 对象和数组
        Object.prototype.clone=function(){
            var o= this.constructor===Array? [] : {};
            for(var e in this){
                o[e]= typeof this[e]==="object" ? this[e].clone() : this[e];
            }
            return o;
        };
        2. 展开数组，和对象
        3. 展开字符串
        4. 可以转换伪数组  , 跟 Array.from()
        5. 对象合并
        6. function中...arg, 可以拿到一个数组
        7. 伪数组转换成数组：两种方法：[...arguments]    Array.from()
        8. 展开set 和map 数据结构
    7. 箭头函数
        let Person = function() {
            this.name = "张飞",
            this.age = 18,
            this.obj = {
                name:"关羽",
                // fun: function() {
                //     console.log(this.name)
                // },
                fun: () => {
                    console.log(this.name)
                }
            }
        }
        let p = new Person()
        console.log(p)
        p.obj.fun()
    8. 数组扩展
        arr.includes()  // 数组中是否包含
        arr.fill()  // 数组填充 第一个参数填充的内容，第二个参数填充的起始位置，第三个参数，结束的位置
        arr.findIndex() // 数组查找下标,找到返回索引值，找不到返回-1
        arr.find()      // 数组中符合条件的对象
        every()  // 循环条件都为真时，返回true
        some()   // 循环条件有一个为真时，返回true
        map()    // 映射（具有返回新数组）
        filter() // 过滤出符合条件的对象，返回新数组
    9. 对象的扩展
        对象的简洁语法：
        对象合并 Object.assgin({},obj)
        对象循环：Object.keys()  Object.values()

    10. Class 基本使用和继承
    11. Class 静态方法 静态属性
    12. set 和map数据结构：
        set数据结构，里面存储都是不能重复的值
        size属性，就是set数据结构中的数量
        add()    向set数据结构中添加一个数据
        delete() 在set结构中删掉一个数据
        clear()  全部清空
        has()    判断是否有这个值
        数组去重：
        let arr = [1,2,3,4,2,1,2,3,4,12,3,1,2,31,1]
        let s = [...new Set(arr)]

        map 数据结构
        set()    向map数据中存
        get()    取数据
        add()    向map数据结构中添加一个数据
        delete() 在map结构中删掉一个数据
        clear()  全部清空
        has()    判断是否有这个值
        特点：就是可以以任何数据类型进行存储 key=>value

    13. Promise 对象
        let p = new Promise()
        有两个回调，一个是成功回调resolve  失败reject
    14. async 函数
        异步函数:
        函数的语法：在普通函数前面加上 async 关键字，那么就变成了异步函数，
        异步函数的特点：
        返回值 一直是promise对象
        调用方式跟普通函数一致
        遇到关键字await，会先执行await后面的promise对象，然后再执行下面的语句

    15. Symbol :
        es6推出的独一无二的第7中数据类型，可以通过typeof(),查看他的数据类型，一般情况是用来当对象的属性来用
        let s = Symbol()  // s就是symbol数据类型

### webpack4.0
    1. webpack 介绍
    2. webpack重要性
    3. 打包基本配置
    4. 服务器、热加载配置

### vue基础
    1. MVVM 和 MVC
    2. 核心点：数据驱动和组件开发
    3. 渐进式框架
    4. 虚拟dom
    5. 模板语法
    {{  }}
    6. 指令以及修饰符
        v-if v-show v-for v-html v-model v-bind v-on v-clock
    7. 事件修饰符

### vue 基础进阶
    1. vue 方法 methods
    2. 计算属性 computed 与 监听 watch
        （计算属性的用法）与（监听的基本用法）
    3. class与style绑定
        :class="isShow?'pink':'white'"
        :class="{red:true}"
        :class="[{red:true},{blue:true}]"
    4. Filter 过滤器
    5. directive 自定义指令

### vue 的组件
    1. 组件的划分（全局组件，局部组件）
    全局
        在main.js中 注册全局组件
        import Loading from '@/components/loading'
        Vue.component("Loading",)  // 在脚手架任意一个组件中使用
    局部
        在某个组件中，使用局部组件
        import appHeader from '@/components/header'
        components:{
            appHeader:appHeader
        }
    2. 组件的好处
        组件得复用性，组件得维护性，高效
    3. 组件的封装

    4. 组件通讯
        （父传子，子传父，兄弟传值，props验证） 
    5. 插槽slot
        匿名插槽：
        父组件： 使用子组件
        <appdiv>
            132132
        </appdiv>
        子组件：
        可以通过slot标签拿到上面得132132
        <slot></slot>

        具名插槽：****
        父组件： 使用子组件
        <appdiv slot="title">
            首页
        </appdiv>
        子组件：
        可以通过slot标签拿到上面得132132
        <slot name="title"></slot>

        子组件：
        data() {
            return{
                obj:{name:132,age:456}
            }
        }
        <slot :data=obj></slot>

        父组件：
        <appdiv slot-scope="obj"></appdiv>
        （匿名插槽、具名插槽、作用域插槽）
    6. 动态组件
        (keepalive)
        可以将组件进行缓存
        第一种：
        <keep-alive includes=["header"]>
            <app-header/>
        </keep-alive>

        第二种：
        路由表配置：
        {
            path:"/",
            name:"Home",
            component:Home,
            meta:{
                keepalive:true // 在显示当前路由组件时，我就进行缓存
            }
        }
        <keep-alive>
            <router-view v-if="$route.meta.keepalive"/>
        </keep-alive>
        <router-view v-if="!$route.meta.keepalive"/>

    7. vue 生命周期与单向数据流
        挂载阶段（创建前 beforeCreate、创建后 created、挂载前 beforeMount、挂载后 mounted）

        运行阶段（更新前 beforeUpdate、更新updated）

        销毁阶段 （销毁前 销毁后）
### 脚手架以及路由
    1. 为什么使用vue-cli
    2. vue-cli的安装
    3. vue-cli的目录介绍
    4. vue 单页面应用 路由的使用
    5. history和hash模式的区别
        hash 能兼容到IE8， history 只能兼容到 IE10
        hash:（默认）
            以#定位的方式去进行路由切换，类似锚点，url方式进行传递参数，有体积的限制，json的大小
        histroy: 
            pushState,replaceState 去改变路由状态，histroy 体积上限值要大，还有专门的对象进行存储，如果在服务器上，进行布置测试，不怕前进后退，刷新操作，会出现404，需要进行一些文件的配置

    6. router-link的配置项
       to属性进行跳转 to="/"  tag="div"
    7. 重定向 （redirect）
        路由中配置：
        路由表：
        {
            path:"/",
            name:"Home",
            component:Home,
            redirect:"/city"
        }
        
    8. 嵌套路由 
    9. 命名视图（路由表）
    10. 动态路由传参 
        this.$router.push({
            path:"",
            query:{
                
            }
        })
        this.$router.push({
            name:"",
            params:{}
        })
    11. 监控$route 路由信息对象
        watch:{
            $route(to,from) {
                console.log(to)
            }
        }
    12. 导航动画
        v-leave-enter:  起始路由离开的状态
        v-leave-to:     终止路由离开的状态
        v-leave-active: 加个过度
    13. 钩子函数
        （全局钩子、组件钩子、单个路由钩子）
        beforeEach  全局前置
        afterEach   全局后置

        单个的路由钩子
        beforeEnter: 单个路由钩子

        组件的钩子
        beforeEnterRoute:  组件确认钩子
        beforeUpdateRoute: 组件的路由参数改变时触发
        beforeLeaveRoute:  组件离开之前触发


    14. 编程式导航
        （Router.push、 Router.replace、Router.go）
        
### vuex 
    1. vuex 的使用场景
    2. vuex的核心
        （state、getters、mutations、actions、modules）
    3. vuex的运行机制

### axios 
    1. 安装与使用
    2. 核心方法
        （get请求、post请求、并发请求、创建实例、拦截器）

### UI框架
    1. elementUi
    2. MintUi

### 作业
    作业效果：https://m.douban.com/movie/
    1.配置根路由list,在list路由中，请求热门、top250、即将上映，数据获取，渲染页面
    2.渲染图片，名字，得分多少星
    3.点击某一个数据列表，可以跳转到detail路由，传递过去一个id
    4.在detail路由页面，进行详情数据获取，渲染页面

