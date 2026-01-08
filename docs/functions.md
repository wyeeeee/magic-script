# 内置函数速查

## 字符串函数

| 函数 | 说明 | 示例 |
|------|------|------|
| `uuid()` | 生成32位UUID | `uuid()` |
| `is_blank(str)` | 判断是否为空 | `is_blank("")` → true |
| `not_blank(str)` | 判断是否不为空 | `not_blank("a")` → true |

## 日期函数

| 函数 | 说明 | 示例 |
|------|------|------|
| `now()` | 当前日期 | `now()` |
| `date_format(date, pattern)` | 格式化日期 | `date_format(now(), "yyyy-MM-dd")` |
| `current_timestamp()` | 当前时间戳(秒) | `current_timestamp()` |
| `current_timestamp_millis()` | 当前时间戳(毫秒) | `current_timestamp_millis()` |

## 数组函数

| 函数 | 说明 |
|------|------|
| `new_array(size)` | 创建Object数组 |
| `new_int_array(size)` | 创建int数组 |
| `new_byte_array(size)` | 创建byte数组 |
| `range(start, end)` | 生成数字范围 |
