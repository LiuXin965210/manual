# Vue中的基本概念

>以下内容看完简介后，请务必点击各自的官方文档进行入门学习

## node.js

[node.js](http://nodejs.cn/learn)是一个基于chrome v8引擎的javascript运行环境，它可以帮助我们服务端运行javascript（传统上我们都是通过浏览器来运行javascript代码），它具有如下特点：

- 性能好，底层chrome V8引擎由C++编写，编译javascript速度快
- 事件驱动的异步非阻塞IO模型，无需为每个请求创建新的线程，在处理高并发问题时，有更好的表现
- 生态系统非常庞大，npm仓库提供了大量的模块包

>同步和异步的概念描述的是用户线程与内核的交互方式：同步是指用户线程发起IO请求后需要等待或者轮询内核IO操作完成后才能继续执行；而异步是指用户线程发起IO请求后仍继续执行（直接返回），当内核IO操作完成后会通知用户线程，或者调用用户线程注册的回调函数

>阻塞和非阻塞的概念描述的是用户线程调用内核IO操作的方式：阻塞是指IO操作需要彻底完成后才返回到用户空间；而非阻塞是指IO操作被调用后立即返回给用户一个状态值，无需等到IO操作彻底完成

>一个IO操作可以分为两个步骤：发起IO请求和实际的IO操作
阻塞IO和非阻塞IO的区别在于第一步，发起IO请求是否会被阻塞，如果阻塞直到完成那么就是传统的阻塞IO，如果不阻塞，那么就是非阻塞IO。
同步IO和异步IO的区别就在于第二个步骤是否阻塞，如果实际的IO读写阻塞请求进程（IO操作完成后才能返回），那么就是同步IO，因此阻塞IO、非阻塞IO、IO复用、信号驱动IO都是同步IO，如果不阻塞，而是操作系统做完IO两个阶段的操作再将结果返回给用户线程，那么就是异步IO

## vue

[vue](https://cn.vuejs.org/v2/guide/)是一套用于构造用户界面的渐进式框架。它具有如下特点：

- 体积小，轻量，压缩后33K
- 双向数据绑定，减少开发者对dom的操作，精力放在业务逻辑上
- 采用虚拟dom技术，预先通过js进行大量的计算，最终把dom操作计算出来并优化
- 上手容易学习成本低，官网提供中文文档，并且生态系统丰富

>虚拟DOM就是为了解决浏览器性能问题而被设计出来的。如前，若一次操作中有10次更新DOM的动作，虚拟DOM不会立即操作DOM，而是将这10次更新的diff内容保存到本地一个JS对象中，最终将这个JS对象一次性attch到DOM树上，再进行后续操作，避免大量无谓的计算量。所以，用JS对象模拟DOM节点的好处是，页面的更新可以先全部反映在JS对象(虚拟DOM)上，操作内存中的JS对象的速度显然要更快，等更新完成后，再将最终的JS对象映射成真实的DOM，交由浏览器去绘制

## vue-cli

[vue-cli](https://cli.vuejs.org/zh/)也叫脚手架，官方定义为Vue.js 开发的标准工具，相比script标签引入，脚手架具有如下特点：  

- 功能丰富，对Babel、TypeScript、ESLint、PostCSS、PWA、单元测试和 End-to-end 测试提供开箱即用的支持
- 易于扩展，它的插件系统可以让社区根据常见需求构建和共享可复用的解决方案
- CLI之上的图形化界面，通过配套的图形化界面创建、开发和管理你的项目。安装vue-cil 3.x版本后`npm install -g @vue/cli`，cmd输入`vue ui`会启动可视化的管理页面

## vue-router

[vue-router](https://router.vuejs.org/zh/)是Vue.js官方的路由管理器。它和Vue.js的核心深度集成，让构建SPA变得易如反掌。包含的功能有：

- 功能丰富  
- 嵌套的路由/视图表
- 模块化的、基于组件的路由配置
- 路由参数、查询、通配符
- 基于 Vue.js过渡系统的视图过渡效果
- 细粒度的导航控制
- 带有自动激活的CSS class的链接
- 提供HTML5的history模式或hash模式，在IE9中自动降级
- 自定义的滚动条行为  

>SPA（*single-page application*）意为单页面应用由一个外壳页面和多个页面片段组成，与之对应的是MPA（_multi-page application_）多页面应用模型，像目前常见的框架：react、view、angularjs都采用的是SPA的模式。  

SPA主要有以下几个特点（以vue为例）：

- 页面仅有一个index.html，页面跳转通过加载对应组件的js实现
- 页面引用的公共资源（css、js）仅加载一次
- 初次进入页面加载时间要长于MPA应用，页面切换更加流畅（局部刷新），且画面之间传值方式简单
- 初期上手难度较大，后期维护成本低  

## vuex

[vuex](https://vuex.vuejs.org/zh/)是一个专为vue.js应用程序开发的状态管理模式。它采用集中式存储管理应用的所有组件的状态，并以相应的规则保证状态以一种可预测的方式发生变化。vuex也集成到vue的官方调试工具devtools extension，提供了诸如零配置的time-travel调试、状态快照导入导出等高级调试功能。  

## axios

[axios](https://www.kancloud.cn/yunye/axios/234845)是一个基于Promise用于浏览器和nodejs的HTTP客户端，本质上也是对原生XHR的封装，只不过它是Promise的实现版本，符合最新的ES规范。  

axios主要有以下几个特点：

- 从浏览器中创建 XMLHttpRequests
- 从 node.js 创建 http 请求
- 支持 Promise API
- 拦截请求和响应
- 转换请求数据和响应数据
- 取消请求
- 自动转换 JSON 数据
- 客户端支持防御 XSRF

## element ui

[Element](https://element.eleme.cn/#/zh-CN/component/installation)基于 Vue 2.0 的组件库，提供了组件丰富功能完备，帮助开发者快速搭建网站。由饿了么公司前端团队开源。

## sass

[Sass](https://www.sasscss.com/documentation)是一种CSS的预编译语言。它提供了变量（variables）、嵌套（nested rules）、混合（mixins）、函数（functions）等功能，并且完全兼容CSS语法。Sass能够帮助复杂的样式表更有条理，并且易于在项目内部或跨项目共享设计

## webpack

[webpack](https://www.webpackjs.com/concepts/)是一个现代 JavaScript 应用程序的静态模块打包器(module bundler)。当 webpack 处理应用程序时，它会递归地构建一个依赖关系图(dependency graph)，其中包含应用程序需要的每个模块，然后将所有这些模块打包成一个或多个bundle

## babel（了解即可）

[Babel](https://www.babeljs.cn/docs/)是一个工具链，主要用于将采用ECMAScript 2015+ 语法编写的代码转换为向后兼容的JavaScript语法，以便能够运行在当前和旧版本的浏览器或其他环境中

## eslint（了解即可）

[ESLint](https://cn.eslint.org/docs/user-guide/getting-started)是在 ECMAScript/JavaScript代码中识别和报告模式匹配的工具，它的目标是保证代码的一致性和避免错误。在许多方面它和JSLint、JSHint相似，它主要有以下几个特点：

- 默认规则包含所有 JSLint、JSHint 中存在的规则，易迁移
- 规则可配置性高：可设置「警告」、「错误」两个 error 等级，或者直接禁用
- 包含代码风格检测的规则
- 支持插件扩展、自定义规则
