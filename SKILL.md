---
name: code-review
description: Review code changes, shell commands, tool calls, file operations, test results, and implementation decisions produced by any AI IDE or coding assistant, then generate a standalone HTML report from a static template. Use when the user asks to audit, review, summarize, inspect, document, or deliver a report about what an AI coding tool changed, executed, verified, failed to verify, or is uncertain about.
---

# code-review

Create a compact standalone HTML review report from `assets/report-template.html`. The workflow is AI IDE agnostic: it can be used by Codex, Cursor, Windsurf, Trae, Cline, Claude Code, or any assistant that can inspect files and write HTML.

## Workflow

1. Inspect only needed evidence: `git status --short`, `git diff --stat`, relevant diffs/files, command output, test/build/lint output, and conversation context.
2. Match the user's dominant language: Chinese user -> Chinese report; English user -> English report.
3. Copy the template and replace every `{{...}}` placeholder directly. Do not use a script.
4. Keep sections short: bullets, compact cards, or short paragraphs.
5. The code section must show important code snippets, not just changed filenames.

## Code Section Requirement

`{{CODE_CHANGES}}` must include real changed code when code changes are available.

Use this compact structure for each important change:

```html
<div class="grid">
  <article class="item">
    <div class="label">file path</div>
    <p>What changed and why it matters.</p>
    <pre><code>escaped key code snippet</code></pre>
  </article>
</div>
```

Rules for snippets:
- Include 1-5 key snippets that best explain the AI work.
- Prefer actual changed code from diffs or files.
- Keep each snippet short, usually 5-30 lines.
- If a full block is too long, trim unrelated lines and mark omitted parts with comments.
- Escape `<`, `>`, and `&` inside code blocks.
- If no code changed, explicitly say no code changes were found.
- Do not replace code snippets with file-only bullets.

## Placeholders

- Core: `{{HTML_LANG}}`, `{{TITLE}}`, `{{SUMMARY}}`, `{{GENERATED_AT}}`, `{{WORKSPACE}}`
- Labels: `{{L_GENERATED}}`, `{{L_WORKSPACE}}`, `{{L_OVERVIEW}}`, `{{L_CODE_CHANGES}}`, `{{L_COMMANDS_ACTIONS}}`, `{{L_VERIFICATION}}`, `{{L_RISKS}}`, `{{L_UNCERTAINTIES}}`, `{{L_NEXT_STEPS}}`, `{{L_FOOTER}}`
- Content: `{{OVERVIEW}}`, `{{CODE_CHANGES}}`, `{{COMMANDS_ACTIONS}}`, `{{VERIFICATION}}`, `{{RISKS}}`, `{{UNCERTAINTIES}}`, `{{NEXT_STEPS}}`

## Rules

- Escape unsafe user/code text before inserting HTML.
- State facts only when backed by evidence.
- Put unverified claims and missing checks in `{{UNCERTAINTIES}}`.
- Do not modify the reviewed project unless separately asked.
- If evidence is missing, say so; do not invent it.
