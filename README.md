## MongoDB学习笔记

### 安装MongoDB
> 版本：mongodb-osx-x86_64-3.4.9.tgz

> 官网地址：https://www.mongodb.com/download-center#community


##### 1.下载MongoDB

![下载MongoDB](doc/img/p2.png)


##### 2.解压并重命名

![解压并重命名](doc/img/p3.png)

##### 3.配置环境变量

![配置环境变量](doc/img/p1.png)

##### 4.启动MongoDB服务端
![启动MongoDB服务端](doc/img/p4.png)

> 启动MongoDB服务端：mongod --dbpath=/Users/wujinqing/data/db 或者mongod

> 参数说明：

> --dbpath=/Users/wujinqing/data/db 指定数据库文件存放的路径，

> 默认保存在根目录下的/data/db下


##### 5.启动MongoDB客户端
![启动MongoDB客户端](doc/img/p5.png)

> 启动MongoDB客户端: mongo默认连接到本地的27017端口




### bin目录下的脚本
|命令|中文说明|英文说明|
|---|---|---|
|mongod|数据库服务器|The database server.|
|mongos|分区、分片路由|Sharding router|
|mongo|连接数据库的客户端|The database shell (uses interactive javascript).|
|mongodump|创建一个二进制的数据库内容的dump文件|Create a binary dump of the contents of a database.|
|mongorestore|重新存储由mongodump命令导出的数据|Restore data from the output created by mongodump.|
|mongoexport|将collection中的数据导出到json或者CSV|Export the contents of a collection to JSON or CSV.|
|mongoimport|将JSON, CSV or TSV格式的数据导入|Import data from JSON, CSV or TSV.|
|mongofiles|从GridFS中添加、获取或者删除文件|Put, get and delete files from GridFS.|
|mongostat|显示一个正在运行的mongod/mongos的状态|Show the status of a running mongod/mongos.|
|bsondump|将BSON格式的文件转换成人类可读的格式|Convert BSON files into human-readable formats.|
|mongoreplay|Traffic capture and replay tool|Traffic capture and replay tool.|
|mongotop|追踪读取和写入数据花费的时间|Track time spent reading and writing data.|



























