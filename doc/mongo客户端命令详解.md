## mongo客户端命令详解

### show dbs: 显示所有数据库

> show dbs

![show dbs](img/cmd/show_dbs.png)


### use 数据库名: 切换数据库

> use local

![show dbs](img/cmd/use_db.png)

### db: 查看当前使用的数据库

> db

![show dbs](img/cmd/db.png)

### show collections 查看当前所在数据库的所有集合

> show collections;


### db.hello.insert(): 向集合hello中插入数据

> db.hello.insert({name:'zhang san', age:20});

![insert](img/cmd/insert.png)

![insert](img/cmd/insert2.png)

> 无模式插入

![insert](img/cmd/insert4.png)

![insert](img/cmd/insert3.png)


### db.hello.find(): 查找集合hello中的所有数据

> db.hello.find();

![find](img/cmd/find.png)

> db.hello.find().limit(2);

![find limit](img/cmd/find_limit.png)

> db.hello.find;

![find limit](img/cmd/find2.png)

### db.hello.remove({}): 删除集合hello中的所有数据

> db.hello.remove({});

![remove](img/cmd/remove.png)

### db.personalinfo.update(查询条件,新数据): 更新数据

> db.personalinfo.update({name:'zhangsan', info1},{});

![remove](img/cmd/update.png)






























































