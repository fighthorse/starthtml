# starthtml
前端框架-官网模板-采用Html5+vueJS2.0 +Bootstrap CSS+npm工具

-------------------------------------------------------------------------------------------
VUE框架构建
-------------------------------------------------------------------------------------------
安装nodejs 其中会包含npm webpack

安装vue淘宝镜像 
npm install -g vue –registry=https://registry.npm.taobao.org

安装webpack 
npm install webpack -g

安装vue脚手架 
npm install vue-cli -g

根据模板创建项目 
vue init webpack 项目名字<项目名字不能用中文>

会有一些初始化的设置，如下输入: 
Target directory exists. Continue? (Y/n) 直接回车默认(然后会下载 vue2.0模板，这里可能需要连代理) 
Project name (vue-test) 直接回车默认 
Project description (A Vue.js project) 直接回车默认 
Author 直接回车默认 
Use ESLint to lint your code? n 
pick an eslint preset. 默认Standard 
setup unit tests with karma + mocha?No(单元测试不需要) 
setup e2e tests with Nightwatch?No(单元测试不需要)

进入项目 
打开终端 
cd 项目名字

安装项目依赖 
npm install

安装 vue 路由模块vue-router和网络请求模块vue-resource –save-dev 是你开发时候依赖的东西，–save 是你发布之后还依赖的东西 
npm install vue-router vue-resource –save

启动项目 
npm run dev

发布项目 
npm run build

-------------------------------------------------------------------------------------------
项目结构
-------------------------------------------------------------------------------------------
文件\目录	      说明
build	      这个是我们最终发布的时候会把代码发布在这里，在开发阶段，我们基本不用管。
config	      配置目录，默认配置没有问题，所以我们也不用管
node_modules  这个目录是存放我们项目开发依赖的一些模块，这里面有很多很多内容，不过高兴的是，我们也不用管
src	          我们的开发目录，基本上绝大多数工作都是在这里开展的
static	      资源目录，我们可以把一些图片啊，字体啊，放在这里。
test	      初始测试目录，没用，删除即可
.xxxx文件	  这些是一些配置文件，包括语法配置，git配置等。基本不用管，放着就是了
index.html	  首页入口文件，基本不用管，如果是开发移动端项目，可以在head区域加上你合适的meta头
package.json  项目配置文件。前期基本不用管，但是你可以找一下相关的资料，学习一下里面的各项配置。至少，要知道分别是干嘛的。
README.md	  简述文档

src是开发目录
把文件夹和文件都新建空文件即可。注意，用scss来写css文件的。

文件\目录	  说明
component    组件文件夹我们写的一些公用的内容可以放在这里的。
config	     核心配置文件夹
frame	     存放自路由的文件夹
page	     项目模板文件夹,所有的页面文件全部存放与此，后面会根据需要来建立各种子目录
style	     样式存放目录

-------------------------------------------------------------------------------------------
项目开发
-------------------------------------------------------------------------------------------
开始制作页面 

利用 http://cnodejs.org/api 这里公开的api来做项目。
这里，我们假设我们的项目是做俩页面，一个列表页面，一个内容页面。列表页面有分页等，内容页面展示。

因此，我们需要两个模板文件。
我们在src/page目录下面新建两个文件，分别是index.vue和content.vue

代码分别是
//index.vue
<template>
  <div>index</div>
</template>

//content.vue
<template>
  <div>content</div>
</template>

接下来，我们需要安装VueRouter2到我们的项目。参考文档见VueRouter2安装文档 https://router.vuejs.org/zh-cn/installation.html
在终端中，我们把当前目录跳转到我们的项目，然后执行npm install vue-router -D命令
后面加一个-D的参数呢？这个是为了让我们的安装的vue-router这个插件写入到package.json配置文件中

配置运行端口
如果没有跑起来，提示下面的错误，就表明默认的端口8080被占用了。一般不会被占用，但是也有可能被占用。所以，我们这边来学习一下如何配置运行端口。
打开项目根目录下/config/index.js配置文件，找到
 port: 8080

安装sass-loader以及node-sass插件
如果你上面是严格代码来的，这里应该会提示缺少sass-loader组件错误。
npm install sass-loader -D进行安装。
npm install node-sass -D进行安装。

其他错误
关闭格式校验检查 config/index.js中
 useEslint: false ,

安装superagent组件
要请求接口，就必须有相对应的组件。如果你使用过jquery，应该熟悉其中的AJAX方法。当然，在vue中，我们就不考虑使用jquery了。我们使用superagent这个组件。

安装非常简单，我们首先跳转到项目根目录，然后输入 npm install superagent -D进行安装。

http://localhost:8086/#/user/info
http://localhost:8086/#/user/


本项目依照此博文撰写，作为学习
http://blog.csdn.net/fungleo/article/details/53213167
本项目为旧版本搭建



