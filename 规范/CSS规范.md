# CSS规范

webstorm的相关配置
* [命名规则说明](#命名规则说明)
* [css缩写属性](#css缩写属性)
* [鼠标代码缩放](#鼠标代码缩放)
* [主题设置](#主题设置)
* [git集成使用](#git集成使用)
* [git快捷键](#git快捷键)
* [Terminal样式配置](#Terminal样式配置)
* [npm安装](#npm安装)
* [git命令跳路径](#git命令跳路径)
* [nginx配置](#nginx配置)

## css缩写属性

CSS有些属性是可以缩写的，比如padding,margin,font等等，简写属性是可以让你同时设置其他几个 CSS 属性值的 CSS 属性。使用简写属性，Web 开发人员可以编写更简洁、更具可读性的样式表，节省时间和精力。

> background 背景属性

background 有以下属性：
```css
background-color: #000;
background-image: url(images/bg.gif);
background-repeat: no-repeat;
background-position: top right;
```

简写成一行声明：

```css
background: #000 url(images/bg.gif) no-repeat top right;
```
简写的形式实际上等价于以上普通属性再加上 background-attachment: scroll  以及 CSS3 中的一些附加属性。

> font 文本属性（不建议缩写）

font 有以下属性：
```css
font-style: italic;
font-weight: bold;
font-size: .8em;
line-height: 1.2;
font-family: Arial, sans-serif;
```

简写成一行声明：

```css
font: italic bold .8em/1.2 Arial, sans-serif;
```
这个简写声明实际上等价于以上普通属性再加上 font-variant: normal 和 font-size-adjust: none (CSS2.0 / CSS3)，font-stretch: normal (CSS3)。
`注意`种简写方法只有在同时指定font-size和font-family属性时才起作用

> border 边框属性

对于 border 来说，宽度、颜色和类型是可以被简写到一个声明里的。比如：

```css
border-width: 1px;
border-style: solid;
border-color: #000;
```

简写成一行声明：

```css
border: 1px solid #000
```
> margin（外边距） 和 padding（内边距） 属性

margin 和 padding 值的简写版本类似。  

```css
margin: 10px;（上、下、左、右各10px）
margin: 10px 50px;（上、下10px；左、右50px）
margin: 10px 50px 60px;（上10px；左、右50px；下60px）
margin: 10px 50px 60px 70px;（上10px；右50px；下60px；左70px。（顺时针））
```


## 命名规则说明
##### 使用CSS缩写属性
实例：
```css
 #不正确
 font-size: 0.32rem;
 #正确
 font-size: .32rem;
```



##### 使用类选择器，放弃ID选择器
ID在一个页面中的唯一性导致了如果以ID为选择器来写CSS，就无法重用

##### 用-进行连接，不建议使用下划线 _ 进行连接

* 节省操作，输入的时候少按一个 shift 键
* 能良好区分 JavaScript 变量命名

##### 所有的命名最好都小写
定义的选择器名，属性及属性值的书写皆为小写
##### 尽量使用英文命名原则

##### 尽量不缩写，除非一看就明白的单词
很多用户都喜欢简写类名，但前提是要让人看懂你的命名才能简写哦!
实例：
```css
 #不正确
 .navigation{
 
 }
 .atr{
 
 }

 #正确
 .nav{
 
 }
 .author{
 
 }
```





##### 属性的值一定要用双引号("")括起来
#####去掉小数点前的"0"

实例：
```css
 #不正确
 font-size: 0.32rem;
 #正确
 font-size: .32rem;
```


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




