# 环境搭建

github/gitlab环境搭建使用需要配置以下环境
* [注册账户](#注册账户)
* [创建仓库](#创建仓库)
* [git下载](#git下载)
* [git安装](#git安装)
* [git配置](#git配置)
* [链接](#链接)
* [图片](#图片)
* [代码](#代码和语法高亮)
* [表格](#表格)
* [忽略Markdown](#反斜杠-忽略Markdown语法)
* [块引用](#块引用)
* [水平线](#水平线)
* [换行符](#换行符)
* [Youku视频](#Youku视频)
* [脚注](#脚注)
* [内嵌HTML](#内嵌HTML)

## git

* [下载 git Windows 版](https://git-scm.com/download/win)

## git下载安装
1、git下载
2.下载完之后，双击安装
3、选择安装目录
4、选择组件
5、开始菜单目录名设置
6、选择使用命令行环境
7、以下三步默认，直接点击下一步
8、安装完成
9、检验是否安装成功
回到电脑桌面，鼠标右击如果看到有两个git单词则安装成功

## git配置
安装完成后，还需要最后一步设置，在命令行输入：

1、Git安装之后需要进行一些基本信息设置
 查看自己之前是否生成过ssh密钥：
 ``
 cat ~/.ssh/id_rsa.pub
 
 ``
 如果出现一段ssh-rsa开头的，表示已经生成了，可以跳过此步骤
 首先在本地创建ssh key秘钥；
 ssh-keygen -t rsa -C "zy901002@gmail.com"  
来生成密钥。其中生成的文件，id_rsa为自己电脑上的私钥，id_rsa.pub为放在服务器上验证的公钥
（3）将ssh的公钥放到gitlab上面，页面如下所示：


　　a、设置用户名：git  config -- global  user.name  '你再github上注册的用户名';

　　b、设置用户邮箱：git  config -- global  user.email  '注册时候的邮箱';

注意：该配置会在github主页上显示谁提交了该文件

 　　c、配置ok之后，我们用如下命令来看看是否配置成功

　　git config --list

注意：git  config --global 参数，有了这个参数表示你这台机器上所有的git仓库都会使用这个配置，当然你也可以对某个仓库指定不同的用户名和邮箱

## Git初始化及仓库创建和操作


安装Git完成之后，会在桌面创建Git Bash快捷方式，在任意目录下右击鼠标可以找打Git Bash Here的选项。

