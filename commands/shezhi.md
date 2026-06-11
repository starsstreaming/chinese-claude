---
description: 用中文查看和修改 Claude Code 设置 (View and modify Claude Code settings in Chinese)
argument-hint: "[想查看或修改的设置，如：把回复语言设为中文]"
---

用户执行了 /shezhi 命令，参数：$ARGUMENTS

请按 chinese-claude 插件 shezhi-helper 技能（skills/shezhi-helper/SKILL.md）的流程操作，设置项含义参考 skills/shezhi-helper/shezhi-cankao.md：

- **参数为空**：读取用户的 `~/.claude/settings.json`（Windows 为 `%USERPROFILE%\.claude\settings.json`）和当前项目的 `.claude/settings.json`（如存在），用中文逐项解读当前生效的设置，并提几个常见的可调项（如 language、model、permissions、editorMode、theme）。
- **参数是问题**（如"权限是什么意思"）：先读真实配置，再用中文解释。
- **参数是修改请求**（如"把回复语言设为中文"、"允许 npm test 不再询问"）：确认写入哪个层级（个人偏好→用户级，团队共享→项目级），直接编辑对应 settings.json 完成修改，然后用中文说明改了什么、如何验证生效。涉及权限放行（allow）等安全相关修改时，先用一句话说明影响再动手。

全程用中文交流。不确定的设置项查官方文档 https://code.claude.com/docs/en/settings ，不要编造。
