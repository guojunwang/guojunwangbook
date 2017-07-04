# 阿里云Nginx配置

* [nginx单站点的配置]()
* [nginx多站点的配置](nginx多站点的配置)

## nginx多站点的配置
首先要找到nginx 配置文件之所在，阿里云上的nginx.conf 文件在 /alidata/server/nginx-1.4.4/conf 中

![](/服务器/images/Nginx位置.png)

然后在conf目录下创建一个vhosts 目录,  这个目录是用来存放不同站点的配置文件的

![](/服务器/images/vhosts.png)

然后在nginx.conf 最后 加入一行include /alidata/server/nginx/conf/vhosts/*.conf;  
这行表示将 vhosts 下面所有的 conf 文件包含进来

![](/服务器/images/Nginx加入配置.png) 

然后，在vhosts 目录下写 你对应站点的 conf 文件了。下面给出一个范例,我以配置guojunwang为例
