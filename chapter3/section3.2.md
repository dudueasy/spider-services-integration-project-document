# http 服务

### 数据 API
##### GET 'api/search/:keyword'
爬虫数据关键字搜索

查询参数: 
* page: 可选,表示资源条目所在页数, 默认为0
* pageSize: 可选,表示每次请求的条目数, 默认为10


### 用户 API
##### GET 'api'
获取用户列表数据

##### POST 'api/user'
注册用户, 需要提交以下数据, 返回值是 jwttoken
* name: 必须
* username: 必须
* password: 必须

##### POST 'api/user'
登陆用户, 需要提交以下数据, 返回值是 jwttoken 和用户数据
* username: 必须
* password: 必须

##### GET 'api/user/:userId'
获取指定用户的数据

##### GET 'api/user/:userId/subscription'
获取指定用户的订阅信息, **需要登录**.

##### POST 'api/user/:userId/subscription'
为指定用户创建一个订阅, **需要登录**, 需要提交以下数据: 
* type 

    订阅的资源类型.
    type 的值是以下集合中的一个值: ['spider_services']
    
* sourceId 
   对应微服务在系统中的 id

##### GET '/:userId/subContent'
获取用户订阅的微服务数据, **需要登录**

查询参数: 
* page: 可选,表示资源条目所在页数, 默认为0
* pageSize: 可选,表示每次请求的条目数, 默认为10


#### 如何通过登录要求?
由于本项目中使用了 JWT 来实现用户鉴权机制. 
用户需要首先通过 '/api/user/login' 接口获取登陆的 token. 
然后在请求头的 Authentication 字段中赋值, 
字段值以 Bearer 开头, 后接 token 字符串.
```
Authentication: Bearer tokenString 
```

### 微服务 API
##### GET '/api/admin/showservices' 
获取项目中已有的微服务信息

##### POST '/api/admin/spider'
向聚合项目提交一个微服务
* 请求体: 

~~~
 service: {
      name: String, // 服务名, 不能与项目中现有的服务重名
      validationUrl,  // 验证 URL, 爬虫服务需要在这个 URL 被访问时返回正确的数据, 包含了从微服务获取爬虫资源的接口
    } 
~~~

