# 常用代码示例

## 基础查询

```js
// 查询列表
return db.select("select * from users")

// 查询单条
return db.selectOne("select * from users where id = #{id}")

// 分页查询
return db.page("select * from users")
```

## 条件查询

```js
var sql = """
select * from users
<where>
    <if test="name != null">
        and name like concat('%', #{name}, '%')
    </if>
    <if test="status != null">
        and status = #{status}
    </if>
</where>
order by created_at desc
"""
return db.page(sql)
```

## 新增数据

```js
// SQL方式
return db.insert("insert into users(name, age) values(#{name}, #{age})")

// 单表API方式
return db.table("users").insert({
    name: body.name,
    age: body.age,
    created_at: now()
})
```
