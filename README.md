<h1 align="center">code-review</h1>

面向所有 AI IDE 的轻量代码 Review Skill。

用于让 AI 总结自己生成的代码、命令、验证结果、风险和不确定项，并输出一个独立 HTML 报告。报告必须包含关键改动代码片段，不能只列文件名。

## 安装

打开你正在使用的 Agent，例如 Claude Code、Codex、Cursor、OpenClaw、Hermes、CodeBuddy、WorkBuddy、Gemini CLI、OpenCode 等，然后告诉它：
```bash
帮我安装这个 skill：https://github.com/SPUERSAIYAN/code-review-skill
```

或者使用通用 CLI 安装器 `vercel-labs/skills`：

```bash
npx skills add SPUERSAIYAN/code-review-skill
```

## 使用

示例：

> 使用 code-review skill，审查刚才 AI 生成的代码、执行过的命令和验证结果，生成一个 HTML Review 报告。报告里必须包含关键改动代码片段、风险、不确定项和下一步建议。

适用于 Codex、Cursor、Windsurf、Trae、Cline、Claude Code 等 AI 编程工具。

## 结果
<img width="495" height="645" alt="0c7d3751de1667bf1709a57791e5a870" src="https://github.com/user-attachments/assets/cd94b158-d4a1-4c69-9475-061e167350fd" />

