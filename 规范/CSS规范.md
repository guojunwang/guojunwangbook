# CSS规范

webstorm的相关配置
* [规范说明](#规范说明)
* [css缩写属性](#css缩写属性)
* [CSS书写顺序](#CSS书写顺序)
* [css注释](#css注释)
* [css常用命名](#css常用命名)
* [git快捷键](#git快捷键)
* [Terminal样式配置](#Terminal样式配置)
* [npm安装](#npm安装)
* [git命令跳路径](#git命令跳路径)
* [nginx配置](#nginx配置)  

[参考1](https://www.zhihu.com/question/20100142)
[参考2](https://www.zhihu.com/question/38773260)
[参考3](https://www.zhihu.com/question/19586885)
[参考4](http://nec.netease.com/standard/css-name.html)
[参考5](http://yujiangshui.com/)
[命名参考bootcss](http://v3.bootcss.com/css/)

## css注释

### 单行注释

星号与内容之间必须保留一个空格。

```css
/* 表格隔行变色 */
```
### 多行注释
星号要一列对齐，星号与内容之间必须保留一个空格


```css
/**
 * 我是多行注释
 */
```
### 规则声明块内注释

使用 // 注释，// 后面加上一个空格，注释独立一行。


```css
.foo{
    border: 0;  
    // ....
}


```



####文件注释

```css
/**
 * @name: 文件名或模块名
 * @description: 文件或模块描述
 * @author: author-name(mail-name@domain.com)
 *          author-name2(mail-name2@domain.com)
 * @update: 2017-04-29 00:02
 */
```
当该业务项目主要由固定的一个或多个人负责时，需要添加@author标识，一方面是尊重劳动成果，另一方面方便在需要时快速定位责任人

## css缩写属性

CSS有些属性是可以缩写的，比如padding,margin,font等等，简写属性是可以让你同时设置其他几个 CSS 属性值的 CSS 属性。使用简写属性，Web 开发人员可以编写更简洁、更具可读性的样式表，节省时间和精力。  
缩写目的：为什么要让CSS属性缩写？
1、简化代码。一些CSS属性简写可以减少CSS代码从而减少CSS文件的占用字节，加快网页下载速度和网页加载打开速度。
2、优化CSS目的。其中CSS优化之一即是简化代码缩写CSS属性代码。


> background 背景属性

background 有以下属性：
```css
.class{
  background-color: #000;
  background-image: url(images/bg.gif);
  background-repeat: no-repeat;
  background-position: top right;
}
```

简写成一行声明：

```css
.class{
 background: #000 url(images/bg.gif) no-repeat top right;
}

```
简写的形式实际上等价于以上普通属性再加上 background-attachment: scroll  以及 CSS3 中的一些附加属性。

> font 文本属性

`注意`种简写方法只有在同时指定font-size和font-family属性时才起作用。如果没有这两个值不建议缩写

font 有以下属性：
```css
.class{
 font-style: italic;
 font-weight: bold;
 font-size: .8em;
 line-height: 1.2;
 font-family: Arial, sans-serif;
}
```

简写成一行声明：

```css
.class{
 font: italic bold .8em/1.2 Arial, sans-serif;
}
```
这个简写声明实际上等价于以上普通属性再加上 font-variant: normal 和 font-size-adjust: none (CSS2.0 / CSS3)，font-stretch: normal (CSS3)。

> border 边框属性

对于 border 来说，宽度、颜色和类型是可以被简写到一个声明里的。比如：

```css
.class{
 border-width: 1px;
 border-style: solid;
 border-color: #000;
}
```

简写成一行声明：

```css
.class{
 border: 1px solid #000;
}
```
> margin（外边距） 和 padding（内边距） 属性

margin 和 padding 值的简写版本类似。  

```css
.class{
 margin: 10px;（上、下、左、右各10px）
 margin: 10px 50px;（上、下10px；左、右50px）
 margin: 10px 50px 60px;（上10px；左、右50px；下60px）
 margin: 10px 50px 60px 70px;（上10px；右50px；下60px；左70px。（顺时针））
}
```


## 规范说明
##### 表现与结构完全分离
表现与结构完全分离，html代码中不涉及任何的表现元素，如：style、font、bgColor、border 等
##### 使用类选择器，放弃ID选择器
ID在一个页面中的唯一性导致了如果以ID为选择器来写CSS，就无法重用

##### 用-进行连接，不要用下划线 _ 

* 节省操作，输入的时候少按一个 shift 键
* 能良好区分 JavaScript 变量命名

##### background-image 的 url 内使用引号

如果路径里面有空格，旧版 IE 是无法识别的，会导致路径失效，建议不管是否存在空格，都添加上单引号或者双引号：


```css
div {
background-image: url('...');
}
```
##### 编码设置
采用 UTF-8 编码，在 CSS 代码头部使用：

```
/* 字符编码 */
@charset "utf-8";

```
注意，必须要定义在 CSS 文件所有字符的前面（包括编码注释），@charset 才会生效。
#####font-family 内使用引号

当字体名字中间有空格，中文名字体及 Unicode 字符编码表示的中文字体，为了保证兼容性，都建议在字体两端添加单引号或者双引号：


```css
body {
font-family: 'Microsoft YaHei', '黑体-简', '\5b8b\4f53';
}
```


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
属性的值一定要用双引号("")括起来，且一定要有值如 class="helloweb" , id="helloweb"
#####去掉小数点前的"0"


不正确：~~font-size: 0.32rem;~~

正确写法：font-size: .32rem;


##### 当长度值为 0 时省略单位


不正确：~~margin: 0px auto~~

```正确写法：margin: 0 auto```

##### 十六进制的颜色属性值使用小写和尽量简写。

十六进制的颜色属性值有些颜色代码是可以缩写的，我们就尽量缩写吧，提高用户体验为主。
不正确：~~color: #ffcc00~~

```正确写法:color: #fc0```

##### 避免使用 !important

## CSS书写顺序

1. 位置属性

 ```css
 position, z-index,top,right,bottom,left

 ```
说明：z-index只能在position属性值为relative或absolute或fixed的元素上有效。

2. 布局属性

 ```css
display,float,clear,visibility,overflow
```
3. 自身属性

 ```css
  padding, margin,width, height,border,background

 ```
4. 文本属性

 ```css
 font, line-height, letter-spacing,color,text-align,text-decoration等

 ```
5. 其他

 ```css
 animation, transition等
 ```


## css常用命名

页面结构

| 左对齐 | 居中对齐| 右对齐|居中对齐| 右对齐|
|:------ |:-----:| -----:|:-----:|:-----:|
| 容器: container/wrap | 整体宽度：wrapper | 页头：header |内容：content|页面主体：main|
| 页尾：footer | 导航：nav | 侧栏：sidebar | 栏目：column | 中间内容：center |

导航

| 左对齐 | 居中对齐| 右对齐|居中对齐| 右对齐|
|:------ |:-----:| -----:|:-----:|:-----:|
| 导航：nav| 导航：mainbav/globalnav | 子导航：subnav |顶导航：topnav|边导航：sidebar|
| 左导航：leftsidebar | rightsidebar | 边导航图标：sidebarIcon | 菜单：menu | 子菜单：submenu |
|标题: title|

功能

| 左对齐 | 居中对齐| 右对齐|居中对齐| 右对齐|
|:------ |:-----:| -----:|:-----:|:-----:|
| 标志：logo| 登陆：login | 登录条：loginbar |注册：regsiter|产品：products|
| 产品价格：productsPrices |产品评论：productsReview | 编辑评论：editor-review | 最新产品：news-release|广告/标语：banner
| 摘要:summary| 生产商：publishe | 缩略图：screenshot |常见问题：faqs|产品：products|
| 关键词：keyword| 博客：blog |论坛：forum |搜索：search|搜索输入框：search-input|
| 搜索输出：search-output| 搜索结果：search-results |加入我们：joinus |状态：status|按钮：btn|







