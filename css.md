# CSS规范

复习css元素属性使用
* [letter-spacing（间距设置）](#letter-spacing（间距设置）)
* [csstext-indent （首行开头缩进）](#text-indent （首行开头缩进）)
* [text-overflow（文本溢出处理）](#text-overflow（文本溢出处理）)
* [font-variant](#font-variant)
* [text-transform](#text-transform)
* [white-space](#white-space)
* [css sprites精灵图](#css sprites精灵图)
* [npm安装](#npm安装)
* [git命令跳路径](#git命令跳路径)
* [nginx配置](#nginx配置)

## letter-spacing（间距设置）

letter-spacing来设置字与字间距_字符间距离，字体间距css样式
![](/assets/css/1_100321083643_1.png)
即对对应div设置css属性样式为letter-spacing:8px;，字间距为8px

## text-indent （首行开头缩进）
通常text-indent缩进属性将对段落首行开头文本文字进行缩进显示
![](/assets/css/1_130210003131_1.png)

## text-overflow（文本溢出处理）
text-overflow参数值和解释：


```css
clip : 　不显示省略标记（...），而是简单的裁切
ellipsis : 　当对象内文本溢出时显示省略标记（...）

```
## text-transform

text-transform 值：
* Capitalize 英文拼音的首字母大写
* Uppercase 英文拼音字母全大写
* Lowercase 英文拼音字母全小写

效果图：
![](/assets/css/1_130204122514_1.png)


##  font-variant
参数： 
* normal : 正常的字体
* small-caps : 让字母变成小型的大写字母字体并缩小字母
效果图：
![](/assets/css/1_130204142255_1.png)

##  white-space

white-space参数：
normal : 　默认处理方式
nowrap : 　强制在同一行内显示所有文本，直到文本结束或者遭遇br标签对象才换行。DIVCSS5推荐使用white-space:nowrap强制不换行。
效果图：
![](/assets/css/1_130211165058_1.png)

## css sprites精灵图