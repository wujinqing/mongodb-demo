## Aggregation Pipeline Stages

|阶段|描述|语法|示例|
|---|---|---|---|
|$limit|限制记录条数，Limits the number of documents passed to the next stage in the pipeline.|{ $limit: positive integer }|db.article.aggregate({ $limit : 5 });|
|$skip|跳过记录数，Skips over the specified number of documents that pass into the stage and passes the remaining documents to the next stage in the pipeline.|{ $skip: positive integer }|db.article.aggregate({ $skip : 5 });|
|$sort|排序，Sorts all input documents and returns them to the pipeline in sorted order.|{ $sort: { field1: sort order, field2: sort order ... } }|1表示升序or-1表示降序，db.users.aggregate(\[{ $sort : { age : -1, posts: 1 } }]) |
|$match|查询语句，类似SQL里面的WHERE语句,Filters the documents to pass only the documents that match the specified condition(s) to the next pipeline stage.|{ $match: { query } }|db.articles.aggregate(\[ { $match : { author : "dave" } } ]);|
|$project|重塑文档，指定需要哪些字段、不需要哪些字段，或者添加新字段。Passes along the documents with the requested fields to the next stage in the pipeline. The specified fields can be existing fields from the input documents or newly computed fields.|{ $project: { field: 1 or true,  field: 1 or true} }, 格式：field: 1 or true; _id: 0 or false; field: expression; field:0 or false|db.books.aggregate( \[ { $project : { _id: 0, title : 1 , author : 1 } } ] )|
|$unwind|将一个数组按数组里的每个元素拆成一条记录，|{ $unwind: field path }|db.inventory.aggregate( \[ { $unwind : "$sizes" } ] )|
|$group|分组，分组字段必须是_id|{ $group: { _id: expression, field1: { accumulator1 : expression1 }, ... } }|db.sales.aggregate(\[{$group : {_id : { month: { $month: "$date" }, day: { $dayOfMonth: "$date" }, year: { $year: "$date" } },totalPrice: { $sum: { $multiply: \[ "$price", "$quantity" ] } },averageQuantity: { $avg: "$quantity" },count: { $sum: 1 }}}])|



### $unwind

$unwind前：

> {id: 1, tags: \['java', 'python', 'ruby']}

$unwind后：

> {id: 1, tags: 'java'}

> {id: 1, tags: 'python'}

> {id: 1, tags: 'ruby'}

其他字段不变，数组字段拆开。


































































































































































































