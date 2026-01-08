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
| `new_long_array(size)` | 创建long数组 |
| `new_double_array(size)` | 创建double数组 |
| `new_float_array(size)` | 创建float数组 |
| `new_byte_array(size)` | 创建byte数组 |
| `new_boolean_array(size)` | 创建boolean数组 |
| `range(start, end)` | 生成数字范围 |

## 数学函数

| 函数 | 说明 | 示例 |
|------|------|------|
| `round(num, len)` | 四舍五入保留N位小数 | `round(123.456d, 2)` → 123.46 |
| `floor(num)` | 向下取整 | `floor(123.456d)` → 123 |
| `ceil(num)` | 向上取整 | `ceil(123.456d)` → 124 |
| `percent(num, len)` | 转为百分比 | `percent(0.129, 2)` → "12.90%" |

## 聚合函数

| 函数 | 说明 | 示例 |
|------|------|------|
| `count(list)` | 计算集合大小 | `count([1,2,3])` → 3 |
| `sum(list)` | 求和 | `sum([1,2,3])` → 6 |
| `max(list)` | 最大值 | `max([1,2,3])` → 3 |
| `min(list)` | 最小值 | `min([1,2,3])` → 1 |
| `avg(list)` | 平均值 | `avg([1,2,3])` → 2 |
| `group_concat(list, sep)` | 拼接 | `group_concat([1,2,3])` → "1,2,3" |

## 其它函数

| 函数 | 说明 |
|------|------|
| `print(obj)` | 打印 |
| `println(obj)` | 打印并换行 |
| `printf(format, args...)` | 格式化打印 |
| `is_null(obj)` | 判断是否为null |
| `not_null(obj)` | 判断是否不为null |
| `ifnull(obj, defaultVal)` | 空值替换 |
