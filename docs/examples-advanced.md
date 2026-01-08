# 高级代码示例

## 更新和删除

```js
// 更新
db.table("users")
    .primary("id")
    .update({id: body.id, name: body.name})

// 删除
db.update("delete from users where id = #{id}")
```

## 事务操作

```js
db.transaction(() => {
    db.update("update accounts set balance = balance - #{amount} where id = #{fromId}")
    db.update("update accounts set balance = balance + #{amount} where id = #{toId}")
    return "转账成功"
})
```

## 调用第三方API

```js
import http

var result = http.connect("https://api.example.com/data")
    .header("Authorization", "Bearer " + token)
    .param("page", page)
    .get()
    .getBody()
return result
```

## 文件下载

```js
import response

var data = db.select("select * from users")
var content = JSON.stringify(data)
return response.download(content, "users.json")
```

## 参数校验

```js
assert not_blank(body.name) : 400, "名称不能为空"
assert body.age > 0 : 400, "年龄必须大于0"

return db.table("users").insert(body)
```
