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
2. 数据类型错误：variable type error： array
需要把数组转json
## 常见快捷键
1. 移除没有使用的库 ctrl+alt+o

## 异常处理方式

注意：  
1. 在rest服务中null也是异常
___

异常分类：  
* . 由于用户行为导致的异常（没有通过验证器、没有查询到结果）  
这种类型不需要记录日志，需要向用户返回具体信息

* . 抛出异常：
服务器自身异常:如代码错误，调用第三方外部接口  
通常记录日志，不需要向用户返回具体原因


异常代码实例：
```php
<?php
/**
 * desc:.
 * User: 果郡王
 * Date: 2018-04-03
 * Time: 17:41
 */

namespace app\api\model;


class Banner
{
    public static function getBannerById($id)
    {
        try{
            3/0;
        }catch (Exception $exception){

            throw  $exception;
        }
        //TODO 根据banner id获取banner信息
        return "这是banner获取的信息";

    }

}
```

控制器调用
```php
<?php
/**
 * desc: Banner接口
 * User: 果郡王
 * Date: 2018-04-03
 * Time: 11:12
 * ——————————————————快捷键——————————————
 *  pubf(prif、prof私有、保护前缀一样) 生成 public function (){}
 *  pubsf (prisf、prosf私有、保护前缀一样) 生成 public static function () {}
 *
 * ——————————————————开发笔记—————————————
 * 1 .方法function前面没有写public 默认为public
 */

namespace app\api\controller\v1;
//因为banner两个一样开发工具感应引入有问题，需要手动写一个，并且给别名区分
use app\api\model\Banner as BannerModel;

class Banner
{
    /**
     * 获取指定banner的信息
     * @url /banner/:id
     * @http GET
     * @id banner的id号
     */
    public function getBanner($id)
    {
        //(new IDMustBePostiveInt())->goCheck();//进行验证
        //id获取到后并且校验符合要求后就需要进行业务处理
        //这时候就需要放到单独的业务层，建立controller同级的model文件夹，新建与当前文件名相同的类，这样看着结构比较清晰
        $banner = BannerModel::getBannerById($id);
        return $banner;

    }

}
```
请求地址：


```
http://z.com/banner/1
```



2. 捕获异常处理
3. 处理（记录日志，不用tp5自带记录日志，自定义只记录服务器异常日志）
tp5框架默认会记录错误日志，但是它会记录所有的日志，包括用户行为异常和服务器异常日志和一些无用的日志，而且还会占大量空间。所以关闭掉tp5默认的记录日志，自定义
4. 全局异常处理类（aop）如果不处理就是状态码，还有就是验证后的返回格式不正确， api这样不能这样，所有需要用全局异常处理

5. 自定义异常
要启用自定义错误处理页面，首先得把config.php文件中的exception_handle设置为重写Handle的render方法的类的命名空间地址，默认为空，如我这里写的如下



```
   // 异常处理handle类 留空使用 \think\exception\Handle
    'exception_handle'       => 'app\lib\exception\ExceptionHandler',
```


## 上线需要修改的
1. 调试模式修改为false

## 调试
按debug后复制XDEBUG_SESSION_START=19579类似的代码，拷贝到接口后面，打断点后，请求就会进入断点，如果报错就重新获取
 
 ## 数据库
 
 ---
 
### 配置

 在database.php配置数据库信息


```
// 服务器地址,本机电脑127.0.01，外网：外网ip地址
'hostname'        => '127.0.0.1',
// 数据库名 我是hzyaohao
'database'        => 'hzyaohao',
// 用户名
'username'        => 'root',
// 密码
'password'        => '123456',
// 端口
'hostport'        => '3306',
```
### tp5查询数据库三种方式   
无论使用哪种方式最终都会转化成原生sql语句查询
 * 使用原生sql语句查询数据库
 * 查询构造器db
 * 使用模型以及关联模型查询数据库（用这种方式）  
 
性能分析
* 模型是框架自带，性能有点损坏，稍差，官方推荐使用（推荐用着这种方式优先）
* 中小型项目速度慢，多半是sql语句问题

### 不推荐使用原生sql语句查询数据库原因


* 没有查询构造器怎么简洁和方便
*  查询构造器封装了统一的不同数据库操作语法（支持mysql、sql server等其他数据库）

### 开启sql日志记录

开启原因：  
*  调试sql
*  日志记录查询时间、方便自己优化，性能调优、排查错误

开启方式：  
* fetchSql()  

配置：修改config.php文件日志记录方式type为File，

 ```
 'log'  => [
    // 日志记录方式，内置 file socket 支持扩展
    'type'  => 'File',
    // 日志保存目录
    'path'  => LOG_PATH,
    // 日志记录级别
    'level' => [],
],
 ```


使用方式
```
$result = Db::table("banner_item")
    ->fetchSql()
    ->where("banner_id",'=',$id)->select();
```
缺点  
日志信息显示不够详情，获取不到自己想要的信息

* tp5自动记录日志（生产线上环境最好不需要开启，提示性能）

 打款自动记录日志需要进行参数配置    
第一步：修改database.php文件数据库调试模式debug为true

 ```
 // 数据库调试模式
 'debug'           => true,
 ```
  
 第二步：修改config.php文件应用调试模式app_debug为true

 ```
  // 应用调试模式 默认为true
 'app_debug'              => true,
  ```

 第三步：修改config.php文件日志记录方式type为File  

 ```
 'log'  => [
    // 日志记录方式，内置 file socket 支持扩展
    'type'  => 'File',
    // 日志保存目录
    'path'  => LOG_PATH,
    // 日志记录级别
    'level' => [],
],
 ```
第四步：因为不需要自动保存日志，所以设置为type设置为test，关闭自动保存日志，但需要开启sql日志记录，就需要手动初始化日志配置  


在index.php文件中写，因为每次请求都会进入index文件进行初始化sql日志
```
\think\Log::init([
    'type'  =>  'File',
    'path'  =>  LOG_PATH,
    'level' => ['sql']
]);

```
测试接口 http://z.com/api/v1/banner/1

日志输出：/runtime/log
```
[ 2018-04-04T13:59:02+08:00 ] 127.0.0.1 127.0.0.1 GET /api/v1/banner/1?XDEBUG_SESSION_START=15507
[ log ] z.com/api/v1/banner/1?XDEBUG_SESSION_START=15507 [运行时间：0.484410s][吞吐率：2.06req/s] [内存消耗：2,085.18kb] [文件加载：37]
[ sql ] [ DB ] CONNECT:[ UseTime:0.001551s ] mysql:dbname=hzyaohao;host=127.0.0.1;port=3306;charset=utf8
[ sql ] [ SQL ] select * from banner_item where banner_id='1' [ RunTime:0.001124s ]
[ sql ] [ SQL ] SHOW COLUMNS FROM `banner_item` [ RunTime:0.012296s ]
[ sql ] [ SQL ] SELECT * FROM `banner_item` WHERE  `banner_id` = 1 [ RunTime:0.000875s ]

---------------------------------------------------------------
```

## orm
对象关系映射：操作的是对象，对象与对象间的关系  

表与表之间的关系`不再是数据结构与数据结构之间外键的关系了`，而是对象与对象之间的作用关系（符合面向对象）

对象关系模型：orm框架，如java中的hibernate

模型：这里是指tp5中的m模型：包含数据库查询、包含相关业务逻辑操作  
简单理解：一个表是一个对象，模型可能对应多个表、多个对象
模型分层：模型可以在model、server中
## 模型

模型是orm的一个对象  
优势:
### 模型定义

定义一个User模型类：
```
namespace app\index\model;

use think\Model;

class User extends Model
{
}
```

默认数据表名自动识别为类名，如上面代码的User对应数据库中user表。如果需要指定表名，可以设置当前模型对应的完整数据表名称，如下代码



```
namespace app\index\model;

class User extends \think\Model
{
    // 设置当前模型对应的完整数据表名称
    protected $table = 'think_user';
  }
```


默认为主键为自动识别，如果需要指定，可以设置属性：


```
namespace app\index\model;

use think\Model;

class User extends Model
{
    protected $pk = 'uid';
}
```
### 调用模型  

模型类可以使用静态调用或者实例化调用两种方式

模型查询（数据库查询）：推荐使用静态调用

```
// 静态调用
$user = User::get(1);
$user->name = 'thinkphp';
$user->save();

// 实例化模型
$user = new User;
$user->name= 'thinkphp';
$user->save();

// 使用 Loader 类实例化（单例）
$user = Loader::model('User');

// 或者使用助手函数`model`
$user = model('User');
$user->name= 'thinkphp';
$user->save();
```
### 模型关联
 定义模型关联

```
 //定义Banner与BannerItem关联
  public function items()
  {
      //this指代Banner  hasMany()是模型关联自带函数 参考https://www.kancloud.cn/manual/thinkphp5/142358
      //语义化理解：Banner模型包含多个BannerItem模型 通过banner_item表中的banner_id和banner表中id进行关联
      return $this->hasMany("BannerItem","banner_id","id");
  }

```
模型关联使用


## 隐藏字段
 
 ### 隐藏原因
 * 简洁：返回客户端的数据有些用不到
 * 安全性考虑：有些自带不需要返回
 
` 模型自带隐藏`

在模型类中 声明 protected $hidden=["id"];即可隐藏

```
<?php
/**
 * desc:.
 * User: 果郡王
 * Date: 2018-04-03
 * Time: 17:41
 */

namespace app\api\model;


use think\Db;
use think\Model;

class Banner extends Model
{
    protected $hidden=["id"];

    //定义Banner与BannerItem关联
    public function items()
    {
        //this指代Banner  hasMany()是模型关联自带函数 参考https://www.kancloud.cn/manual/thinkphp5/142358
        //语义化理解：Banner模型包含多个BannerItem模型 通过banner_item表中的banner_id和banner表中id进行关联
        // BannerItem关联模型名 banner_id关联模型外键 id当前模型的主键
        return $this->hasMany("BannerItem","banner_id","id");
    }


    public static function getBannerById($id)
    {

        //原生sql查询数据库
       // $result = Db::query('select * from banner_item where banner_id=?',[$id]);

        // 查询构造器查询数据库
        // db代表数据库类，需要数据库库操作必须用Db，select()前面都是链式方法，select()这些才是真正查询的方法
        $result = Db::table("banner_item")->where("banner_id",'=',$id)->select();





        return $result;

    }

}

```
## url路径处理

相关注意事项

1. 数据库url配置成相对路径，方便测试环境和线上环境更改
2. 拼接
3. 判断是本地图片还是网络第三方图片 可以在数据库设置from字段来自哪里判断

需要配置文件和读取器




