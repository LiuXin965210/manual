# 常见问题

>记录一些开发过程中和项目部署常见的问题

## 前端

### mall-admin-web-master\node_modules\node-gyp\gyp\gyp_main.py': [Errno 22] Invalid argument

**本地环境：**

`nodejs v14.17.5`

`python v2.7`

`"node-sass": "^4.13.0"`

**问题发现：**

从github上拉下了一个前端项目*mall-admin-web-master*，执行`npm install`时，控制台输出上述错误

**问题关键点：**

>网上大多数解决方案都是node-sass与node版本不兼容，node降版本或者node-sass升版本。还有部分解决方案是安装python2.7和下载node-gyp`npm install -g node-gyp`

找到log中首个错误，不要只看红色的Err部分，第一次看的时候就忽略掉了下图红圈标识的错误！
![实际错误出现位置](./assets/error_1.png)

**问题解决：**

执行`npm config set python python2.7`后重新安装

## 项目部署

### Error response from daemon: driver failed programming external connectivity on endpoint nginx

**本地环境：**

**问题发现：**

部署前后端分离部署时，执行`docker start nginx`启动失败

**问题关键点：**

**问题解决：**

`systemctl restart docker`重启docker后再次执行命令`docker start nginx`启动成功
