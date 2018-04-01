# ThinkPHP框架

ThinkPHP框架的目录，点击可跳转对应模块

* [官方开发手册](#官方开发手册)
* [下载](#工具箱)
* [pstorm快捷键操作](#pstorm快捷键操作)
* [调试](#调试)
* [ 配置虚拟域名简化URL路径](#配置虚拟域名简化URL路径)
* [滤镜](#滤镜)
* [视图操作](#视图操作)
* [编辑操作](#编辑操作)
* [图像调整](#图像调整)
* [加点按](#加点按)
* [图层操作](#图层操作)
* [取消操作](#取消操作)

## 官方开发手册


[官方开发手册地址](https://www.kancloud.cn/manual/thinkphp5_1/353946)


## 下载

## pstorm快捷键操作
Alt + 上下方向键 ：用于切换方法  
ctrl + E:打开最近使用的文件（可搜索）  
ctrl + 左上角波浪线 + 选择color scheme：快速切换主题  
## PHPstorm配置调试工具
php调试使用xdebug
1. 下载xdebug[地址](https://xdebug.org/download.php)  
技巧（如何选择下载对应自己php版本的xdebug）： 


* 进入https://xdebug.org/download.php页面
* 点击Releases --》custom installation instructions进入页面（[或者直接进入](https://xdebug.org/wizard.php)）
* 新建php文件输入phpinfo并进入页面--》查看源码——》复制所有代码
* 粘贴代码到第二步页面的输入框中--》点击输入框下面的Analyse my phpinfo() output得到如下提示



```
Instructions

Download php_xdebug-2.6.0-7.1-vc14.dll
Move the downloaded file to D:\xampp\php\ext
Edit D:\xampp\php\php.ini and add the line
zend_extension = D:\xampp\php\ext\php_xdebug-2.6.0-7.1-vc14.dll
Restart the webserver
```
   
* 安装XDebug按照上面提示下载“php_xdebug-2.6.0-7.1-vc14.dll
”，将其复制到d:\xampp\php\ext\目录中。
* 按照上面提示在php.ini中配置zend_extension = D:\xampp\php\ext\php_xdebug-2.6.0-7.1-vc14.dll
这里复制下面到php.ini中文件底部即可

```

[Xdebug]
zend_extension = D:\xampp\php\ext\php_xdebug-2.6.0-7.1-vc14.dll
xdebug.remote_enable =1
xdebug.remote_handler = "dbgp"
xdebug.remote_host = "localhost"
xdebug.remote_mode = "req"
xdebug.remote_port = 9000
xdebug.idekey = "PHPSTORM"
```
* 重启Apache
需要注意的是xdebug.idekey配置，这里配置的值（当前为“PHPSTORM”）在phpstorm中及浏览器中都需要设置（下面有相关描述），可以改为其它值，但必须保证在这三处设置统一。
* 验证xdebug是否成功：在phpinfo页面中输入xdebug看看能不能找到，找到即p位置成功

 `PHPstorm配置xdebug`
 ***
 
 * 在run ——》edit configuration ——》 php web pag——》+
 ——》选择三个点 然后弹出server界面 输入名称（Xampp Apache自己随便输入）和host（localhost） port （默认80，如果不是就更改为自己的 为这里为89）——》ok——》start url输入/yaohao/public/index.php（调试的页面，自己输入)——》ok 然后打断点即可调试

##  配置虚拟域名简化URL路径







