# Linux常用命令
* [常用命令]()
## 查看软件存在的相关目录

whereis mysql
输出例如：/usr/lib64/mysql
移除目录
rm -rf /usr/lib64/mysql

注：find / -name mysql
注：清空相关mysql的所有目录以及文件和其他配置和设置等。如果有，则删除。也必须考虑其他软件不去影响
### 查看Apache服务是否开启
netstat -tnlp
### CentOS7下MySQL的卸载
1：查看MySQL是否安装:

 方式1:



``` linux
[root@localhost usr]# yum list installed mysql*
Loaded plugins: fastestmirror
Loading mirror speeds from cached hostfile
 * base: mirrors.yun-idc.com
 * extras: mirror.neu.edu.cn
 * updates: mirrors.yun-idc.com
Installed Packages
MySQL-client.x86_64   5.6.27-1.el6    installed
MySQL-devel.x86_64    5.6.27-1.el6    installed
MySQL-server.x86_64   5.6.27-1.el6    installed
[root@localhost usr]#

```
方式2( -i  :不区分大小写)：

``` linux

[root@localhost usr]# rpm -qa | grep -i mysql
MySQL-server-5.6.27-1.el6.x86_64
MySQL-client-5.6.27-1.el6.x86_64
MySQL-devel-5.6.27-1.el6.x86_64
[root@localhost usr]# 
```
2：卸载MySQL:
卸载1：
``` linux

[root@localhost usr]# yum remove mysql mysql-server mysql-libs compat-mysql51
[root@localhost usr]# rm -rf /var/lib/mysql
[root@localhost usr]# rm /etc/my.cnf
如果装了mysql-devel(其他一样add command)，卸载为：

[root@Tony_ts_tian init.d]# yum remove mysql mysql-devel mysql-server mysql-libs compat-mysql51
注（例如）:

mysql-5.5.39-1.el6.remi.x86_64
mysql-libs-5.5.39-1.el6.remi.x86_64
compat-mysql51-5.1.54-1.el6.remi.x86_64
mysql-server-5.5.39-1.el6.remi.x86_64

```
``` linux

卸载2{继续，1，2选择一种（此处为介绍）：}:
[root@localhost mysql]# rpm -aq | grep -i mysql
MySQL-server-5.6.27-1.el6.x86_64
MySQL-client-5.6.27-1.el6.x86_64
MySQL-devel-5.6.27-1.el6.x86_64
[root@localhost mysql]# rpm -e MySQL-server-5.6.27-1.el6.x86_64
[root@localhost mysql]# rpm -e MySQL-client-5.6.27-1.el6.x86_64
[root@localhost mysql]# rpm -e MySQL-devel-5.6.27-1.el6.x86_64
[root@localhost rc.d]# cd /var/lib/
[root@localhost lib]# rm -rf mysql/
```

注:删除MySQL数据库目录(关键) ，否则password不更新（默认安装，如果自定义安装路径和链接路径ln -s ……请删除。）
  rm -rf /var/lib/mysql
卸载3：
[root@localhost usr]# whereis mysql
mysql: /usr/lib64/mysql
[root@localhost usr]# rm -rf /usr/lib64/mysql
注：find / -name mysql
注：清空相关mysql的所有目录以及文件和其他配置和设置等。如果有，则删除。也必须考虑其他软件不去影响。
rm -rf /usr/lib/mysql
rm -rf /usr/share/mysql
卸载4：
[root@localhost usr]# rm –rf /usr/my.cnf
[root@localhost usr]# rm -rf /root/.mysql_sercret 
卸载5（自启服务）：
[root@localhost usr]# chkconfig --list | grep -i mysql
[root@localhost usr]# chkconfig --del mysqld
此处删除看自己设置:mysql/mysqld 

### 新建文件
touch 

### 查看进程
所有进程
```linux
ps -aux 
```

查看某个进程或者服务是否存在，命令 ps -aux  ｜ grep xxx 例如mysql

```linux
ps aux |grep mysqld
```

### mysql版本查看

```linux
mysql -V
```
###
(service mysqld stop )

## 复制

cp
## Nginx常用命令

```linux
启动  
./nginx  
  
重启  
./nginx -s reload  
  
关闭  
ps -ef | grep nginx     # 查询nginx主进程号  
从容停止   kill -QUIT 主进程号  
快速停止   kill -TERM 主进程号  
强制停止   kill -9 nginx  
若nginx.conf配置了pid文件路径，如果没有，则在logs目录下  
kill -信号类型 '/usr/local/nginx/logs/nginx.pid'  
  
判断配置文件是否正确  
./nginx -t  

```

