# flask project 

## flask框架
### 为什么要使用框架？

web网站发展至今，特别是服务器端，涉及到的知识、内容，非常广泛。这对程序员的要求会越来越高。如果采用成熟，稳健的框架，那么一些基础的工作，比如，网络操作、数据库访问、会话管理等都可以让框架来处理，那么程序开发人员可以把精力放在具体的业务逻辑上面。使用Web框架开发Web应用程序可以降低开发难度，提高开发效率。

### flask介绍

Flask诞生于2010年，是Armin ronacher（人名）用Python语言基于Werkzeug工具箱编写的轻量级Web开发框架。它主要面向需求简单的小应用。

Flask本身相当于一个内核，其他几乎所有的功能都要用到扩展（邮件扩展Flask-Mail，用户认证Flask-Login），都需要用第三方的扩展库来实现。比如可以用Flask-extension加入ORM、窗体验证工具，文件上传、身份验证等。Flask没有默认使用的数据库，你可以选择MySQL，也可以用NoSQL。其 WSGI 工具箱采用 Werkzeug（路由模块） ，模板引擎则使用 Jinja2 。

Python最出名的框架要数Django，此外还有Flask、Tornado等框架。虽然Flask不是最出名的框架，但是Flask应该算是最灵活的框架之一，这也是Flask受到广大开发者喜爱的原因。

### 官方文档

http://flask.pocoo.org/docs
      
http://docs.jinkan.org/docs/flask/     

### MVC框架

MVC的全拼为Model-View-Controller，最早由TrygveReenskaug在1978年提出，是施乐帕罗奥多研究中心(Xerox PARC)在20世纪80年代为程序语言Smalltalk发明的一种软件设计模式，是为了将传统的输入（input）、处理（processing）、输出（output）任务运用到图形化用户交互模型中而设计的。随着标准输入输出设备的出现，开发人员只需要将精力集中在业务逻辑的分析与实现上。后来被推荐为Oracle旗下Sun公司Java EE平台的设计模式，并且受到越来越多的使用ColdFusion和PHP的开发者的欢迎。现在虽然不再使用原来的分工方式，但是这种分工的思想被沿用下来，广泛应用于软件工程中，是一种典型并且应用广泛的软件架构模式。后来，MVC的思想被应用在了Ｗeb开发方面，被称为Ｗeb MVC框架。

MVC框架的核心思想是：解耦，让不同的代码块之间降低耦合，增强代码的可扩展性和可移植性，实现向后兼容。

当前主流的开发语言如Java、PHP、Python中都有MVC框架。

Ｗeb MVC各部分的功能
M：全拼为Model，主要封装对数据库层的访问，对数据库中的数据进行增、删、改、查操作。

V：全拼为View，用于封装结果，生成页面展示的html内容。

C：全拼为Controller，用于接收请求，处理业务逻辑，与Model和View交互，返回结果

### MVT框架

Models: 封装数据操作,数据库的表和字段的定义

Template: 模板, 用来展示数据

Views: 视图函数, 相当于controller, 接收请求，协调模型和模板



##  Q&A
### flask 连接mysql数据库报错:pymysql.err.OperationalError: (1045....

数据库名与用户名一致

### 静态资源加载不进来

### jinja2.exceptions.UndefinedError: 'current_user' is undefined

jinja2模板中的变量没有定义

### 无限循环重定向


### 登录后挑战不到首页

ajax:  common_ops.alert( res.msg,callback );


### 删除的用户为什么还能登录？

