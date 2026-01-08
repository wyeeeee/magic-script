# Java互操作

## 异步调用

```js
// 异步执行，返回Future
var user1 = async db.select("select * from users where id = 1")
var user2 = async db.select("select * from users where id = 2")
// 获取结果
return [user1.get(), user2.get()]

// 异步lambda
var list = []
for(i in range(1, 10)) {
    list.add(async (i) => db.selectOne("select * from users where id = #{i}"))
}
return list.map(item => item.get())
```

## 调用Spring Bean

```js
// 方式1：使用类名
import xx.xxx.UserService
return UserService.selectUserList()

// 方式2：使用Bean名
import "userService" as userService
return userService.selectUserList()
```

## 调用静态方法

```js
import 'org.apache.commons.lang3.StringUtils' as StringUtils
return StringUtils.isBlank("")
```

## 调用magic-api接口

```js
// 导入已定义的接口
import "@get:/api/user/list" as userList
return userList()
```

## 调用magic-api函数

```js
// 导入已定义的函数
import "@/common/encode/md5" as md5
return md5('123456')
```
