# [爬虫微服务聚合项目](https://github.com/dudueasy/spider-services-integration-project)


这是一个通过 Express + MongoDB + Elasticsearch 实现的通用爬虫微服务聚合项目, 用户可聚合满足协议的爬虫微服务, 从而获取微服务相关资源数据.

具备鉴权机制, 用户可以订阅系统中的微服务并获得数据.

提供数据搜索功能, 可以实现分页.

### 功能实现 
##### 本地存储
MongoDB & Elasticsearch
##### 用户鉴权
JWT

### 业务交互逻辑
route <-> service <-> model

### 文件结构
项目入口: bin/www

数据库: db/

日志: logs/

路由: routes/

服务层: services/

Model: models/

工具脚本: scripts/

错误类: errors/

配置文件: .env
