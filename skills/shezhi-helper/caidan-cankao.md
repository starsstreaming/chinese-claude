# Claude Code 内置命令中文手册

> 整理自官方文档（2026-06，Claude Code v2.1.x）。完整英文版：https://code.claude.com/docs/en/commands
> 并非所有命令对所有用户可见，取决于平台、订阅计划和版本。

## 会话与上下文

| 命令 | 中文说明 |
| --- | --- |
| `/clear [名称]` | 清空上下文开新对话，旧对话保留在 `/resume` 里（别名 `/new`、`/reset`） |
| `/compact [侧重说明]` | 压缩对话腾出上下文，可附加摘要侧重点 |
| `/context [all]` | 彩色网格显示上下文占用情况和优化建议 |
| `/resume [会话]` | 恢复历史会话（别名 `/continue`） |
| `/rewind` | 回退对话和/或代码到之前的检查点（别名 `/undo`、`/checkpoint`） |
| `/branch [名称]` | 从当前位置分叉一份对话试另一条路，原对话可随时回去 |
| `/fork <指令>` | 派生一个继承完整对话的后台子智能体去办事，你继续聊 |
| `/btw <问题>` | 问个小问题，不占用对话历史 |
| `/rename [名称]` | 重命名当前会话 |
| `/recap` | 生成本次会话一句话总结 |
| `/export [文件名]` | 导出对话为纯文本 |
| `/copy [N]` | 复制最近第 N 条回复到剪贴板 |
| `/exit` | 退出（别名 `/quit`） |

## 模型与回复

| 命令 | 中文说明 |
| --- | --- |
| `/model [模型]` | 切换模型并存为默认；无参数打开选择器 |
| `/effort [档位]` | 调推理力度：low / medium / high / xhigh / max / ultracode |
| `/fast [on\|off]` | 开关快速模式（Opus 高速输出） |
| `/advisor [模型\|off]` | 开关顾问模式：关键时刻咨询第二个模型 |
| `/usage` | 查看用量、费用、配额（别名 `/cost`、`/stats`） |
| `/usage-credits` | 配置超量后的付费额度 |

## 配置与权限

| 命令 | 中文说明 |
| --- | --- |
| `/config` | 打开设置面板：主题、模型、输出风格等（别名 `/settings`） |
| `/status` | 设置面板的状态页：版本、模型、账号、连接状态 |
| `/permissions` | 管理工具权限的 allow / ask / deny 规则（别名 `/allowed-tools`） |
| `/hooks` | 查看钩子（hook）配置 |
| `/theme` | 换主题色，支持自动亮暗、色盲友好、自定义主题 |
| `/statusline` | 配置状态栏，描述想要什么即可 |
| `/keybindings` | 打开快捷键配置文件 |
| `/terminal-setup` | 配置终端按键（如 Shift+Enter），仅部分终端可见 |
| `/tui [default\|fullscreen]` | 切换终端渲染器（全屏防闪烁模式） |
| `/scroll-speed` | 调鼠标滚轮速度（仅全屏模式） |
| `/focus` | 切换专注视图：只看最后的提问、工具摘要和回复 |
| `/color [颜色]` | 设置输入栏颜色 |
| `/sandbox` | 开关沙箱模式（部分平台） |
| `/privacy-settings` | 查看/修改隐私设置（Pro/Max） |
| `/doctor` | 体检：诊断安装与配置问题，按 `f` 让 Claude 修复 |
| `/login` / `/logout` | 登录 / 登出 Anthropic 账号 |
| `/release-notes` | 查看更新日志 |

## 项目与记忆

| 命令 | 中文说明 |
| --- | --- |
| `/init` | 为项目生成 CLAUDE.md 入门指南 |
| `/memory` | 编辑 CLAUDE.md 记忆文件、管理自动记忆 |
| `/add-dir <路径>` | 本会话额外允许访问一个目录 |
| `/cd <路径>` | 把会话搬到新工作目录（v2.1.169+） |

## 任务与并行

| 命令 | 中文说明 |
| --- | --- |
| `/plan [描述]` | 进入计划模式：先研究出方案、批准后再动手 |
| `/goal [条件]` | 设个目标，Claude 跨回合持续干到达成为止 |
| `/agents` | 管理子智能体（subagent）配置 |
| `/tasks` | 查看/管理后台运行的任务（别名 `/bashes`） |
| `/background [提示]` | 把当前会话转后台运行，释放终端（别名 `/bg`） |
| `/stop` | 停止当前后台会话 |
| `/batch <指令>` | 大规模改动：拆成多个独立单元并行各开 worktree 完成 |
| `/loop [间隔] [提示]` | 循环执行某个提示（如每 5 分钟查一次部署） |
| `/schedule [描述]` | 创建云端定时任务（别名 `/routines`） |
| `/workflows` | 查看/暂停/恢复运行中的工作流 |

## 代码审查与验证

| 命令 | 中文说明 |
| --- | --- |
| `/code-review [力度] [--fix]` | 审查当前改动找 bug 和可简化处；`ultra` 为云端深度多智能体审查 |
| `/review [PR]` | 在当前会话里审查一个 Pull Request |
| `/security-review` | 安全审查当前分支改动：注入、鉴权、数据泄露等 |
| `/simplify [目标]` | 只做代码清理（复用/简化/效率），不找 bug |
| `/verify` | 实际构建并运行应用验证改动有效 |
| `/run` | 启动并操作项目应用看改动的真实效果 |
| `/diff` | 交互式查看未提交改动和每回合的 diff |

## 扩展：插件 / MCP / 技能

| 命令 | 中文说明 |
| --- | --- |
| `/plugin [子命令]` | 管理插件：list / install / enable / disable |
| `/reload-plugins [--force]` | 不重启重新加载插件 |
| `/mcp [子命令]` | 管理 MCP 服务器连接和 OAuth 认证 |
| `/skills` | 列出可用技能，可隐藏不想要的 |
| `/reload-skills` | 重新扫描技能目录（v2.1.152+） |

## 集成与其他

| 命令 | 中文说明 |
| --- | --- |
| `/ide` | 管理 IDE 集成 |
| `/chrome` | 配置 Claude in Chrome 浏览器扩展 |
| `/desktop` | 把会话转到桌面 App 继续（别名 `/app`） |
| `/mobile` | 显示手机 App 下载二维码（别名 `/ios`、`/android`） |
| `/remote-control` | 允许从 claude.ai 远程控制本会话（别名 `/rc`） |
| `/teleport` | 把网页版会话拉到本终端（别名 `/tp`） |
| `/web-setup` | 用本地 gh 凭证连接网页版 Claude Code |
| `/remote-env` | 选择云端智能体的默认环境 |
| `/install-github-app` | 为仓库安装 Claude GitHub Actions |
| `/install-slack-app` | 安装 Claude Slack 应用 |
| `/autofix-pr [提示]` | 开云端会话盯着 PR，CI 挂了或有评论自动修 |
| `/ultraplan <提示>` | 云端起草计划、浏览器审阅、远程或本地执行 |
| `/deep-research <问题>` | 多路网络搜索交叉验证，产出带引用的研究报告 |
| `/claude-api` | 加载 Claude API 参考资料 / 迁移旧代码到新模型 |
| `/feedback [报告]` | 反馈问题、报 bug（别名 `/bug`、`/share`） |
| `/help` | 显示帮助和可用命令 |
| `/insights` | 生成你的 Claude Code 使用分析报告 |
| `/powerup` | 互动小课堂：学习 Claude Code 功能 |
| `/team-onboarding` | 根据你的使用历史生成团队上手指南 |
| `/debug [描述]` | 开启调试日志并排查本会话的问题 |
| `/heapdump` | 导出内存快照，排查内存占用过高 |
| `/voice [模式]` | 开关语音输入 |
| `/radio` | 打开 Claude FM lo-fi 电台 🎵 |
| `/stickers` | 订购 Claude Code 贴纸 |
| `/upgrade` | 升级订阅计划 |
