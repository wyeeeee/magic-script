# 内置模块参考

## http模块 - HTTP请求

```js
import http

http.connect("https://api.example.com")
    .header("Authorization", "Bearer xxx")
    .param("page", 1)           // URL参数
    .body({id: 1, name: "test"}) // 请求体
    .contentType("application/json")
    .post()
    .getBody()
```

方法: `get()` `post()` `put()` `delete()` `patch()`

## request模块 - 请求信息

```js
import request

request.getFile("file")      // 获取上传文件
request.getFiles("files")    // 获取文件列表
request.getValues("names")   // 获取数组参数
request.getClientIP()        // 获取客户端IP
request.get()                // 获取Request对象
```

## response模块 - 响应控制

```js
import response

response.json({success: true})     // JSON响应
response.text("ok")                // 文本响应
response.redirect("/path")         // 重定向
response.download(content, "a.txt") // 文件下载
response.image(bytes, "image/png") // 图片输出
response.addHeader("key", "value") // 添加响应头
response.addCookie("k", "v")       // 添加Cookie
```
