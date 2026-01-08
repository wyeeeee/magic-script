# Lambda与Linq操作

## Lambda表达式

```js
// 基本语法
var fn = () => expr
var fn = (a, b) => { return a + b }
```

## 集合Lambda方法

```js
var list = [{sex: 0, name: '小明'}, {sex: 1, name: '小花'}]

// map - 映射转换
list.map(item => {
    sex: item.sex == 0 ? '男' : '女',
    name: item.name
})

// filter - 过滤
list.filter(item => item.sex == 0)

// group - 分组
list.group(item => item.sex)
list.group(item => item.sex, items => items.size())

// join - 关联
list1.join(list2,
    (left, right) => left.id == right.id,
    (left, right) => {id: left.id, name: right.name}
)
```

## Linq语法

```sql
select
    t.field [alias]
from expr t
[left join expr t1 on condition]
[where condition]
[group by t.field]
[having condition]
[order by t.field [asc|desc]]
[limit expr [offset expr]]
```

## Linq示例

```js
// 基础查询
return select * from list t where t.status = 1

// 关联查询
return select t.name, t1.score
    from users t
    left join scores t1 on t.id = t1.user_id
    where t.age > 18
    order by t1.score desc

// 分组聚合
return select t.dept, count(t.id) total
    from users t
    group by t.dept
    having count(t.id) > 5

// 分页
return select * from list t limit 10 offset 20
```
