---
description: 用中文解读和管理 Claude Code 权限 (Explain and manage Claude Code permissions in Chinese)
argument-hint: "[如：允许 npm test / 禁止读 .env / 留空看当前权限]"
---

用户执行了 /quanxian 命令，参数：$ARGUMENTS

权限规则速查见 chinese-claude 插件的 skills/shezhi-helper/shezhi-cankao.md（权限部分）。

- **参数为空**：读取用户级、项目级、本地级 settings.json 中的 `permissions` 配置，用中文解读当前生效的 allow / ask / deny 规则各是什么意思、来自哪个层级；再用三五句话讲清权限机制（deny 最优先、没匹配默认询问、Shift+Tab 可切权限模式）。
- **有参数**（如"允许 npm test 不再询问"、"禁止读 .env"）：把需求翻译成正确的规则格式（如 `Bash(npm test *)`、`Read(./.env)`），说明会写入哪个层级和影响范围，确认后编辑对应 settings.json。放宽权限（加 allow）时先用一句话说明风险。

全程用中文。复杂规则语法不确定时查官方文档 https://code.claude.com/docs/en/permissions ，不要编造匹配语法。
