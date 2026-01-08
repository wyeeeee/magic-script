# 类型扩展方法

## Object扩展

```js
// 类型转换
obj.asInt()           // 转int，失败返回0
obj.asInt(defaultVal) // 转int，失败返回默认值
obj.asDouble()        // 转double
obj.asLong()          // 转long
obj.asFloat()         // 转float
obj.asString()        // 转String
obj.asDate("yyyy-MM-dd")  // 转Date
obj.asDecimal()       // 转BigDecimal

// 类型判断
obj.is("string")      // 判断类型
obj.isString()        // 是否String
obj.isInt()           // 是否int
obj.isLong()          // 是否long
obj.isDouble()        // 是否double
obj.isDate()          // 是否Date
obj.isArray()         // 是否数组
obj.isList()          // 是否List
obj.isMap()           // 是否Map
obj.isCollection()    // 是否集合
```

## Number扩展

```js
var num = 123.456d
num.round(2)      // 123.46 四舍五入
num.toFixed(10)   // "123.4560000000" 固定小数位
num.floor()       // 123 向下取整
num.ceil()        // 124 向上取整
num.asPercent(2)  // "12345.60%" 转百分比
```

## Date扩展

```js
var date = new Date()
date.format("yyyy-MM-dd HH:mm:ss")  // 格式化日期
```

## 集合扩展

```js
var list = [1, 2, 3, 4, 5]

// 遍历与转换
list.map(e => e + 1)      // [2,3,4,5,6]
list.filter(e => e > 3)   // [4,5]
list.each(e => println(e)) // 循环处理
list.sort((a,b) => a - b) // 排序

// 取值
list.first()              // 1
list.last()               // 5
list.find(e => e > 3)     // 4
list.findIndex(e => e > 3) // 3

// 聚合
list.sum()                // 15
list.avg()                // 3
list.max()                // 5
list.min()                // 1

// 其他操作
list.join("-")            // "1-2-3-4-5"
list.reverse()            // [5,4,3,2,1]
list.shuffle()            // 打乱
list.distinct()           // 去重
list.skip(2)              // [3,4,5]
list.limit(3)             // [1,2,3]
list.concat([6,7])        // [1,2,3,4,5,6,7]
list.every(e => e > 0)    // true 全部满足
list.some(e => e > 4)     // true 部分满足
list.reduce((sum,v) => sum + v) // 6 累加
list.toMap(k => k, v => v*2)    // 转Map
```

## Pattern扩展

```js
var regx = /^\d+$/
regx.test("123456")  // true 校验是否匹配
```

## Class扩展

```js
import 'java.text.SimpleDateFormat' as SDF
SDF.newInstance('yyyy-MM-dd')  // 实例化
SDF.getName()                   // 获取类名
```
