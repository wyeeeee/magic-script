# 数据库高级操作

## 事务

```js
// 自动事务
var result = db.transaction(() => {
    db.update("insert into t(name) values('a')")
    db.update("insert into t(name) values('b')")
    return "success"
})

// 手动事务
var tx = db.transaction()
try {
    db.update("...")
    tx.commit()
} catch(e) {
    tx.rollback()
}
```

## 单表CRUD (db.table)

```js
// 插入
db.table("users").insert({name: "张三", age: 20})

// 批量插入
db.table("users").batchInsert([
    {name: "张三", age: 20},
    {name: "李四", age: 25}
])

// 更新
db.table("users").primary("id").update({id: 1, name: "王五"})

// 保存(自动判断insert/update)
db.table("users").primary("id").save({name: "新用户"})

// 查询
db.table("users").select()
db.table("users").page()
```

## 单表高级选项

```js
// 逻辑删除：delete转update，select自动拼接条件
db.table("users").logic().delete()

// 不过滤空值
db.table("users").withBlank().insert({name: "", age: 20})

// 指定查询列
db.table("users").column("id").column("name").select()
```

## 条件查询

```js
db.table("users")
    .where()
    .eq("status", 1)      // =
    .ne("deleted", 1)     // <>
    .like("name", "%张%") // like
    .gt("age", 18)        // >
    .in("role", [1,2,3])  // in
    .select()
```

条件方法: `eq` `ne` `lt` `gt` `lte` `gte` `in` `notIn` `like` `notLike`

## 其他功能

```js
// 数据源切换
db.slave.select("...")

// SQL缓存
db.cache("user_cache", 3600000).select("...")
db.deleteCache("user_cache")

// 列名转换
db.camel().select(...)  // 驼峰
db.lower().select(...)  // 小写
```
