# PDF Output

Render the author-approved Markdown into a PDF. The Markdown is the source of truth: the PDF body must preserve the same visible wording, punctuation, numbers, technical terms, links, field labels, order, and table values. PDF-only additions are limited to the running header, page-number footer, and visual formatting.

## Files and conversion

- Ask once for the PDF destination. Save `YYYY-MM-DD-Author-周报.md` and `YYYY-MM-DD-Author-周报.pdf` in the same directory.
- Use a reliable local Markdown-to-PDF, HTML-to-PDF, or temporary Word-to-PDF path available in the current environment. Temporary conversion files are artifacts: delete them when practical and never deliver them.
- If either target already exists, do not overwrite it; choose a distinct filename or ask the author.
- Do not upload report content to an external conversion service unless the author explicitly requests it.

## Page and visual style

- Use A4 portrait. Set top and bottom margins to 2.54 cm, left and right margins to 2.5 cm, header distance to 1.5 cm, and footer distance to 1.75 cm.
- Use one restrained navy accent, `#1F3864`; use `#F2F4F7` for subtle shading and `#333333` for body text. Do not add decorative icons, status dots, slogans, or illustrations.
- Use Heiti or Source Han Sans for the title and section headings, and Microsoft YaHei for body text when available. The main title is 20 pt bold navy, centered, with 18 pt after-spacing and a 1.5 pt navy bottom border.
- Use 14 pt bold navy first-level headings with a 4 pt navy left border, 14 pt before-spacing, and 8 pt after-spacing. Use 11.5 pt bold dark-gray task/project subheadings. Use 10.5–11 pt body text, 1.5 line spacing, 4 pt after-spacing, and readable margins.
- Keep one visual style per list level. Format Markdown lists without changing visible wording or order.
- Render every labeled field as a separate paragraph or list item starting on a new line. In completed and Gantt items, `目标`, `具体动作`, `结果`, and `证据` must occupy four separate paragraphs; apply the same rule to incomplete items and next-week plans. Do not concatenate fields into a continuous paragraph or remove these line breaks to fit a page target. One or two pages is a preference, not a ceiling; add pages while retaining the specified body font, spacing, margins, and all approved text.

## Header and footer

- Leave the left side of the header empty. Do not add `实验室工作周报`.
- At the right, place two right-aligned lines: `北邮智电实验室脑机组{author}周报` above the confirmed Gantt week label. Use 9 pt light-gray text and a thin light-gray bottom border.
- Center the footer text `第 X 页 / 共 Y 页` in 9 pt light-gray text, using page-number and total-page fields when supported.
- These exact header/footer strings and generated page-number fields are the only text additions exempt from the Markdown/PDF body equality check.

## Verify

1. Save the approved Markdown before conversion. Extract or inspect the visible PDF body and compare it with Markdown in order. Account only for Markdown syntax rendered as formatting; do not normalize prose punctuation, whitespace inside prose, numbers, labels, or wording.
2. Verify the right-aligned header strings and footer fields separately. Confirm the removed left header text is absent.
3. Render the PDF to page images or use an equivalent local preview and inspect every page. Confirm Chinese glyphs render, text is legible, hierarchy is clean, links are present, sections remain in order, and nothing is clipped or unexpectedly split. Check that each field begins on a separate line in its own paragraph; matching extracted text does not establish correct line breaks. Keep each task heading with its first field, and keep field labels with their content. Allow three or more pages when needed; do not merge field paragraphs, shrink text, or omit verified work to reduce page count.
4. If rendering or PDF creation is unavailable, still save the approved Markdown and clearly report that the PDF could not be created or visually verified. Do not substitute a DOCX or claim successful PDF delivery.
