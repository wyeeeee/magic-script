# Magic-Script Skill

Magic-API脚本开发助手技能，用于帮助AI编写magic-api接口脚本。

## 文件结构

```
magic-script/
├── SKILL.md              # 主文件(元数据+核心说明)
├── syntax.md             # 语法参考
├── database.md           # 数据库基础操作
├── database-advanced.md  # 事务/单表CRUD/缓存
├── modules.md            # HTTP/请求/响应模块
├── modules-extra.md      # magic/env/log模块
├── functions.md          # 内置函数速查
├── examples.md           # 基础代码示例
└── examples-advanced.md  # 高级代码示例
```

## 触发条件

当用户需要：
- 编写magic-api接口脚本
- 进行数据库操作
- 发起HTTP请求
- 询问magic-script语法

## 分区加载策略

AI根据任务类型按需加载对应文档，避免一次性加载全部内容。
