# settings.json 设置项中文对照

> 整理自官方文档（2026-06，Claude Code v2.1.x）。以 https://code.claude.com/docs/en/settings 为准，新版本可能增减。

## 设置文件位置与优先级

| 层级 | 文件 | 用途 |
| --- | --- | --- |
| 用户级 user | `~/.claude/settings.json`（Windows：`%USERPROFILE%\.claude\settings.json`） | 个人偏好，所有项目生效 |
| 项目级 project | `<项目>/.claude/settings.json` | 团队共享，进版本库 |
| 本地级 local | `<项目>/.claude/settings.local.json` | 仅本机本项目，git 忽略 |
| 托管 managed | 企业管理员下发 | 不可被覆盖 |

优先级从高到低：托管 > 命令行参数 > 本地 > 项目 > 用户。

## 常用设置项

| 设置项 | 中文说明 |
| --- | --- |
| `model` | 默认模型（如 `"claude-sonnet-4-6"`），会话中可用 `/model` 切换 |
| `language` | Claude 回复使用的语言（如 `"chinese"`），同时影响语音输入语言；**不改变界面语言** |
| `permissions` | 工具权限规则：`allow`（自动放行）/ `ask`（询问，默认）/ `deny`（禁止），详见下文权限部分 |
| `env` | 注入每个会话及子进程的环境变量 |
| `hooks` | 生命周期钩子：在工具调用前后、会话开始等时机自动执行命令 |
| `outputStyle` | 输出风格（调整系统提示词） |
| `editorMode` | 输入框按键模式：`"normal"` 或 `"vim"` |
| `autoUpdatesChannel` | 更新通道：`"stable"`（稳一周）或 `"latest"`（最新） |
| `cleanupPeriodDays` | 会话记录保留天数，超期启动时清理（默认 30） |
| `autoMemoryEnabled` | 是否启用自动记忆（默认 `true`） |
| `alwaysThinkingEnabled` | 是否默认开启扩展思考 |
| `effortLevel` | 推理力度：`"low"` / `"medium"` / `"high"` / `"xhigh"` |
| `availableModels` | 限制 `/model` 可选的模型列表 |
| `fallbackModel` | 主模型过载时的备用模型（最多链 3 个） |
| `statusLine` | 自定义状态栏（可用 `/statusline` 配置） |
| `spinnerTipsEnabled` | 等待动画中是否显示小提示（默认 `true`） |
| `spinnerVerbs` | 自定义等待动画里的动词（如 "Pondering"） |
| `attribution` | 自定义 git 提交/PR 中的署名 |
| `includeCoAuthoredBy` | git 提交是否带 Claude 共同作者署名 |
| `includeGitInstructions` | 系统提示词中是否包含内置 git 工作流说明（默认 `true`） |
| `respectGitignore` | `@` 文件补全是否遵守 `.gitignore`（默认 `true`） |
| `fileSuggestion` | 自定义 `@` 文件补全脚本 |
| `enabledPlugins` | 启用的插件列表（由 `/plugin` 自动维护） |
| `forceLoginMethod` | 限制登录方式：`"claudeai"` 或 `"console"` |
| `theme` | 主题色（建议用 `/theme` 改） |

## 权限（permissions）速查

```json
{
  "permissions": {
    "allow": ["Bash(npm run test *)", "Read(~/.zshrc)"],
    "ask":   [],
    "deny":  ["Read(./.env)", "Read(./secrets/**)", "Bash(curl *)"]
  }
}
```

- 规则格式：`工具名(匹配模式)`，如 `Bash(git commit *)`、`Read(./.env)`、`WebFetch(domain:example.com)`
- `deny` 最优先；未匹配任何规则时默认询问（ask）
- 交互式管理：会话中执行 `/permissions`
- 权限模式（启动时 `--permission-mode` 或会话中 Shift+Tab 切换）：
  - `default`：每个敏感操作询问
  - `acceptEdits`：自动接受文件编辑
  - `plan`：计划模式，只读不改
  - `dangerously-skip-permissions`：全部放行（危险，仅限隔离环境）

## 常用环境变量（env 或系统环境）

| 变量 | 说明 |
| --- | --- |
| `ANTHROPIC_API_KEY` | API 密钥（API 计费方式时用） |
| `ANTHROPIC_MODEL` | 覆盖默认模型 |
| `HTTP_PROXY` / `HTTPS_PROXY` | 代理设置 |
| `CLAUDE_CODE_USE_BEDROCK=1` | 走 Amazon Bedrock |
| `CLAUDE_CODE_USE_VERTEX=1` | 走 Google Vertex AI |
| `DISABLE_TELEMETRY=1` | 关闭遥测 |
