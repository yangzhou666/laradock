# laradock学习文档
    1. fork https://github.com/laradock/laradock 到自己仓库 https://github.com/yangzhou666/laradock  方便自定义配置和维护
    2. Workspace

## 安装
    1. git clone 项目 到本地仓木
    2. cp .env.example .env
    3. 修改镜像（不会翻墙的可能拉不下来镜像）

## 默认已经带有的服务
    1. Workspace
    2. php-fpm
    3. php-worker
    4. Laravel Horizon
    5. Soketi Server
    6. nginx 
    7. OpenResty Server
    8. Blackfire
    9. Apache Server
    10. HHVM
    11. Minio
    12. MySQL
    13. Percona
    14. MSSQL
    15. MariaDB
    16. PostgreSQL
    17. pgbackups PostgreSQL
    18. PostgreSQL PostGis
    19. Neo4j
    20. Nats
    21. MongoDB
    22. RethinkDB
    23. ClickHouse
    24. Redis
    25. Redis Cluster
    26. SSDB
    27. ZooKeeper
    28. Aerospike
    29. Memcached
    30. Beanstalkd
    31. SQS
    32. RabbitMQ
    33. Mercure
    34. Cassandra
    35. Gearman
    36. Beanstalkd Console
    37. Caddy Server
    38. phpMyAdmin
    39. Adminer
    40. PhpPgAdmin
    41. MeiliSearch
    42. ElasticSearch
    43. Logstash
    44. Kibana
    45. Dejavu
    46. Certbot
    ....


## 实际操作中遇到的问题   
    0. docker-compose up workspace nginx mysql php-fpm redis php-worker 会默认安装 docker-in-docker
    1. lnmp 环境 workspace nginx mysql php-fpm redis php-worker 
    2. MYSQL_VERSION=latest  mysql 5.7  更改为指定版本
    3. redis修改密码 REDIS_PASSWORD=123456
    4. 更改php版本 PHP_VERSION=7.4
    5. 开启php需要的扩展  
    6. # composer镜像源
       WORKSPACE_COMPOSER_REPO_PACKAGIST=https://mirrors.aliyun.com/composer/
    7. # nvm镜像源 WORKSPACE_NVM_NODEJS_ORG_MIRROR=https://npmmirror.com/mirrors/node
    8. # npm镜像源  WORKSPACE_NPM_REGISTRY=https://registry.npmmirror.com
    9. #指定容器挂载在什么目录上，如果在laravel根目录安装则是../
       APP_CODE_PATH_HOST=../

    10. # MySQL,Redis等数据持久化保存在主机的什么位置
        DATA_PATH_HOST=~/.laradock/data

    11.  给这个laralock(docker-compose)项目取个名字,这个名字将会作为未来启动的容器的命名前缀,不能与其它laradock重名.默认是`laradock`
    COMPOSE_PROJECT_NAME=general

    12. # 设置时区,会影响到所有运行的容器
       WORKSPACE_TIMEZONE=Asia/Shanghai

## 拉取镜像包失败
    1.error pulling image configuration: download failed after attempts=6: dial tcp 199.59.149.203:443: connect: connection timed out 
