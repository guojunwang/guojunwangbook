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
复制一份默认default.conf文件修改为guojunwang.conf
![](/assets/guojunwangconf.png)

默认配置
```conf
server {
        listen       80;
		# 这个表示 网站域名, 可以是二级甚至多级域名  
        server_name  localhost;
		# 表示默认索引文件 
		index index.html index.htm index.php;
		# 该站点对应的网站根目录所在
		root /alidata/www/default;
		# 这里可配置代理
		location ~ .*\.(php|php5)?$
		{
			#fastcgi_pass  unix:/tmp/php-cgi.sock;
			fastcgi_pass  127.0.0.1:9000;
			fastcgi_index index.php;
			include fastcgi.conf;
		}
		location ~ .*\.(gif|jpg|jpeg|png|bmp|swf)$
		{
			expires 30d;
		}
		location ~ .*\.(js|css)?$
		{
			expires 1h;
		}
		#伪静态规则
		include /alidata/server/nginx/conf/rewrite/default.conf;
		access_log  /alidata/log/nginx/access/default.log;
}
```
把打包后的前端网站放到 /alidata/www目录下，我这里放我自己为公司做的一个商户端commercials-bos项目的目录，root 那里修改为/alidata/www/commercials-bos，server_name 我配置一个guojunwang.ytljn.com的域名，伪静态规则根据自己情况修改