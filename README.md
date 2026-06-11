# 汉化Claude (chinese-claude)

让 Claude Code 用**中英双语对照**回复——方便华人使用，也帮你借技术场景学中文。

> A Claude Code plugin that makes Claude respond in bilingual Chinese-English, for Chinese-speaking users and Chinese learners. [English summary below](#english).

## 功能

- **双语对照模式**：中文在前、English 在后，按段落对照，不是机翻腔。代码不翻译、注释用中文，报错先引用原文再用中文解释。
- **简繁切换**：默认简体中文，`/fanti` 一键切换繁体（含术语差异：软件→軟體、变量→變數、内存→記憶體……），`/jianti` 切回简体。
- **术语词典**：内置 100+ 高频编程术语「英文 | 简体（繁體）| 拼音」三栏对照表，`/shuyu` 随手查。
- **学中文友好**：中文学习者可获得拼音标注，边写代码边学中文。
- **零脚本**：纯 Markdown/JSON，无任何可执行代码，跨平台（Windows/macOS/Linux），放心审计、放心装。

## 安装

### 方式一：从 GitHub 安装（推荐）

在 Claude Code 中执行：

```
/plugin marketplace add <你的GitHub用户名>/chinese-claude
/plugin install chinese-claude@chinese-claude
```

或在终端中：

```bash
claude plugin marketplace add <你的GitHub用户名>/chinese-claude
claude plugin install chinese-claude@chinese-claude
```

### 方式二：本地安装（无需联网/无需发布）

把本仓库 clone（或复制）到个人技能目录，下次启动自动加载：

```bash
git clone https://github.com/<你的GitHub用户名>/chinese-claude ~/.claude/skills/chinese-claude
```

### 方式三：开发调试

```bash
claude --plugin-dir /path/to/chinese-claude
```

## 命令

| 命令 | 说明 |
| --- | --- |
| `/shuangyu [on\|off]` | 开启/关闭双语对照模式 |
| `/fanti` | 中文输出切换为繁體中文（含术语转换） |
| `/jianti` | 切换回简体中文 |
| `/shuyu <术语>` | 查询编程术语：英文 / 简体 / 繁體 / 拼音 / 双语解释 |

安装后命令以插件名为命名空间，如 `/chinese-claude:shuangyu`；无冲突时直接用短名即可。

另外，当你直接用中文提问时，`shuangyu-mode` 技能也会被 Claude 自动启用，无需手动执行命令。

## 效果示例

> **你**：什么是闭包？
>
> **Claude**：
>
> 闭包（closure）是指一个函数（hánshù, function）连同它捕获的外部作用域变量一起构成的组合。即使外层函数已经返回，闭包仍然可以访问那些变量。
>
> A closure is a function bundled together with the variables it captures from its enclosing scope. Even after the outer function has returned, the closure can still access those variables.
>
> ```js
> function counter() {
>   let count = 0;        // 被闭包捕获的变量
>   return () => ++count; // 返回的函数仍能访问 count
> }
> ```

## 边界说明

本插件汉化的是 **Claude 的回复内容**。Claude Code 自身的界面（菜单、按钮、提示文字）由官方程序内置，插件无法翻译。

## 自定义

- 想默认全中文（不要英文对照）？执行 `/shuangyu off` 后直接告诉 Claude「以后只用中文回复」，或在 `~/.claude/CLAUDE.md` 中加一行「请始终用简体中文回复」。
- 术语译名有不同意见？欢迎改 [skills/shuangyu-mode/glossary.md](skills/shuangyu-mode/glossary.md) 并提 PR。

## 贡献

欢迎提 Issue 和 PR，特别是：

- 术语表补充与译名修正（请同时提供简体、繁体、拼音）
- 粤语、闽南语等方言注音支持
- 更多学习中文的玩法

## 协议

[MIT](LICENSE) — 自由使用、修改、分发。

---

## English

**chinese-claude** is a Claude Code plugin that makes Claude respond in bilingual Chinese-English: Chinese first, English follows, paragraph by paragraph. Code stays untranslated with Chinese comments; error messages are quoted verbatim then explained in Chinese. It ships a 100+ term English–Simplified–Traditional–Pinyin programming glossary, making it useful both for Chinese-speaking developers and for anyone **learning Chinese through code**.

Commands: `/shuangyu [on|off]` (toggle bilingual mode), `/fanti` (switch to Traditional Chinese, including terminology differences), `/jianti` (back to Simplified), `/shuyu <term>` (look up a term with pinyin).

Install: `/plugin marketplace add <your-github-username>/chinese-claude` then `/plugin install chinese-claude@chinese-claude`. Pure Markdown/JSON — no executable code, cross-platform. Note: the plugin localizes Claude's responses, not Claude Code's built-in UI. MIT licensed; contributions welcome.
