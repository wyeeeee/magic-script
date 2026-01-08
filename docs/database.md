# 数据库操作参考

db模块默认引入，无需import。

## 查询方法

| 方法 | 返回值 | 说明 |
|------|--------|------|
| `db.select(sql)` | `List<Map>` | 查询列表 |
| `db.selectOne(sql)` | `Map` | 查询单条 |
| `db.selectInt(sql)` | `int` | 查询整数 |
| `db.selectValue(sql)` | `Object` | 查询单值 |
| `db.page(sql)` | `Object` | 分页查询 |

## 增删改方法

| 方法 | 返回值 | 说明 |
|------|--------|------|
| `db.update(sql)` | `int` | 执行增删改 |
| `db.insert(sql)` | `Object` | 插入返回主键 |
| `db.batchUpdate(sql, args)` | `int` | 批量执行 |

## SQL参数

```js
// #{} 预编译参数(防注入，推荐)
db.select("select * from t where id = #{id}")

// ${} 字符串拼接(慎用)
db.select("select * from t order by ${orderBy}")

// ?{} 动态SQL
db.select("select * from t ?{name, where name = #{name}}")
```

## MyBatis动态SQL

```js
var sql = """
select * from users
<where>
    <if test="name != null">
        and name = #{name}
    </if>
    <if test="status != null">
        and status = #{status}
    </if>
</where>
"""
return db.select(sql)
```

支持标签: `<if>` `<else>` `<elseif>` `<where>` `<set>` `<foreach>` `<trim>`
