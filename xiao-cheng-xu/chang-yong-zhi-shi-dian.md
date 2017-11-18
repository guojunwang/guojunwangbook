webstorm的相关配置
* [webstorm下载](#webstorm下载)
* [注册码](#注册码)
* [鼠标代码缩放](#鼠标代码缩放)
* [主题设置](#主题设置)
* [git集成使用](#git集成使用)
* [git快捷键](#git快捷键)
* [Terminal样式配置](#Terminal样式配置)
* [npm安装](#npm安装)
* [git命令跳路径](#git命令跳路径)
* [nginx配置](#nginx配置)


## WXSS
下载地址：[官网](https://www.jetbrains.com/webstorm/)

## 注册码
我们通过开发者工具快速创建了一个 QuickStart 项目。你可以留意到这个项目里边生成了不同类型的文件:：
1. json 后缀的 JSON 配置文件
2. wxml 后缀的 WXML 模板文件
3. wxss 后缀的 WXSS 样式文件
4. js 后缀的 JS 脚本逻辑文件

####小程序配置 app.json
app.json 是对当前小程序的全局配置，包括了小程序的所有页面路径、界面表现、网络超时时间、底部 tab 等。QuickStart 项目里边的 app.json 配置内容如下：
  ```
{
  "pages":[
    "pages/index/index",
    "pages/logs/logs"
  ],
  "window":{
    "backgroundTextStyle":"light",
    "navigationBarBackgroundColor": "#fff",
    "navigationBarTitleText": "WeChat",
    "navigationBarTextStyle":"black"
  }
}
  ```
  配置项细节可以参考文档 小程序的[配置 app.json](https://mp.weixin.qq.com/debug/wxadoc/dev/framework/config.html) 。
