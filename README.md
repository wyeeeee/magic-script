# Magic-Script Skill

Magic-API 脚本开发助手技能，用于帮助 AI 编写 magic-api 接口脚本。

## 文件结构

```
magic-script/
├── SKILL.md                # 主文件(元数据+核心说明+索引)
├── README.md               # 本文件
└── references/             # 精简参考文档(按需加载)
    ├── syntax.md           # 语法/类型/流程控制
    ├── database.md         # 数据库基础操作
    ├── database-advanced.md # 事务/单表CRUD/缓存
    ├── modules.md          # HTTP/请求/响应模块
    ├── modules-extra.md    # magic/env/log/参数获取
    ├── functions.md        # 内置函数速查
    ├── lambda-linq.md      # Lambda与Linq操作
    ├── extensions.md       # 类型扩展方法
    ├── java-interop.md     # Java互操作/异步调用
    ├── examples.md         # 基础代码示例
    └── examples-advanced.md # 高级代码示例
```

## 触发条件

当用户需要：
- 编写 magic-api 接口脚本
- 进行数据库操作
- 发起 HTTP 请求
- 询问 magic-script 语法

## 分区加载策略

AI 根据任务类型按需加载对应文档，避免一次性加载全部内容。
