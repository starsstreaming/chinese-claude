---
name: shuangyu-mode
description: 双语对照回复模式 (Bilingual Chinese-English response mode). Use this skill when the user writes in Chinese, asks for Chinese or bilingual responses, runs /shuangyu, or is learning Chinese through technical content. Defines how to format Chinese-English side-by-side answers.
---

# 双语对照回复规范 / Bilingual Response Guidelines

当本技能生效时，按以下规范用中英双语回复用户。

## 基本格式 / Basic Format

- **中文在前，English follows。** 按段落或小节对照，不要逐句穿插，避免机翻腔。
- 中文部分默认使用**简体中文**。若本会话中用户执行过 `/fanti` 或明确要求繁体，则中文部分改用**繁體中文**（并采用台湾/香港惯用术语，见下文）。
- 短回答（一两句话）可以只给一段中文 + 一段英文；长回答按小节组织，每个小节内先中文后英文。
- 标题可以用「中文 / English」双语形式。

## 技术术语 / Technical Terms

- 技术术语保留英文原文，**首次出现时**附中文译名，例如：「依赖注入（dependency injection）」「闭包（closure）」。之后可只用其中一种，以行文通顺为准。
- 命令、代码标识符、文件名、API 名称一律保留原文，不翻译。
- 常用术语译名以 [glossary.md](glossary.md) 为准；表中没有的术语按大陆主流技术社区习惯翻译。

## 代码与报错 / Code and Errors

- **代码本身不翻译**；代码注释用中文（繁体模式下用繁体）。
- 报错信息：先原样引用英文报错，再用中文解释含义和解决办法。

## 学习者模式 / Learner Mode

当用户明显是中文学习者（例如用英文提问但表示在学中文，或要求拼音）时：

- 关键中文词语附拼音标注，例如：变量 (biànliàng)、函数 (hánshù)。
- 可以顺带指出一两个值得学的常用说法，但不要喧宾夺主——技术问题本身仍是重点。
- 可参考 [glossary.md](glossary.md) 中的「English | 简体（繁體）| 拼音」三栏对照。

## 繁简术语差异 / Simplified vs Traditional Terminology

繁体模式不只是字形转换，部分术语在台湾/香港习惯不同，常见对照：

| 简体（大陆） | 繁體（台灣/香港） |
| --- | --- |
| 软件 | 軟體 |
| 变量 | 變數 |
| 数据 | 資料 |
| 网络 | 網路 |
| 内存 | 記憶體 |
| 对象 | 物件 |
| 数组 | 陣列 |
| 默认 | 預設 |
| 文件 | 檔案 |
| 服务器 | 伺服器 |

## 关闭 / Turning Off

用户执行 `/shuangyu off` 或明确要求只用某一种语言时，停止双语对照，按用户要求的语言回复。
