# koa笔记

### 1、引入koa
##### koa是一个构造函数,还需要创建实例
```
const Koa = require("koa");
const app = new Koa();
```


### 2、引入router模块
##### router模块解决请求路径的不同响应不同的页面
##### koa-router是一个函数，这里引入koa-router并执行它

```
const router = require("koa-router")()
```

### 3、使用use引入中间件。
##### 在Express框架中，使用应用程序实例对象的use方法来调用一个中间件。在请求和响应间运行。一个中间件是一个用于处理客户端请求的函数。调用方式：

```
app.use([path],function)
```
##### 在use方法中，使用两个参数，其中path参数为可选参数，function参数为必须指定参数。path参数值为一个字符串，用于指定何种路径应用中间件，默认参数值为“/”。function参数值为一个函数，用于指定我们所要调用的中间件函数。

### 4、在koa项目中引入router
```
app.use(router.routes())
```

### 5、引入koa-static
##### 作用：前端静态文件、图片等静态资源处理模块。配置静态资源目录后，将不会出现静态资源not found错误。
```
const static = require("koa-static");
```
##### 使用第三方模块创建一个静态文件目录。__dirname可以直接获取到当前项目的绝对路径
```
app.use(static(__dirname + "/public"));
```
