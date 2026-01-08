# 其他内置模块

## magic模块 - 调用其他接口

```js
import magic

// 调用接口(带code/message)
magic.call("get", "/api/users", {id: 1})

// 调用接口(原始结果)
magic.execute("get", "/api/users", {id: 1})

// 调用函数
magic.invoke("/function/add", {a: 1, b: 2})
```

## env模块 - 获取配置

```js
import env

env.get("server.port")           // 获取配置
env.get("server.port", "8080")   // 带默认值
```

## log模块 - 日志

```js
import log

log.info("消息")
log.info("值: {}", value)
log.debug("调试信息")
log.warn("警告")
log.error("错误")
```

## 请求参数获取

无需import，直接使用变量名：

| 参数类型 | 获取方式 |
|----------|----------|
| URL参数 | 直接变量名 `name` |
| 表单参数 | 直接变量名 `name` |
| Header | `header.token` |
| Body | `body.name` |
| Path参数 | `path.id` 或 `id` |
| Cookie | `cookie.JSESSIONID` |
| Session | `session.userId` |
