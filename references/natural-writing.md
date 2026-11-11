# Natural Weekly Report Writing

Use this guide when turning verified notes into report prose. The report should sound like the author explaining real work to a supervisor, not like a press release or a generic AI summary.

## Keep it grounded

- Preserve the author's meaning, technical terms, uncertainty, and confirmed level of confidence. Do not add opinions, emotions, causal explanations, or personal growth the author has not endorsed.
- Prefer concrete actions and outcomes: what was changed, tested, compared, observed, or left unresolved. Name the actual artifact or result when known.
- Use first person naturally for the author's reflection (`我发现`, `我学到`), especially in `学到了什么`. Do not force `我` into every factual sentence.
- When the evidence is partial, say what is known and what remains unclear. Do not turn an attempt into a success or imply broader impact.

## Edit for natural Chinese

- Remove filler openings, empty transitions, and generic conclusions. Start with the work itself.
- Prefer ordinary verbs such as `完成`, `修改`, `测试`, `比较`, `定位`, `发现`, and `还没解决` over inflated language such as `赋能`, `彰显`, `具有重要意义`, or `取得显著成效`.
- Avoid promotional claims, vague attributions, forced three-part lists, repeated synonym swaps, excessive bold, and overuse of `此外`, `值得注意的是`, `不仅……而且……` or em dashes.
- Vary sentence length where it helps, but keep each required field concise and easy to scan. Professional writing can be direct without sounding stiff; do not add jokes, digressions, or artificial emotion to make prose seem human.
- Keep the required report headings and field labels. Naturalization must never remove evidence, weaken a factual distinction, or merge separately required fields.

## Example

Stiff: `本周针对检索模块进行了全面优化，显著提升了系统整体性能，并为后续工作奠定了坚实基础。`

Natural and evidence-led: `我调整了检索结果的排序，并用 20 条样例做了回归测试。其中 16 条的目标文档排在前两位；另外 4 条还需要检查切分方式。`

For `学到了什么`, draft a specific reflection from confirmed work, then show it to the author for approval. For example: `这次对照测试让我发现，召回结果不理想时，问题可能出在文档切分，不一定是排序参数。` Use this only if the author confirms it reflects their actual learning.
