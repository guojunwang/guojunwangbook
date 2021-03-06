只需vuewebstorm的相关配置
* [vue常用单词](#vue常用单词)
* [环境搭建](#环境搭建)
* [鼠标代码缩放](#鼠标代码缩放)
* [主题设置](#主题设置)
* [git集成使用](#git集成使用)
* [git快捷键](#git快捷键)
* [Terminal样式配置](#Terminal样式配置)
* [npm安装](#npm安装)
* [git命令跳路径](#git命令跳路径)
* [nginx配置](#nginx配置)


## vue常用单词
1. vue(view读法一样)
2. install(因私躲)
3. run( [rʌn])
4. router(入特尔)
5. modules(默滴友思)


## 环境搭建
Vue.js 提供一个[官方命令行工具](https://github.com/vuejs/vue-cli)，可用于快速搭建大型单页应用。该工具提供开箱即用的构建工具配置，带来现代化的前端开发流程。只需几分钟即可创建并启动一个带热重载、保存时静态检查以及可用于生产环境的构建配置的项目：

1. 使用vue-cli脚手架搭建
先决条件：Node.js（> = 4.x，6.x首选），npm版本3+和Git。
如果npm安装时间较长换成[cnpm](https://npm.taobao.org/)；
```shell
# 第一步:全局安装 vue-cli
$ npm install --global vue-cli
# 第二步:创建一个基于 webpack 模板的新项目
# 执行如下命令后会有如下提示:项目名称（有默认）、描述、作者、是否需要es6代码风格检查器（需要yes）、模板（直接使用标准的standard）、单元测试（不需要n）、e2e测试（不需要n）
$ vue init webpack my-project
# 第三步:进入创建的项目目录
$ cd my-project
# 第四步:安装依赖
$ npm install
# 运行项目
$ npm run dev
```
项目目录介绍：
build和config：webpack配置相关
node-modules：npm install安装的依赖库
src：存放源码项目
static：存放第三方静态资源；里面的.gitkeep文件：代表的是目录为空也可以把目录提交的github仓库

2. 纯手工搭建
3. 项目有标红提示,需要设置成es6
解决方法：webstorm编辑器导入vue项目有标红或有警告信息，需要配置webstorm的JavaScript的版本，默认是es5，要设置成es6，
操作步骤：File --> setting-->Languages & Frameworks-->Javascript--> 选择ECMAScript6-->apply-->ok


