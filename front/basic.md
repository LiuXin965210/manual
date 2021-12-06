# Vue中的基本概念

>以下内容看完简介后，请务必点击各自的官方文档进行入门学习

## node.js

[node.js](http://nodejs.cn/learn)是一个基于chrome v8引擎的javascript运行环境，它可以帮助我们服务端运行javascript（传统上我们都是通过浏览器来运行javascript代码），它具有如下特点：

1. 性能好，底层chrome V8引擎由C++编写，编译javascript速度快
2. 事件驱动的异步非阻塞IO模型，无需为每个请求创建新的线程，在处理高并发问题时，有更好的表现
3. 生态系统非常庞大，npm仓库提供了大量的模块包

>异步非阻塞IO：

## vue

[vue](https://cn.vuejs.org/v2/guide/)是一套用于构造用户界面的渐进式框架。它具有如下特点：

1. 体积小，轻量，压缩后33K
2. 双向数据绑定，减少开发者对dom的操作，精力放在业务逻辑上
3. 采用虚拟dom技术，预先通过js进行大量的计算，最终把dom操作计算出来并优化
4. 上手容易学习成本低，官网提供中文文档，并且生态系统丰富

>虚拟dom：

## vue-cli

[vue-cli](https://cli.vuejs.org/zh/)也叫脚手架，官方定义为Vue.js 开发的标准工具，相比script标签引入，脚手架具有如下特点：  

1. 功能丰富，对Babel、TypeScript、ESLint、PostCSS、PWA、单元测试和 End-to-end 测试提供开箱即用的支持
2. 易于扩展，它的插件系统可以让社区根据常见需求构建和共享可复用的解决方案
3. CLI之上的图形化界面，通过配套的图形化界面创建、开发和管理你的项目。安装vue-cil 3.x版本后`npm install -g @vue/cli`，cmd输入`vue ui`会启动可视化的管理页面

## vue-router

[vue-router](https://router.vuejs.org/zh/)是Vue.js官方的路由管理器。它和Vue.js的核心深度集成，让构建SPA变得易如反掌。包含的功能有：

1. 功能丰富  
2. 嵌套的路由/视图表
3. 模块化的、基于组件的路由配置
4. 路由参数、查询、通配符
5. 基于 Vue.js过渡系统的视图过渡效果
6. 细粒度的导航控制
7. 带有自动激活的CSS class的链接
8. 提供HTML5的history模式或hash模式，在IE9中自动降级
9. 自定义的滚动条行为  

>SPA（*single-page application*）意为单页面应用由一个外壳页面和多个页面片段组成，与之对应的是MPA（_multi-page application_）多页面应用模型，像目前常见的框架：react、view、angularjs都采用的是SPA的模式。  

SPA主要有以下几个特点（以vue为例）：

1. 页面仅有一个index.html，页面跳转通过加载对应组件的js实现
2. 页面引用的公共资源（css、js）仅加载一次
3. 初次进入页面加载时间要长于MPA应用，页面切换更加流畅（局部刷新），且画面之间传值方式简单
4. 初期上手难度较大，后期维护成本低  

## vuex

[vuex](https://vuex.vuejs.org/zh/)是一个专为vue.js应用程序开发的状态管理模式。它采用集中式存储管理应用的所有组件的状态，并以相应的规则保证状态以一种可预测的方式发生变化。vuex也集成到vue的官方调试工具devtools extension，提供了诸如零配置的time-travel调试、状态快照导入导出等高级调试功能。  

## axios

[axios](https://www.kancloud.cn/yunye/axios/234845)是一个基于Promise用于浏览器和nodejs的HTTP客户端，本质上也是对原生XHR的封装，只不过它是Promise的实现版本，符合最新的ES规范。  

axios主要有以下几个特点：

1. 从浏览器中创建 XMLHttpRequests
2. 从 node.js 创建 http 请求
3. 支持 Promise API
4. 拦截请求和响应
5. 转换请求数据和响应数据
6. 取消请求
7. 自动转换 JSON 数据
8. 客户端支持防御 XSRF

## element ui

## webpack

## babel

## eslint