---
title: mongodb学习笔记
layout: post
category : mongodb
tagline: "Supporting tagline"
tags : [mongodb]
---
### **合集操作**
-  显示集合(等同于关系数据库里的表):
	`show collections`
- 创建合集
 	`db.createCollection('collname')`
- 更改合集名称:
	`db.collname.renameCollection('NewCollName')
- 删除合集:	
	`db.collname.drop()`

### **创建、删除、更新文档**
- 创建、插入文档
	`db.test.insert('doc')` (插入将转换成BSON格式，最大不能超过4M)
- 删除文档:
	`db.test.remove()`	#删除test集合所有的文档，但不会删除集合本身，原有索引也会保留。当给定参数时候，只有符合条件的文档才会被删除，删除数据是永久的不能恢复和撤销
- 更新文档
	`db.test.update('旧文档','新文档')` 更新文档
**修改器操作**
- "$set":用来指定一个键的值，如果这个键不存在则创建它
	```shell
    	db.test.update({},{"$set":{"title":'ccer'}})
	```
- "$unset":删除指定一个键
	```
    	db.dbname.update({},{$unset:{"title":""}})
    ```
- "$inc":用来增加已有的键值（如果不存在则创建,只能使用整数、长整数、双精度浮点数)
	```mongodb
    	db.test.update({'username':'er'},{$inc:{'source':'123'})
	```
- "$push":数组修改器:
	```
    	db.blog.posts.update({'title':'test'},{$push:{'comments':{'name':'er','content':'nice post.'}}})

	```

### **查询**
- 普通查询:
```
	db.test.find()
```
- 条件查询:
	- $lt (小于)
    ```
     	db.user.find('age':{$lt:33}) #查询年龄小于33的人
    ```
    - $lte (小于等于)
       	```
        	db.user.find('age':{$lt:33}) #查询年龄小于33的人
       	```
    - $gt (大于)
    ```languages
		db.user.find('age':{$gt:33}) #查找年龄大于33的人
    ```
    - $gte (大于等于)