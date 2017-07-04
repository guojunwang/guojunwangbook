# 阿里云Nginx配置

* [nginx单站点的配置]()
* [nginx多站点的配置](nginx多站点的配置)

## nginx多站点的配置
首先要找到nginx 配置文件之所在，阿里云上的nginx.conf 文件在 /alidata/server/nginx-1.4.4/conf 中
![](/服务器/images/阿里云Nginx位置.png)

然后在conf目录下创建一个vhosts 目录,  这个目录是用来存放不同站点的配置文件的
![](/服务器/images/vhosts.png)