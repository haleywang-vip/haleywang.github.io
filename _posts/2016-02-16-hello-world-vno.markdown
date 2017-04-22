---
layout: post
title: TaffyDB：开源JavaScript数据库
date: 2016-02-16 15:32:24.000000000 +09:00
---

你是否曾经注意到javascript的对象有点像数据库中的记录，你把很多javascript对象包装到一起时就像是你在处理一个数据库中的表，`TaffyDB`是一个Javascript库，它提供了强大的数据库功能，大大改善了你在Javascript中使用数据的方式。`TaffyDB` 是一个免费开源的 JavaScript 库，用于在 Web 上实现一个轻量级的数据访问层，也就是一个简单的数据库。

#### 主要特点：

* 很小，只有10K左右
* 简单，JavaScript的语法
* 快速
* 易于集成到任何Web应用
* 兼容主流的Ajax库，例如：YUI, JQuery, Dojo, Prototype, EXT, etc
* CRUD 接口 (Create, Read, Update, Delete)
* 排序
* 循环
* 高级查询

#### 使用例子

创建一个数据库

```javascript
// Create DB and fill it with records
var friends = TAFFY([
    {"id":1,"gender":"M","first":"John","last":"Smith","city":"Seattle, WA","status":"Active"},
    {"id":2,"gender":"F","first":"Kelly","last":"Ruth","city":"Dallas, TX","status":"Active"},
    {"id":3,"gender":"M","first":"Jeff","last":"Stevenson","city":"Washington, D.C.","status":"Active"},
    {"id":4,"gender":"F","first":"Jennifer","last":"Gill","city":"Seattle, WA","status":"Active"}    
]);
```

使用字段名或者字段的关系过滤

```javascript
// Find all the friends in Seattle
friends({city:"Seattle, WA"});

// Find John Smith, by ID
friends({id:1});

// Find John Smith, by Name
friends({first:"John",last:"Smith"});
```

很容易访问数据

```javascript
// Kelly's record
var kelly = friends({id:2}).first();

// Kelly's last name
var kellyslastname = kelly.last;

// Get an array of record ids
var cities = friends().select("id");

// Get an array of distinct cities
var cities = friends().distinct("city");

// Apply a function to all the male friends
friends({gender:"M"}).each(function (r) {
   alert(r.name + "!");
});
```

github网址：[https://github.com/typicaljoe/taffydb](https://github.com/typicaljoe/taffydb)   
官网：[http://taffydb.com](http://taffydb.com)
