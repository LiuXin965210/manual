# Vue Router
##一、基本概念
1. route：一条路由，如登录按钮——>系统主页这是一条路由，密码变更按钮——>密码变更画面这是另一条路由
2. routes：是一组路由（数组），把上面的route的组合起来的结果
3. router：是一个机制，相当于路由的管理者，因为routes只是定义了一组路由，并没有被vue使用，当获取到客户端请求时需要router这个管理者去在routes中找到请求对应的显示内容
##二、使用方式
1. 模块安装：`npm install vue-router`  
2. 如果使用Vue-Cli搭建的项目`vue add router`在router目录下的index.js引入依赖：  
```
import Vue from 'vue'
import VueRouter from 'vue-router'
Vue.use(VueRouter)
```
3. router目录下index.js，创建router，并传入路由映射配置routes
```
const routes = []
const router = new VueRouter({
  mode: 'history',
  base: process.env.BASE_URL,
  routes
})
```
   - hash模式最直观的特点是url上存在#如`localhost:8080/#/xxx`，这个#以后的部分不包含在http请求中，因此对后端没有影响
   - history模式是利用HTML5中history的pushState API实现的，该模式显著特点就是，页面后退或前进后，不会重新执行页面的脚本（初期化方法）。
   - history模式设置的新url可以是当前url同源的任意url，而hash只可修改#后面的部分
   - history模式设置新的url可以与当前url一模一样，这样被记录在浏览器栈中，而hash设置的新值仅与上次url不一样时，才会被记录在浏览器栈中
   - history模式需提供后台配置的支持，如`localhost:8080/app/usermgr`，若后台缺少/app/usermgr的处理将返回404错误。
   - base属性默认值："/"，应用的基本路径，例如整个单页应用服务在/app/，base应该为/app/
4. 在main.js中对vue实例中挂载router
```
new Vue({
  router,
  render: h => h(App)
}).$mount('#app')
```
##四、<router-link>与<router-view>
1. `<router-link to='/home' tag='li' replace active-class="active">`中的属性：
* to：用于指定跳转的路径
* tag：可以指定<router-link>之后渲染成什么组件，默认渲染为\<a>标签
* replace：指定replace属性后，浏览器后退键，无法返回上一页面
* active-class：当<router-link>对应的路由匹配成功后，会自动给当前元素设置一个router-link-acitve的class，该class可手动指定
2. `<router-view/>` 
* 相当于占位符的作用，决定跳转后内容显示的地方
##五、路由的默认配置
通常情况下，我们进入网站首页时，不需要点击标签按钮，直接看到<router-view/>中的内容可进行如下配置
```
const routes = [
   {
      path: '',
      redirect: '/home' //重定向，即最初路径为根路径时，立即重定向到/home路径
   }
]
```
## 动态路由
```
const User = {
    template: '<div>User {{$route.params.id}}</div>'
};

const router = new VueRouter({
    router: [
        {path: '/user/:id', component: User}
    ]
});
```
用于匹配/user/zhangsan、/user/lisi的路径都将映射到User组件。  
在User组件中可通过`$router.params.id`的方式获取