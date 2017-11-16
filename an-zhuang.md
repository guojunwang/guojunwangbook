vuewebstorm的相关配置
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
1. vue:(view读法一样)
2. install:(因私躲)
3. run:( [rʌn])
4. router:(入特尔)


## 环境搭建
Vue.js 提供一个[官方命令行工具](https://github.com/vuejs/vue-cli)，可用于快速搭建大型单页应用。该工具提供开箱即用的构建工具配置，带来现代化的前端开发流程。只需几分钟即可创建并启动一个带热重载、保存时静态检查以及可用于生产环境的构建配置的项目：

1. 使用vue-cli脚手架搭建
先决条件：Node.js（> = 4.x，6.x首选），npm版本3+和Git。
如果npm安装时间较长换成[cnpm](https://npm.taobao.org/)；
```shell
# 第一步:全局安装 vue-cli
$ npm install --global vue-cli
# 第二步:创建一个基于 webpack 模板的新项目
# 会有如下提示:项目名称（有默认）、描述、作者、代码检测器
$ vue init webpack my-project
# 第三步:进入创建的项目目录
$ cd my-project
# 第四步:安装依赖
$ npm install
# 运行项目
$ npm run dev
```

2. 纯手工搭建

