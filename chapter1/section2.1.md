# 配置示例
请在项目根目录下创建 .env 文件, 并在文件中定义以下配置项

###  Nodejs 服务器配置 
PORT: 端口

### mongodb 数据库配置
DB_RESOURCE_DB: 微服务数据存储数据库

DB_COLLECTION: 微服务数据使用的数据表

DB_URL: mongodb 连接地址 

### pbkdf2 用户密码加密配置
SALT: pbkdf2 加密 salt

ITERATION_TIMES: 加密轮数

KEY_LEN: 输出的哈希字符长度

DIGEST: 使用的加密算法类型

### JWT 配置
JWT_SECRETKEY: JWT密钥

JWT_TOKEN_EXPIRESIN: JWT token 有效期 

### Elasticsearch 配置
ES_HOST: Elasticsearch 服务器域名

ES_INDEX: Elasticsearch 索引(数据库)名

ES_TYPE: Elasticsearch Type 


### 配置示例 
~~~ 
# config for express server
PORT = 3000

# config for mongodb (聚合服务数据存储)
DB_RESOURCE_DB = 'apolo'
DB_COLLECTION = 'servicecontent'
DB_URL = 'mongodb://localhost:27017'

# pbkdf2
SALT = 'A_RANDOM_STRING'
ITERATION_TIMES = 10000
KEY_LEN = 64
DIGEST = 'sha256'

# JWT
JWT_SECRETKEY  = 'AJWTSecretKey'
JWT_TOKEN_EXPIRESIN = '604800000'

#elasticsearch
ES_HOST = 'localhost:9200'

# ES_INDEX for content from registered spider content service
ES_INDEX = 'spider_service_content_index'

# ES_TYPE for content from registered spider content service
ES_TYPE = 'spider_service_content_type'
~~~


