# Design Notes

These notes explain the skill's design for the person learning to write skills. They are not part of the weekly report workflow and should not be shown to report authors during ordinary use.

## Why the report is more detailed but still compact

The revised report increases information density through controlled fields rather than longer prose. Completed and Gantt items use `目标 / 具体动作 / 结果 / 证据`; failed work uses `尝试 / 原因或卡点 / 当前结论 / 下一步`; plans use `目标 / 准备做的动作 / 预期结果` and add risk only when confirmed. Each field starts on a separate line in its own paragraph in both Markdown and PDF. One or two pages is a preference, not a ceiling: add pages rather than joining fields or shrinking text.

## Why items are split selectively

The skill splits independent objectives, outputs, or clearly different methods/experiments, then merges routine steps under the same objective. This exposes meaningful work without manufacturing workload from tool calls, dates, or chat fragments.

## Why Markdown is the source of truth

The user wants an editable Markdown record and a visually readable PDF. Locking the approved Markdown before conversion keeps both files aligned and prevents PDF formatting work from silently rewriting the report.

## Why PDF conversion is separate

Different agents expose different local renderers. A temporary HTML or Word file can be used when it improves Chinese rendering, but it is only an implementation artifact. The skill delivers only the Markdown and PDF and reports a limitation instead of claiming a missing PDF.

## Why the header changed

The left `实验室工作周报` label duplicated the right-side report identity. It was removed while preserving the right-aligned lab/author line, Gantt week label, and centered page numbering.

## Why author confirmation remains mandatory

History, commits, files, and Gantt schedule markers help discover work but do not prove intent, completion, or reportability. Candidate review and explicit status confirmation prevent unsupported claims and allow the author to add work outside accessible agents.
