---
description: Claude Code 命令中文手册 (Chinese manual for Claude Code built-in commands)
argument-hint: "[命令名，如 compact；留空看全部]"
---

用户执行了 /caidan 命令，参数：$ARGUMENTS

中文命令手册在 chinese-claude 插件的 skills/shezhi-helper/caidan-cankao.md。

- **参数为空**：读取该手册，按"会话与上下文 / 模型与回复 / 配置与权限 / 项目与记忆 / 任务与并行 / 代码审查 / 扩展 / 集成与其他"分类，输出全部内置命令的中文对照表。开头提醒一句：可用 `/caidan 某命令` 查看单个命令的详细说明。
- **有参数**（命令名，带不带斜杠都行）：详细解释该命令——做什么、参数怎么写、典型使用场景、1-2 个示例。手册里只有一句话简介，详细信息可查官方文档 https://code.claude.com/docs/en/commands 。如果该命令不存在，提示用户可能的拼写或相近命令。

全程用中文回答。提醒用户：部分命令是否可见取决于平台、订阅计划和 Claude Code 版本。
