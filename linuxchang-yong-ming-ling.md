# Linux常用命令
* [常用命令]()

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

