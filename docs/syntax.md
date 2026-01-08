# Magic-Script 语法参考

## 关键字

| 关键字 | 说明 | 示例 |
|--------|------|------|
| `var` | 定义变量 | `var x = 1` |
| `if/else` | 条件判断 | `if(x) {...} else {...}` |
| `for/in` | 循环 | `for(item in list) {...}` |
| `while` | while循环 | `while(cond) {...}` |
| `return` | 返回值 | `return data` |
| `exit` | 终止并返回 | `exit 400, '错误', null` |
| `assert` | 断言 | `assert x==1 : 400, '错误'` |
| `import` | 导入 | `import http` |
| `new` | 创建对象 | `new Date()` |
| `async` | 异步调用 | `async db.select(...)` |
| `try/catch/finally` | 异常处理 | `try {...} catch(e) {...}` |

## 数据类型

| 类型 | 写法 |
|------|------|
| int/long | `123` / `123L` |
| float/double | `123f` / `123d` |
| BigDecimal | `123m` |
| boolean | `true` / `false` |
| string | `'hello'` / `"hello"` / `"""多行"""` |
| Pattern | `/\d+/g` |
| list | `[1, 2, 3]` |
| map | `{key: value}` |
| lambda | `()=>expr` / `(a,b)=>{...}` |

## 运算符

```
算术: + - * / % ++ -- += -= *= /=
比较: < <= > >= == != === !==
逻辑: && || !
三元: cond ? trueVal : falseVal
```

## 类型转换

```js
"123"::int              // 123
"abc"::int(0)           // 0 (失败默认值)
"2020-01-01"::date("yyyy-MM-dd")
img::sql("blob")
```

## 流程控制

```js
// for循环
for(item in list) { ... }
for(key, value in map) { ... }
for(i in range(0, 10)) { ... }

// while循环
while(count > 0) { count-- }

// 可选链
obj?.prop    // null安全访问
obj?.method()
```

## Import导入

```js
// 导入Java类
import 'java.util.Date' as Date
import 'java.lang.System' as System

// 导入模块
import log
import http
```

## 假值判断

以下值在条件判断中为`false`：
- `null`
- 空集合/空Map/空数组
- 数值`0`
- `false`
