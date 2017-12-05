## 常见问题

##网站控制台network中看不到xhr请求

1. 都走jsonp ，因为接口调用五花八门 都走cors的话 配allow origin都配不完 
2. 大厂都会拆域的，可能不能部门负责不同业务，这里面涉及到跨域～你看看network里面js那一栏就知道了