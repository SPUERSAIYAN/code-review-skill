<h1 align="center">code-review</h1>

面向所有 AI IDE 的轻量代码 Review Skill。

用于让 AI 总结自己生成的代码、命令、验证结果、风险和不确定项，并输出一个独立 HTML 报告。报告必须包含关键改动代码片段，不能只列文件名。

## 下载

```bash
npx degit SPUERSAIYAN/code-review-skill code-review
```

```bash
git clone https://github.com/SPUERSAIYAN/code-review-skill.git
```

## 使用

把 `SKILL.md` 作为 AI 指令，把 `assets/report-template.html` 作为 HTML 模板。

适用于 Codex、Cursor、Windsurf、Trae、Cline、Claude Code 等 AI 编程工具。

