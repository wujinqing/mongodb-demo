# Collection Methods 操作集合的方法

* 官方文档：[Collection Methods](https://docs.mongodb.com/master/reference/method/js-collection/)


### db.collection.insert()

> 插入一条记录，如果记录存在则不插入。


### db.collection.save()

> 插入或者修改一条记录，如果记录存在则修改。

### db.collection.findAndModify(document)

> 修改并返回单个document，默认情况下只会返回修改之前的记录，要想返回修改之后的新记录，请设置 **new** 参数为true.

##### 参数说明

|字段|类型|描述|
|---|---|---|
|query|document|可选的，代表查询条件，即使查出多个查询结果，也只会选择其中一个进行修改。|
|sort|document|可选的，对查询到的结果进行排序，类似于SQL中的order by。当查询结果是多条记录时，这个字段决定了修改哪一条记录，会修改排序后的第一条记录, 1表示升序， -1表示降序。示例：sort: {age:-1}|
|remove|boolean|默认值是false代表update操作, 指定是remove还是update字段，要想删除查询到的记录，将该值设置为true。|
|update|document|要修改为的目标document。|
|new|boolean|默认值是false代表返回修改之前的旧记录，要想返回修改之后的新记录设置为true。|
|fields|document|指定哪些要返回的字段。包含某个字段设置为1，fields: { \<field1>: 1, \<field2>: 1, ... }|
|upsert|boolean|只有当update操作时有效，如果没有查询到匹配记录是否会插入新记录，默认值false不插入。|
|arrayFilters|array|可选的，当某些字段是array类型时，通过这个选项来决定array字段中那些值需要修改， 示例: \[ { "x.a": { $gt: 85} }, { "x.b": { $gt: 80 } } ]|
|maxTimeMS|integer|可选的，设置整个findAndModify操作处理的超时时间，单位：毫秒。|

示例
```
db.personalinfo.findAndModify({
	query: {name:'zhangsan'},
	sort: {age:-1},
	remove: false,
	update: {$set: {address:'changchun'}},
	fields:{name:1, address:1},
	new: true
})
```


### db.collection.find(query, projection)

> 根据查询条件及限制条件查询集合数据。

>

##### 参数说明

|字段|类型|描述|
|---|---|---|
|query|document|可选的，查询条件，通过查询器(query operators)指定|
|projection|document|可选的，限制条件，指定需要返回的字段，示例: { field1: \<value>, field2: \<value> ... }, value为1或true表示返回，0或false表示不返回，_id默认是会返回的，想要不返回请指定_id：0。|











