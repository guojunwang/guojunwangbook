# CSS规范
css参考
webstorm的相关配置
* [规范说明](#规范说明)
* [css缩写属性](#css缩写属性)
* [CSS书写顺序](#CSS书写顺序)
* [css注释](#css注释)
* [css常用命名](#css常用命名)
* [css最佳实践命名](#css最佳实践命名)
* [选择器顺序](#选择器顺序)
* [选择器的权重及优先规则](#选择器的权重及优先规则)
* [css优先级分类](#css优先级分类)
* [css选择器分类](#css选择器分类)
* [CSS中可以和不可以继承的属性](#CSS中可以和不可以继承的属性)  
* [readMe](#readMe)  



[参考1](https://www.zhihu.com/question/20100142)
[参考2](https://www.zhihu.com/question/38773260)
[参考3](https://www.zhihu.com/question/19586885)
[参考4](http://nec.netease.com/standard/css-name.html)
[参考5](http://yujiangshui.com/)
[命名参考bootcss](http://v3.bootcss.com/css/)
[常用参考命名](http://www1.qdfuns.com/blog-5445898-5398950.html)
## CSS中可以和不可以继承的属性
一、无继承性的属性

1、display：规定元素应该生成的框的类型

2、文本属性：

vertical-align：垂直文本对齐

text-decoration：规定添加到文本的装饰

text-shadow：文本阴影效果

white-space：空白符的处理

unicode-bidi：设置文本的方向

3、盒子模型的属性：width、height、margin 、margin-top、margin-right、margin-bottom、margin-left、border、border-style、border-top-style、border-right-style、border-bottom-style、border-left-style、border-width、border-top-width、border-right-right、border-bottom-width、border-left-width、border-color、border-top-color、border-right-color、border-bottom-color、border-left-color、border-top、border-right、border-bottom、border-left、padding、padding-top、padding-right、padding-bottom、padding-left

4、背景属性：background、background-color、background-image、background-repeat、background-position、background-attachment

5、定位属性：float、clear、position、top、right、bottom、left、min-width、min-height、max-width、max-height、overflow、clip、z-index

6、生成内容属性：content、counter-reset、counter-increment

7、轮廓样式属性：outline-style、outline-width、outline-color、outline

8、页面样式属性：size、page-break-before、page-break-after

9、声音样式属性：pause-before、pause-after、pause、cue-before、cue-after、cue、play-during

 

二、有继承性的属性

1、字体系列属性

font：组合字体

font-family：规定元素的字体系列

font-weight：设置字体的粗细

font-size：设置字体的尺寸

font-style：定义字体的风格

font-variant：设置小型大写字母的字体显示文本，这意味着所有的小写字母均会被转换为大写，但是所有使用小型大写字体的字母与其余文本相比，其字体尺寸更小。

font-stretch：对当前的 font-family 进行伸缩变形。所有主流浏览器都不支持。

font-size-adjust：为某个元素规定一个 aspect 值，这样就可以保持首选字体的 x-height。

2、文本系列属性

text-indent：文本缩进

text-align：文本水平对齐

line-height：行高

word-spacing：增加或减少单词间的空白（即字间隔）

letter-spacing：增加或减少字符间的空白（字符间距）

text-transform：控制文本大小写

direction：规定文本的书写方向

color：文本颜色

3、元素可见性：visibility

4、表格布局属性：caption-side、border-collapse、border-spacing、empty-cells、table-layout

5、列表布局属性：list-style-type、list-style-image、list-style-position、list-style

6、生成内容属性：quotes

7、光标属性：cursor

8、页面样式属性：page、page-break-inside、windows、orphans

9、声音样式属性：speak、speak-punctuation、speak-numeral、speak-header、speech-rate、volume、voice-family、pitch、pitch-range、stress、richness、、azimuth、elevation

 

三、所有元素可以继承的属性

1、元素可见性：visibility

2、光标属性：cursor

 

四、内联元素可以继承的属性

1、字体系列属性

2、除text-indent、text-align之外的文本系列属性

 

五、块级元素可以继承的属性

1、text-indent、text-align
## css优先级分类
css的优先级由高到低分为6组：
1. 第一优先级：无条件优先的属性只需要在属性后面使用！important。它会覆盖页面内任何位置定义的元素样式。ie6不支持该属性。
2. 第二优先级：在html中给元素标签加style，即内联样式。该方法会造成css难以管理，所以不推荐使用。
3. 第三优先级：由一个或多个id选择器来定义。例如，#id{margin:0;}会覆盖.classname{margin:3pxl}
4. 第四优先级：由一个或多个类选择器、属性选择器、伪类选择器定义。如.classname{margin:3px}会覆盖div{margin:6px;}
5. 第五优先级：由一个或多个类型选择器定义。如div{marigin:6px;}覆盖*{margin:10px；}
6. 第六优先级：通配选择器，如*{marigin:6px;}

## 选择器的权重及优先规则
我们把特殊性分为4个等级，每一个等级代表一类选择器，没个等级的值相加得出选择器的权重。
4个等级的定义如下：
1. 第一等级：代表内联样式，如style=""，权值为 1000
2. 第二等级：代表id选择器，如#content，权值为100
3. 第三等级：代表类，伪类和属性选择器，如.content，权值为10
4. 第四等级：代表标签选择器和伪元素选择器，如div p，权值为1
注意：通用选择器（*），子选择器（>），和相邻同胞选择器（+）并不在这个等级中，所以他们的权值为0


## 选择器分类
[选择器分类参考1](https://zhuanlan.zhihu.com/p/22341291)
[选择器分类参考2](http://www.runoob.com/cssref/css-selectors.html)
选择器分类：
CSS选择器的效率从高到低做了一个排序：

1. id选择器（#myid）
2. 类选择器（.myclassname）
3. 标签选择器（div,h1,p）
4. 相邻选择器（h1+p）
5. 子选择器（ul  > li）
6. 后代选择器（li a）
7. 通配符选择器（*）
8. 属性选择器（a[rel="external"]）
9. 伪类选择（a:hover,li:nth-child）  

谈到CSS选择器可能大家最熟悉与常用的就是 标签、id、class选择器了，从效率上来说它们三个无疑最高的选择，我们确实也应优先使用，但在实际开发中，我们可能还有一些友好的选择器，下面列举一些常用css选择器（注意只包括常用有代表性的选择器，部分少用的未列举）：  

1. 基本选择器，效率最高;  id 、class、标签、* 通用选择器
2. 组合选择器，效率相对来基本选择器来说较低，‘h1,p多类’、‘div  p后代’、‘div>p子’、‘div~p 同级’、‘div+p相邻（div同级的后一个元素）’选择器
3. 属性选择器，效率相对来说又低一层，E[arr]、E[att^=”val”]、E[att$=”val”]、E[att*=”val”]
4. 伪类选择器，效率最低，:hover  :active  :focus  :first-child :checked :enabled :nth-child(n) :nth-of-type(n)
      (E:after E:before E:first-letter E:first-line伪元素）


## css最佳实践命名

最佳选择器写法（模块）

```css
/* 这是某个模块 */
.m-nav{}/* 模块容器 */
.m-nav li,.m-nav a{}/* 先共性  优化组合 */
.m-nav li{}/* 后个性  语义化标签选择器 */
.m-nav a{}/* 后个性中的共性 按结构顺序 */
.m-nav a.a1{}/* 后个性中的个性 */
.m-nav a.a2{}/* 后个性中的个性 */
.m-nav .z-crt a{}/* 交互状态变化 */
.m-nav .z-crt a.a1{}
.m-nav .z-crt a.a2{}
.m-nav .btn{}/* 典型后代选择器 */
.m-nav .btn-1{}/* 典型后代选择器扩展 */
.m-nav .btn-dis{}/* 典型后代选择器扩展（状态） */
.m-nav .btn.z-dis{}/* 作用同上，请二选一（如果可以不兼容IE6时使用） */
.m-nav .m-sch{}/* 控制内部其他模块位置 */
.m-nav .u-sel{}/* 控制内部其他元件位置 */
.m-nav-1{}/* 模块扩展 */
.m-nav-1 li{}
.m-nav-dis{}/* 模块扩展（状态） */
.m-nav.z-dis{}/* 作用同上，请二选一（如果可以不兼容IE6时使用） */
```


布局（.g-）

| 语义 | 命名| 简写|
|:-------:|:-------:|:------:|
|文档|	doc	|doc|
|头部	|head	|hd|
|主体	|body	|bd|
|尾部	|foot	|ft|
|主栏	|main	|mn|
|主栏子容器|mainc|	mnc|
|侧栏	|side	|sd|
|侧栏子容器	|sidec	|sdc|
|盒容器	|wrap/box|	wrap/box|

模块（.m-）、元件（.u-）

| 语义 | 命名| 简写|
|:-------:|:-------:|:------:|
|导航	|nav	|nav|
|子导航	|subnav	|snav|
|面包屑	|crumb	|crm|
|菜单	|menu	|menu|
|选项卡	|tab	|tab|
|标题区	|head/title	|hd/tt|
|内容区	|body/content	|bd/ct|
|列表	|list	|lst|
|表格	|table	|tb|
|表单	|form	|fm|
|热点	|hot	|hot|
|排行	|top	|top|
|登录	|login	|log|
|标志	|logo	|logo|
|广告	|advertise	|ad|
|搜索	|search	|sch|
|幻灯	|slide	|sld|
|提示	|tips	|tips|
|帮助	|help	|help|
|新闻	|news	|news|
|下载	|download	|dld|
|注册	|regist	|reg|
|投票	|vote	|vote|
|版权	|copyright	|cprt|
|结果	|result	|rst|
|标题	|title	|tt|
|按钮	|button	|btn|
|输入	|input	|ipt|

功能（.f-）

| 语义 | 命名| 简写|
|:-------:|:-------:|:------:|
|浮动清除	|clearboth	|cb|
|向左浮动	|floatleft	|fl|
|向右浮动	|floatright	|fr|
|内联块级	|inlineblock	|ib|
|文本居中	|textaligncenter	|tac|
|文本居右	|textalignright	|tar
|文本居左	|textalignleft|	tal|
|垂直居中	|verticalalignmiddle	|vam|
|溢出隐藏	|overflowhidden|	oh|
|完全消失	|displaynone	|dn|
|字体大小	|fontsize	|fs|
|字体粗细	|fontweight	|fw|



皮肤（.s-）

| 语义 | 命名| 简写|
|:-------:|:-------:|:------:|
|字体颜色	|fontcolor	|fc|
|背景	|background	|bg|
|背景颜色	|backgroundcolor	|bgc|
|背景图片	|backgroundimage	|bgi|
|背景定位	|backgroundposition	|bgp|
|边框颜色	|bordercolor	|bdc|

状态（.z-）

| 语义 | 命名| 简写|
|:-------:|:-------:|:------:|
|选中	|selected	|sel|
|当前	|current	|crt|
|显示	|show|	show|
|隐藏	|hide|	hide|
|打开	|open	|open|
|关闭	|close|	close|
|出错	|error	|err|
|不可用	|disabled	|dis|
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
##### 分类命名：使用单个字母+"-"为前缀
布局（grid）（.g-）；模块（module）（.m-）；元件（unit）（.u-）；功能（function）（.f-）；皮肤（skin）（.s-）；状态（.z-）。
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

##### 使用16进制表示颜色值

除非你需要透明度而使用rgba，否则都使用#f0f0f0这样的表示方法，并尽量缩写。

```
.m-box{color:#f00;background:rgba(0,0,0,0.5);}

```



##### 16进制的颜色属性值使用小写和尽量简写。

十六进制的颜色属性值有些颜色代码是可以缩写的，我们就尽量缩写吧，提高用户体验为主。
不正确：~~color: #ffcc00~~

```正确写法:color: #fc0```

##### 避免使用 !important

##### 私有在前，标准在后
先写带有浏览器私有标志的，后写W3C标准的。

```
.m-box{-webkit-box-shadow:0 0 0 #000;-moz-box-shadow:0 0 0 #000;box-shadow:0 0 0 #000;}
```
## css选择器书写顺序
请综合考虑以下顺序依据：
* 从大到小（以选择器的范围为准）
* 从低到高（以等级上的高低为准）
* 从先到后（以结构上的先后为准）
* 从父到子（以结构上的嵌套为准）  

以下仅为简单示范：




```

/* 从大到小 */
.m-list p{margin:0;padding:0;}
.m-list p.part{margin:1px;padding:1px;}
/* 从低到高 */
.m-logo a{color:#f00;}
.m-logo a:hover{color:#fff;}
/* 从先到后 */
.g-hd{height:60px;}
.g-bd{height:60px;}
.g-ft{height:60px;}
/* 从父到子 */
.m-list{width:300px;}
.m-list .itm{float:left;}

```




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
| 搜索输出：search-output| 搜索结果：search-results |状态：status|按钮：btn|滚动：scroll|
| 标签页：tab| 文章列表：list |提示信息：msg/message |当前的: current|小技巧：tips|
| 皮肤：skin| 充值：pay |活动：activities |推广：promotion|公告：announcement|
| 排行：ranking| 公司简介：companyProfile |公司设备：equipment |公司荣誉：glories|企业文化：culture|
| 企业规模：scaleScale| 营销网络：salesNetwork |组织机构：organization |技术力量：technology|分支机构：branches|
| 企业资质：EnterpriseQualification| 公司实力：strengthStrength |经营理念：operationPrinciple|经理致辞：manager_oratio|发展历程：developmentHistory|
| 工程案例：EngineeringProjects|分类浏览：browseByCategory |应用领域：applicationFields |人力资源：humanResourceHr|领导致辞： leader_oration|
| 客户留言：customerMessage| 客户服务：customerService |您的要求：yourRequirements |销售信息：salesInformation|招商：EnterpriseEstablishing|
| 产品描述：productsDescription| 业务范围：businessScope |联系我们：contactUs |信息发布：Information|返回首页：homepage|
| 产品定购：order| 版权：copyright |友情链接：friendlink |合作伙伴：partner|法律声明：siteinfo-legal|
| 网站信息：siteinfo| 标签：tag |购物车：shop |当前位置：breadcrumb/loc|投票：vote|
| 下载：download| 新闻：news |热点：hot |服务：service|指南：guild|
| 注释：note| 图标: icon|常见问题：FAQ |意见反馈：feedback|下载中心：download|
| 提交：submit| 重写：reset |社区：community |行业：Industry|环境：environment|
