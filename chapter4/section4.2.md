# 爬虫微服务接口约定 

### 微服务单条数据的数据结构
 符合该聚合项目协议的微服务提供的单条数据结构应该如下:
~~~
// Mongoose Schema
  resourceId: {type: String, required: true },
  title: {type: String, required: true},
  contentType: String,
  content: {
    html: {type: Mixed},
    text: {type: Mixed}}
  },
  createdAt: String,
  originalCreatedAt: String,
  tags: [{name: String, value: String, score: Number}],
~~~


### 爬虫微服务验证接口
通过调用该接口, 爬虫微服务应该返回符合规范的内容,
以表示该爬虫能够兼容本聚合项目的协议.

聚合服务将会通过这个接口返回的 config 字段中的 singleContent 和 contentList
中的参数来获得接口 url 和相关查询参数
~~~
  PATH: 由注册爬虫的服务决定
  METHOD: GET
  CONTENT-TYPE: application/json

  SUCCESS-RESPONSE-BODY:
  {
    code:0,
    protocol:{
      version: String, 
      name: 'FULL_FLEDGED_NET_SPIDER_PROTOCOL', 
    },
    config:{
      singleContent:{
        url: String,
        frequency: Number
      }, 
      contentList:{
        url: String,
        frequency: Number,
        pageSize: Number
      } 
    } 
  } 

  ERROR-RESPONSE-BODY:
  {
    code: errorCode,
    msg: errorMessage 
  }
~~~ 
### 获取爬虫微服务数据的接口
~~~
  PATH: 由验证接口返回
  METHOD: GET
  CONTENT-TYPE: application/json
  REQUEST-_PARAMS: {
    pageSize: Number, 
    latestId: String  // latestID 用来表示最后一次爬取时的资源 id, 避免爬取重复资源.
  }

  SUCCESS-RESPONSE-BODY:
  {
    code:0, 
    data:{ 
      contentList: [] 
    },
  } 
~~~

