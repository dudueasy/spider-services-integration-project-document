# 启动项目
在启用 HTTP 服务之前,需要首先启用依赖项: MongoDB 和 Elasticsearch

### 启动 MongoDB 数据库:
~~~
mongod --dbpath db &
~~~

### 启动 Elasticsearch 数据服务: 
1. 请根据 Elasticsearch 所在目录来启用服务.
2. 初次使用项目时, 需要初始化 Elasticsearch 数据库, 如下:

~~~ 
node scripts/es_index_init.js init_es_index
~~~

### 启动 HTTP 服务器
~~~
node bin/www
~~~
