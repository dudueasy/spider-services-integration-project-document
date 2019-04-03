# 聚合服务接口约定
### 注册服务接口
~~~ 
PATH: /api/admin/spider 
METHOD: POST 
CONTENT-TYPE: application/json 
REQUEST-BODY:{
service: {
  name: String, // 服务名, 不能与项目中现有的服务重名
  validationUrl,  // 验证 URL, 爬虫服务需要在这个 URL 被访问时返回正确的数据, 包含了从微服务获取爬虫资源的接口
         } 
} 

SUCCESS-RESPONSE-BODY:
{
  code:0, 
} 

ERROR-RESPONSE-BODY:
{
  code: errorCode,
  msg: errorMessage 
}
~~~
