# Gin+Vue 前后端分离项目实战

## 目标
本项目主要用于练习Golang的web开发

相关链接
- [B站视频地址](https://www.bilibili.com/video/av92519169)
- [gin后端](https://github.com/haydenzhourepo/gin-vue-gin-essential)
- [vue前端](https://github.com/haydenzhourepo/gin-vue-gin-essential-vue)
- [站点](http://218.25.35.27:8083/docs/laenix_daily)


## 开始
本项目主要使用到的技术栈有
- Gin - Golang编写的web框架
- gorm - Golang编写的ORM库
- Viper - 适用于Go应用程序的完整配置解决方案
### 应用程序流程
本项目基于前后端分离模式，此部分为后端接口部分。    
- 模型 (Model) 代表数据结构。通常来说，模型类将包含取出、插入、更新数据库资料等这些功能。在这我们使用模型代表对应数据表对象。
- 控制器 (Controller) 是模型、视图以及其他任何处理HTTP请求所必须的资源之间的中介，并生成网页。在这里我们使用控制器来处理对应的HTTP请求并返回对应的code、data、msg。

框架的数据流
1. main.go作为应用入口，初始化一些运行项目所需要的基本资源，配置信息，监听端口。
2. 路由功能检查HTTP请求，根据URL以及method来确定谁(控制层)来处理请求的转发资源。
3. 安全检测：应用程序控制器调用之前，HTTP请求和任一用户提交的数据将被过滤，同时通过中间件确定用户权限。
5. 控制器装载模型、核心库、辅助函数，以及任何处理特定请求所需的其它资源，控制器主要负责处理业务逻辑。
6. 控制器返回前端请求的信息。

### 目录结构
根据上面的应用程序流程设计，项目的目录结构设计如下：

	|——main.go         入口文件
	|——routes.go       路由
	|——config          配置文件
	|——controller      控制器入口
	|——models          数据库模型模块
	|——utils           辅助函数库
	|——common          通用函数库
	|——dto            
	|——middleware      中间件 
	|——response        标准响应方法 
	|——repository            
	|——vo
