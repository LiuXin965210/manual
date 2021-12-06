# Vue目录结构详解

<!-- ## 2.x版本目录结构

|--dist                             打包之后的发布目录
|   |--css                          存放打包之后的css文件夹  
|   |--img                          存放打包之后的img资源文件夹  
|   |--js                           存放打包之后存放的js文件夹  
|   |--index.html                   存放打包之后的入口页面  
|
|--mock                             本地前端工程mock的一些数据
|
|--node_module                      本地项目的第三方依赖  
|
|--public
|
|--src                              开发目录
|   |
|   |--assets                       开发时候存放的一些静态资源  
|   |
|   |--components                   业务开发的组件
|   |
|   |--lib                          开发过程中自己写的一些工具库  
|   |
|   |-plugins
|   |
|   |-router                        前端工程的路由，将其模块化，单独的拿出来
|   |   |
|   |   |-router.js                 工程的路由配置
|   |  
|   |-vuex                          vuex转态管理  
|   |   |
|   |   |-store.js
|   |
|   |-App.vue                       工程的入口文件，也是整个工程的根组件  
|   |-main.js                       工程的入口文件，用以引入一些全局变量  
|   |-.gitignore                    提交git仓库忽略的文件
|   |-babel.config.js               babel的一些配置
|   |-package.json                  依赖的第三方配置文件
|   |-readMe.md                     项目简单介绍 -->

## 3.x版本

```txt
|   |--node_modules         -- 所有的项目依赖包都放在这个目录下
|   |--public               -- 公共文件夹
|       |--favicon.ico      -- 网站的显示图标
|       |--index.html       -- 入口的html文件
|   |--src                  -- 源文件目录，编写的代码基本都在这个目录下
|       |--assets           -- 放置静态文件的目录，比如logo.pn就放在这里
|       |--components       -- Vue的组件文件，自定义的组件都会放到这
|       |--router           -- vue-router vue路由的配置文件，
|       |--store            -- 存放 vuex 为vue专门开发的状态管理器，
|       |--views            -- 存放视图文件，
|       |--App.vue          -- 根组件
|       |--main.js          -- 入口文件，因为采用了TypeScript所以是ts结尾
|   |--.browserslistrc      -- 在不同前端工具之间公用目标浏览器和node版本的配置文件，作用是设置兼容性
|   |--.eslintrc.js         -- Eslint的配置文件，不用作过多介绍
|   |--.gitignore           -- 用来配置那些文件不归git管理
|   |--.babel.config.js     -- Babel转码器的配置文件，作用于整个项目
|   |--package.json         -- 命令配置和包管理文件
|   |--package-lock.json    -- 模块包的版本锁定文件
|   |--README.md            -- 项目的说明文件，使用markdown语法进行编写
|   |--vue.config.js        -- 非默认生成，用于请求代理, webpack 配置, 打包输出等都会在这里配置
```

### .browserslistrc

### .eslintrc.js

### .babel.config.js

### vue.config.js
