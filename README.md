# code-review

AI IDE agnostic code-review skill for reviewing AI-generated code, commands, verification evidence, risks, and uncertainties, then producing a compact standalone HTML report from a static template.

Use it in Codex, Cursor, Windsurf, Trae, Cline, Claude Code, or any AI coding assistant by giving the assistant `SKILL.md` as the instruction and `assets/report-template.html` as the output template.

Core requirement: the HTML report must include key changed code snippets, not only changed filenames.
