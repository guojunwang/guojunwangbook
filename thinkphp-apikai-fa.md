``# ThinkPHP框架

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
## 接口
在application下对应的模块下写对应的接口

例如
```
class Banner
{
    /**
     * 获取指定id的banner信息
     * @url /banner/:id
     * @http GET
     * @id banner的id号
     *
     */
    public function getBanner($id)
    {
        
    }


}
```


## 路由
写完接口后，要动态注册路由：  
路由定义采用\think\Route类的rule方法注册，通常是在应用的路由配置文件application/route.php进行注册，格式是：Route::rule('路由表达式','路由地址','请求类型','路由参数（数组）','变量规则（数组）');  
例如注册如下路由规则：


```
use think\Route;
// 注册路由到index模块的News控制器的read操作
Route::rule('new/:id','index/News/read');

我们访问：
http://serverName/new/5
```


## 验证
1. Validate：独立验证（thinkphp自带验证）

2. Validate验证器(开发都采用验证器方式进行验证，thinkphp自带验证如email邮箱验证等)

3. 自定义验证规则（thinkphp框架没有的自己需要验证，这时候就需要自定义）



```
请求参数调用check()返回后，tp5会返回如下数据：
$data ——》 数据
$field ——》做验证的参数名称
$value——》做验证的参数值
$rule ——》一般用不到


```
## 拦截器
（new Test()）代表拦截器

##常见错误
1. 致命错误: Class 'app\api\validate\Request' not found  
解决方法：没有引入Request库

## 常见快捷键
1. 移除没有使用的库 ctrl+alt+o

## 异常处理方式
1. 抛出异常
2. 捕获异常处理
3. 处理（记录日志）

全局异常处理（aop）


