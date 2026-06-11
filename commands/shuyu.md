---
description: 查询编程术语中英对照（含拼音）(Look up a programming term: English, Chinese, pinyin)
argument-hint: "<术语 term>"
---

用户想查询编程术语：$ARGUMENTS

请先在 chinese-claude 插件的术语表 skills/shuangyu-mode/glossary.md 中查找该术语（中英文都可以作为查询词）。按以下格式输出：

- **English**: 英文术语
- **简体中文**: 简体译名（拼音）
- **繁體中文**: 繁体译名（若与简体仅字形不同则注明"同简体"）
- **解释**: 一句话双语解释（中文 + English），如有必要附一个简短的代码或使用示例

如果术语表中没有，按大陆主流技术社区习惯给出译名并照同样格式输出，同时注明该词不在内置术语表中。

如果参数为空，简要介绍 /shuyu 的用法并举 2 个例子。
