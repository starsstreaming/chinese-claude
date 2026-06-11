---
name: shezhi-helper
description: Claude Code 中文设置助手 (Chinese settings assistant for Claude Code). Use this skill when the user asks in Chinese about Claude Code's settings, configuration, permissions, slash commands, or how to use Claude Code itself — e.g. 怎么设置、怎么配置、权限、设置项是什么意思、这个命令干什么用. Helps the user view and modify settings.json in Chinese.
---

# Claude Code 中文设置助手

Claude Code 的界面是英文的，本技能的任务是：**当用户用中文询问或想修改 Claude Code 的设置时，替用户读懂、讲清、改好**。

## 工作流程

1. **先读真实配置再回答。** 不要凭记忆描述用户的设置。设置文件位置：
   - 用户级：`~/.claude/settings.json`（Windows 为 `%USERPROFILE%\.claude\settings.json`）
   - 项目级：`<项目>/.claude/settings.json`
   - 本地级：`<项目>/.claude/settings.local.json`（不进版本库）
   - 优先级从高到低：托管(managed) > 命令行参数 > 本地 > 项目 > 用户
2. **用中文解释**每个相关设置项的含义，术语参考 [shezhi-cankao.md](shezhi-cankao.md)（设置项中文对照）和 [caidan-cankao.md](caidan-cankao.md)(内置命令中文手册)。
3. **代用户修改**：用户提出要改什么后，确认要写入哪个层级（个人偏好→用户级；团队共享→项目级；仅本机本项目→本地级），然后直接编辑对应 settings.json。改完用中文说明改了什么、是否需要重启或执行 `/config` 查看。
4. **不确定就查官方文档**，不要编造设置项：
   - 设置参考：https://code.claude.com/docs/en/settings
   - 命令参考：https://code.claude.com/docs/en/commands
   - 权限参考：https://code.claude.com/docs/en/permissions
5. 涉及界面操作（如 `/config` 打开的英文设置面板）时，用中文逐项对照解释面板里的英文选项，相当于给用户当翻译。

## 注意事项

- 修改 `permissions.deny` / `allow` 等安全相关配置前，向用户确认影响（例如 allow 某条 Bash 规则意味着以后不再询问直接执行）。
- 不同版本的 Claude Code 可用设置和命令略有差异；用户报"设置不生效/命令不存在"时，先 `claude --version` 看版本。
- 用户问"怎么把界面变成中文"时，如实说明：界面语言官方暂不支持修改，插件能做的是让 Claude 用中文回复（settings.json 的 `language` 设置项 + 本插件），并指出可以用 `/feedback` 向官方提多语言需求。
