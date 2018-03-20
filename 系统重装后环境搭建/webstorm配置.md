# webstorm配置

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
* [Emmet预先显示HTML代码结构](#Emmet预先显示HTML代码结构)
* [同步热加载插件](#同步热加载插件)
* [编码快捷键](#编码快捷键)
* [开发工具/浏览器分屏](#开发工具/浏览器分屏)
* [收藏夹](#收藏夹)
* [本地历史功能](#本地历史功能)
* [常用快捷键](#常用快捷键)
* [全屏模式切换](#全屏模式切换)





## webstorm下载
下载地址：[官网](https://www.jetbrains.com/webstorm/)

## 注册码
JetBrains下的开发工具都可以按照下面方法激活：
1. 打开webstorm软件
2. 在看到的License Activation窗口中选择“License server”
3. 在输入框输入下面的网址：
  ```
  http://idea.iteblog.com/key.php #或者  http://idea.imsxm.com
  ```
4. 点击Active即可

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
4. 从VCS 更新项目:Ctrl + T 
5. 查看最新改变 Alt + Shift + C 


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

Edit  > Emmet > HTML > enable abbreviation preview

## Emmet预先显示HTML代码结构
在 setting-->Editor> Emmet> HTML>选中 enable abbreviation preview

## 同步热加载插件
1. Live Edit + JetBrains IDE Support  
第一步：Live Edit webstorm2018自带安装（如果没安装，在插件位置安装重启即可）  
第二步：在setting中选中Live Edit中除了第一个nodejs的其他多选框（有node使用，选中nodejs）  
第三步：在chrome 应用商店中安装JetBrains IDE Support插件  
第四步：在需要编辑的html页面选择debug在chrome打开即可   
说明：
1、运行后，底部debug下会出现 console,这个可浏览器 中的是一样的，但是js再次修改js输出不会更新  
2、 color字段颜色不会及时更改，需要点下space空格键
2. Emmet LiveStyle
3. webpack热加载
4. 浏览器自动定时刷新（如360浏览器自带并可以设置）


## 编码快捷键

1.变量声明 Ctrl + Alt + V


```JavaScript
/*
 * webStorm 快捷键方式得到 var number = 1;
 * 第一步:输入 1
 * 第二步:Ctrl + Alt + V 得到 var number = 1; //说明：es6有let var const 三种变量声明方式 点击选择一种 以后声明默认就是选中的，es5只有var一种
 * 第三步:修改变量名number，快捷键按完后直接到变量名number，直接修改即可
 * 第四步：按下enter确认
 * 第五步：shift + enter到下一行
 */

var number = 1;
```


2.对象声明

对象声明 Ctrl + Alt + V

```JavaScript
/*
 * webStorm 快捷键方式得到 var car = new Car();
 * 第一步:输入 new Ca
 * 第二步:点击 Car() 得到 new Car ()
 * 第三步:Ctrl + Alt + V 得到 var car = new Car(); 
 */
 var car = new Car();

```


3.js、css、图片路径全局自动补全及其提示

第一步：在设置中搜索 Code completion  
第二步：在Code completion 右边面板中的Case sensitive completion 右边的下拉列表中选中None 
第三步：Ctrl + Alt + space得到所有文件提示  
第四步：输入搜索或者选中自己需要的引用资源文件 

4.实现图片路径提示+图片预览  

第一步：按照3的步骤配置好Code completion  
第二步：在css 背景设置url中或者img的src中" "里面按Ctrl + Alt + space得到图片资源提示  
第三步：按快捷键：Ctrl + shift + I 即可看到图片预览  


## 开发工具/浏览器分屏
window+左右方向键 就可以一边编码一边在浏览器看效果

## 收藏夹

当工程目录很庞大时，有些子目录很经常打开，但层级又很深，这时候可以把目录添加到收藏夹里面，添加成功后，左侧有个“Favorites”菜单


## 本地历史功能
找回代码的好办法：项目文件夹/单个文件右键点击local history即可

## 常用快捷键
Ctrl + W：选择代码块，一般是增量选择  
Ctrl + Shift + W：上个快捷键的回退，减量选择代码  
Ctrl + Alt + L：代码格式化
Ctrl + C ：拷贝当前行或者所选代码块到剪切
Ctrl + D：复制当前行或者所选代码块
Ctrl + X ：剪切当前行或所选代码块到剪切板
Ctrl + Y：删除光标所在位置行
Shift + Enter：另起一行
Ctrl + Shift + U：光标所在位置大小写转换
Ctrl + +/-：扩展/缩减代码块
Ctrl + Shift+ +/- 扩张/缩减所有
Ctrl + F:当前文件内快速查找代码
Ctrl + Shift + F: 指定文件内寻找路径(搜狗输入法有热键冲突,记得关掉)
`Ctrl + Shift + Backspace `:向最近编辑定位导航
Alt + Home:显示导航栏
F5： 拷贝
F6： 移动
Ctrl + Alt + M：提取函数
Ctrl + Alt + F11:切换全屏模式
Ctrl + Shift + F12: 切换最大化编辑器

## 全屏模式切换
在工具栏中的view中设置：
1. 进入演示模式view--》enter presentation model  
2. 进入全屏模式view--》enter full model
3. 进入免打扰模式 view--》Enter Distraction Free Mode
