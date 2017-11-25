# CSS规范

webstorm的相关配置
* [命名规则说明](#命名规则说明)
* [注册码](#注册码)
* [鼠标代码缩放](#鼠标代码缩放)
* [主题设置](#主题设置)
* [git集成使用](#git集成使用)
* [git快捷键](#git快捷键)
* [Terminal样式配置](#Terminal样式配置)
* [npm安装](#npm安装)
* [git命令跳路径](#git命令跳路径)
* [nginx配置](#nginx配置)


## 命名规则说明
##### 使用类选择器，放弃ID选择器
ID在一个页面中的唯一性导致了如果以ID为选择器来写CSS，就无法重用

##### 不建议使用下划线 _ 进行连接

* 节省操作，输入的时候少按一个 shift 键
* 能良好区分 JavaScript 变量命名


## 鼠标代码缩放

WebStorm设置Ctrl+滚轮调整代码字体大小：
1. 点击左上角的File，再点击setting；
2. Editor->General，选择Change font size (Zoom) with Ctrl+Mouse Wheel；
3. 点击OK即可

## 主题设置

1. 方法1

 A. 下载安装：主题下载地址1：[插件官方下载地址](https://plugins.jetbrains.com/)
  
  B.  操作步骤：File --> setting--> plugins-->install plugins from disk-->选择下载到本地的插件即可导入
2. 方法2

 A.主题下载方式2(开发工具中下载):File --> setting--> plugins-->Browse repositor
 B.操作步骤：然后输入Theme 看到Material Theme UI 后-->点击进行下载-->安装完成后重启，重启后会发现文件内容界面没有改变，需要设置下：1.点击左上角的File，再点击setting；2.Editor->Color Scheme，选择Material.Theme相关主题，背景立即改变；

## git集成使用



## git快捷键

1. add文件 ctrl + Alt + a （add后红色的文件名变为了蓝色）
2. 添加commit注释 ctrl + k
3. push提交 ctrl + shift + k

## Terminal样式配置
1. 配置位置：
 在File --> setting-->Editor-->Color Scheme-->下的console color和console font

2. 重启webstorm即可

## npm安装

支持npm操作，需要node环境支持，现在的node版本中已经集成安装npm，只需要安装node即可

 1. node下载地址1.[国内下载地址](http://nodejs.cn/)  

## git命令跳路径

1. 手动新建无后缀文件mg（mg就是马果首字母）或mg.sh文件、命令创建方式：

 ```
 touch mg.sh #创建mg.sh文件  
 也可以touch mg #创建mg文件

 ```
2. 加入bash环境及其指定跳转路径(命令操作：vim mg --> insert-->  :wq 保存并退出)：

 ```
 #！/bin/bash
 cd d:/project/chedai-bos-web

 ```
3. 使用：输入. ./mg按enter键即可跳转到d:/project/chedai-bos- web中

 ```
 . ./mg
 ```

## nginx配置




