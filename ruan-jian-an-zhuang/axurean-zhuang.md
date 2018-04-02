# Axure安装

ThinkPHP框架的目录，点击可跳转对应模块

* [官方开发手册](#官方开发手册)
* [下载](#工具箱)
* [pstorm快捷键操作](#pstorm快捷键操作)
* [调试](#调试)
* [ 配置虚拟域名简化URL路径](#配置虚拟域名简化URL路径)
* [Navicat安装](#Navicat安装)
* [视图操作](#视图操作)
* [编辑操作](#编辑操作)
* [图像调整](#图像调整)
* [加点按](#加点按)
* [图层操作](#图层操作)
* [取消操作](#取消操作)

## 官方开发手册


[官方开发手册地址](https://www.kancloud.cn/manual/thinkphp5_1/353946)


## Navicat安装配置
1. 新建连接

```

********************
连接名: yaohao(随便写)
主机名或 IP 地址: localhost(本地使用localhost)
端口: 3306（xampp的mysql端口为3306也是mysql默认端口）
用户名: root（安装好后默认为root）
保存密码:  （安装好后默认为空）
********************
点击连接测试进行测试

```
2. 默认密码为空必须修改密码
用户——》root@localhost双击——》密码和确认密码位置重新输入自己想修改的——》点击保存即可  完成后重新新建连接

## Windows平台下80端口被System占用解决办法
查看端口：在开始-运行，输入CMD打开命令行界面，输入命令
netstat -ano | findstr "80" （注80是你想要看查看的端口号）  
发现：tasklist /fi "PID eq 4"  
表示这个80端口被系统占用  
找到 HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\services\HTTP    
找到项Start，将其值改为0

## phpstorm命名空间名称记住设置







