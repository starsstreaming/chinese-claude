---
description: 开启/关闭中英双语对照回复模式 (Toggle bilingual Chinese-English response mode)
argument-hint: "[on|off]"
---

用户执行了 /shuangyu 命令，参数：$ARGUMENTS

- 如果参数是 `off`：从现在起停止双语对照，恢复正常回复语言。
- 如果参数是 `on`、为空或其他：从现在起本会话**开启双语对照模式**，严格遵循 chinese-claude 插件中 shuangyu-mode 技能（skills/shuangyu-mode/SKILL.md）定义的双语回复规范：中文在前、English 在后，分段对照；术语译名以 glossary.md 为准；代码不翻译、注释用中文；报错先引用原文再用中文解释。中文默认简体，若用户之前执行过 /fanti 则用繁体。

切换后用一句双语（中文+English）确认当前模式，不要长篇解释。
