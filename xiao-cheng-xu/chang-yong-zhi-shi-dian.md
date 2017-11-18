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
为了适应广大的前端开发者，WXSS 具有 CSS 大部分特性。同时为了更适合开发微信小程序，WXSS 对 CSS 进行了扩充以及修改。

与 CSS 相比，WXSS 扩展的特性有：

1. 尺寸单位
2. 样式导入

尺寸单位
rpx（responsive pixel）: 可以根据屏幕宽度进行自适应。规定屏幕宽为750rpx。如在 iPhone6 上，屏幕宽度为375px，共有750个物理像素，则750rpx = 375px = 750物理像素，1rpx = 0.5px = 1物理像素。
注意：开发微信小程序时设计师可以用 iPhone6的 750作为视觉稿的标准

使用@import语句可以导入外联样式表，@import后跟需要导入的外联样式表的相对路径，用;表示语句结束。

实例代码
```
/** common.wxss **/
.small-p {
  padding:5px;
}
```



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
