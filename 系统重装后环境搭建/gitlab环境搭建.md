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

> 摘要: 我们在日常工作中会遇到公司有个gitlab，还有些自己的一些项目放在github上。这样就导致我们要配置不同的ssh-key对应不同的环境。所以这里配置多个SSH-Key

 
### 第一个配置（公司`Gitlab SSH-Key`配置）

 ***

## git配置
Git安装完成后，还需要进行一些基本信息设置

1. 注册GitLab或者GitHub账号
 * [gitlab官网](https://gitlab.com/users/sign_in)
 * [github官网](https://github.com/)
 
2. 查看自己之前是否在本地生成过ssh密钥，输入以下命令：

 ``` liunx
 cat ~/.ssh/id_rsa.pub
 ```
 如果出现带有: No such file or directory的提示，说明之前没有生成ssh密钥，如出现ssh-rsa开头，说明生成过ssh密钥，可以跳过2步骤
 
3. 如果之前没有生成ssh密钥，本地创建ssh key秘钥，使用命令：
 
 ``` liunx
 ssh-keygen -t rsa -C "maguo@quanyibao.com" -f ~/.ssh/gitlab_rsa
 ## ssh-keygen -t rsa -C "maguo@quanyibao.com"

 ```
 maguo@quanyibao.com邮箱是gitlab的登录邮箱,代码参数含义：-t 指定密钥类型，默认是 rsa ，可以省略。-C 设置注释文字，比如邮箱,-f 指定密钥文件存储文件名
 我这里密码为6个1
 
4. 把公钥文件内容放到服务器中  
 
 步骤2后，成功的话在~/.ssh/目录会生成gitlab_rsa（私钥）文件和gitlab_rsa.pub（公钥文件）。 我们需要将公钥文件gitlab_rsa.pub中的内容粘帖到公司gitlab服务器的SSH-key的配置中。  
  具体位置在Profile Settings------》SSH keys------》Add an SSH Key的Key输入框中
 
5. 添加私钥
 
 ``` liunx
 $ ssh-add ~/.ssh/gitlab_rsa
 ##  ssh-add ~/.ssh/id_rsa
```
如果执行ssh-add时提示"Could not open a connection to your authentication agent"，执行命令：

 ``` liunx
 $ ssh-agent bash

 ```
 然后再运行$ ssh-add ~/.ssh/gitlab_rsa
 

  ```
  #其它相关命令
  ssh-add -l #确私钥列表
  ssh-add -D #清空私钥列表

  ``` 
  
6. 修改配置文件
 在 ~/.ssh 目录下新建一个config文件,命令和手动创建都可以
 
 ```
 # 命令方式
 touch config
 ```

 然后在config文件中添加以下内容配置
 ```
 # gitlab
 Host gitlab.com
    HostName 120.25.195.31
    PreferredAuthentications publickey
    IdentityFile ~/.ssh/gitlab_rsa
 ```

 其中Host对应的名称是一个别名，命名可以随意，用来进行远程连接，当然使用真实的主机名称也是可以的。HostName和IdentityFile就是各自主机名称以及对应的秘钥文件了~
 
7. 测试
 ``` bash
 ssh -T git@gitlab.com
 
 ```
 当你输入以上代码时，会有一段警告代码，如：

  ```bash
 The authenticity of host '120.25.195.31 (120.25.195.31)' can't be    established.
 ECDSA key fingerprint is SHA256:hvr5FcWTXeBO0fIQ8F9GuhAWCAQVT6GtD5Qx3d8SNVE.
 Are you sure you want to continue connecting (yes/no)?
 ```

 这是正常的，你输入 yes 回车既可，如果你创建 SSH key 的时候没有设置密码，就会看到Welcome to GitLab, maguo!的提示，到此ssh就配置好了

 ```
 Welcome to GitLab, maguo!
 ```

 如有其它错误可用以下命令查看具体出错信息，再根据信息来调试：

 ```bash
 # 查看具体出错信息
 ssh -T -v git@gitlab.com
 
  ``` 
  在服务器部署项目的时候，会一直提示服务器密码,这时候需要把gitlab_rsa.pub中的内容粘帖到公司服务器
 
8. 命令下载项目
  
```
git clone git@120.25.195.31:cnepaycd/chedai-m.git
```
如果git clone时候输入gitlab密码不对,并且有以下提示
```
$ git clone git@120.25.195.31:cnepaycd/chedai-m.git
Cloning into 'chedai-m'...
git@120.25.195.31's password:
Permission denied, please try again.
git@120.25.195.31's password:
Permission denied, please try again.
git@120.25.195.31's password:
git@120.25.195.31: Permission denied (publickey,password).
fatal: Could not read from remote repository.
Please make sure you have the correct access rights
and the repository exists.
```
解决方法：删除之前的ssh key，重新创建，创建ssh key秘钥时候`要设置密码`，这里的密码输入设置的密码即可。

###第二个配置（自己项目`GitHub SSH-Key`配置）
***
配置和gitlab一样

1. 创建GitHub账号的ssh key秘钥

  ``` liunx
  ssh-keygen -t rsa -C "1069804753@qq.com" -f ~/.ssh/github_rsa

  ```
2. GitHub添加SSH key的方式如下图所示：

3. 添加私钥

 ``` liunx
 $ ssh-add ~/.ssh/github_rsa
 ```
如果执行ssh-add时提示"Could not open a connection to your authentication agent"，执行命令：

 ``` liunx
 $ ssh-agent bash

 ```
 然后再运行$ ssh-add ~/.ssh/github_rsa
4. 修改配置文件

 然后在config文件中添加以下内容配置
 ```
# github
Host github.com
 HostName github.com
 PreferredAuthentications publickey
 IdentityFile ~/.ssh/github_rsa
 ```

5. 测试

 ``` bash
 ssh -T git@github.com
 
 ```
你输入 yes 回车看到下面提示，到此ssh就配置好了

 ```
 Hi guojunwang! You've successfully authenticated, but GitHub does not provide shell access.

 ```
 最终config文件中两个的配置文件代码为：
 
 ```
 # gitlab
  Host gitlab.com
  HostName 120.25.195.31
  PreferredAuthentications publickey
  IdentityFile ~/.ssh/gitlab-rsa
	
 # github
  Host github.com
  HostName github.com
  PreferredAuthentications publickey
  IdentityFile ~/.ssh/github-rsa
 ```

***
　　a、设置用户名：git  config -- global  user.name  '你再github上注册的用户名';

　　b、设置用户邮箱：git  config -- global  user.email  '注册时候的邮箱';

注意：该配置会在github主页上显示谁提交了该文件

 　　c、配置ok之后，我们用如下命令来看看是否配置成功

　　git config --list

注意：git  config --global 参数，有了这个参数表示你这台机器上所有的git仓库都会使用这个配置，当然你也可以对某个仓库指定不同的用户名和邮箱

## Git初始化及仓库创建和操作

