# 项目选择Flink的原因
````
  1.Flink从1.10版本集成了Blink（阿里）加持，（Hbase,Phoenix,Hive,Sql等支持力度正在增强）并且升级到java 1.11本项目暂时按照1.8
  2.集成TensorFlow和Paddelpaddel比较容易（Flask以RestFull方式，分布式的研究中），虽然有alink之类的ML目前暂时不研究
  3.集成批流一体的，简化代码复杂度，减少代码维护，大型的批处理正在研究，先研究在线，然后研究离线，spark也很强大，并且生态很完善，
    本项目处于新开发因此未研究替换Spark的好坏，也是处于学习的目的
  4.集成Nacos等优化工程的配置管理，nacos采用1.12版本以上支持Mysql8.0
# 框架搭建环境
````
- 编译器：IDEA 2019.1
- Maven：3.6.0
- JDK：1.8.0_191
- 系统：Win 10
````
# 数据库
## MySQL 8.0
```
- 版本：mysql-installer-community-8.0.15.0.msi
- 账户名:root
- 密码：jianghongyu
- 端口：3306
- 数据库名：jhy_portrait
- 数据库表结构：见flink-user-portrait-main项目根目录/dbfile/mysql/
```

## MongoDB
```
- 版本：mongodb-linux-x86_64-4.0.9
- 可视化工具Robomongo：robo3t-1.3.1 Windows版
```

# 大数据组件
```
- Hadoop：hadoop-2.8.5.tar.gz
- HBase：hbase-1.4.9.tar.gz
- ZK：zookeeper-3.4.14.tar.gz
- Flink：
- Kafka：kafka_2.11-2.2.0.tgz
- Flume：apache-flume-1.9.0-bin.tar.gz
```

# 前端组件
```
- Vue.js
- Node.js
- 
```

# 其他软件
````
- Git客户端：Git-2.21.0 for Windows
- Navicat：Navicat 12 for MySQL Windows版
- Postman
- 
````


# 开发框架
- Spring Boot 2.0（2.0.4、2.0.3、2.0.2均涉及）
```
1. 新增特性
2. 代码重构
3. 配置变更
```
```
http://spring.io
https://github.com/spring-projects/spring-boot/wiki可查看发布日志
https://github.com/spring-projects/spring-boot/wiki/Spring-Boot-2.0-Configuration-Changelog查看配置的改变
```

# flink-userportrait-main组件结构及[端口]
- portrait-analy-service    [无]
```
[Flink画像分析模块]
```
- portrait-common           [无]
```
[提取的公共项目]
含用户行为及日志结构定义、配置文件读取等等。
```
- portrait-register-center  [8761]
```
[注册中心模块]
```
- portrait-info-in-service  [8762]
```
[数据收集服务]
```
- portrait-search-info      [8763]
```
[接口查询服务]
```
- portrait-view-service     [8764]
```
[前端查询服务]
前端查询服务调用接口查询服务获取数据。
```
- dbfile 
```
数据库相关文件、脚本等。
```
前端查询服务模块调用接口查询服务模块，获取数据后与vuejs项目对接，vuejs通过http方式请求前端查询接口。


# flink-userportrait-main启动顺序
项目源码使用模块编程，client端注册到了eureka服务端，所以启动项目应该也要启动eureka的服务端。
1. 安装portrait-common
2. 启动portrait-register-center
3. 启动portrait-info-in-service
4. 启动portrait-search-info
5. 启动portrait-view-service
6. portrait-analy-service做画像分析

# 测试
1. 注册中心测试http://localhost:8761
2. 数据收集测试

    **1）**

    **2）**

3. 


