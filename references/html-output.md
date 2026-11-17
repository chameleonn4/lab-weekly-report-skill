# HTML Output

Create one self-contained weekly-report presentation in `YYYY-MM-DD-Author-周报.html`. The author-approved wording is the content source of truth. Do not create Markdown, PDF, DOCX, or separate image/source-asset deliverables. Ask once for the output directory and never overwrite an existing report.

## Presentation style

- Follow the visual language of the user's approved ACE presentation: a 16:10 slide canvas, near-black graphite background (`#090a0b`), warm light text (`#f4f3f1`), muted gray secondary text, and restrained red emphasis (`#ee3546`). Use thin dividers, restrained gradients, compact navigation, and generous but efficient spacing. Keep display type suited to slides and body text comfortably readable.
- Provide a consistent top navigation, current-section indication, progress and slide count, previous/next controls, a contents dialog, and fullscreen control. Support keyboard navigation and touch swipes. Provide visible labels and focus states; respect reduced-motion preferences.
- Present the report as a short opening summary/index followed by the verified work, Gantt progress, and other applicable sections. Keep each work item's heading with its first field. Give each required field its own visually distinct block. When an item does not fit legibly, continue it on a titled follow-up slide; preserve its wording and field order.
- Keep the weekly report focused on the author's work. Reuse the ACE presentation's visual system, not its unrelated ACE explanatory content. Do not add unsupported interpretations, claims, slogans, or decorative illustrations.
- Make the presentation adapt to common projection sizes and narrow screens without clipped text or overlapping controls. Keep the 16:10 slide composition on presentation-sized viewports; use an appropriate narrow-screen layout or scaling that remains legible and touch-operable.

## Single-file and offline behavior

- Inline all CSS and JavaScript. Do not load fonts, scripts, stylesheets, images, charts, or libraries from a CDN or remote host. Use system font stacks.
- Embed each author-approved image, chart, or source file that should be available from the report. Use data URLs or an inline payload and create download links at runtime when appropriate. Preserve the exact approved file bytes and a useful filename for downloads. Do not emit sidecar assets.
- Do not embed every discovered source file by default. Embed only items selected/approved for the report or explicitly made available as report downloads. Keep evidence references visible in the relevant `证据` field even when a source file is also downloadable.
- Avoid making unapproved local machine paths appear to be portable links. Show them as text, or embed an approved file and provide a working download.
- Keep report copy separate from interface text in implementation so all authored content can be checked for completeness. Interface-only labels may include navigation, slide numbers, controls, and download action labels; they must not rewrite report wording.

## Verify

1. Confirm that the saved filename uses the generation date and confirmed author name. If it already exists, choose another name or ask the author; never overwrite it.
2. Compare the visible report content and field order against the approved draft. Confirm all approved wording, evidence, links, images, and placements are present. The HTML is the only delivered file.
3. Open the final file in a local browser with network access disabled or monitor requests. Confirm it works from `file:` without remote dependencies.
4. Inspect every slide at a standard presentation size, a second desktop size, and a narrow mobile viewport. Confirm legible text, intact Chinese glyphs, field separation, no clipping or overlap, and functioning navigation. Test previous/next, keyboard and touch navigation where available, contents navigation, fullscreen, and each embedded-file download.
5. If browser rendering or interaction checks are unavailable, disclose what could not be verified. Do not substitute Markdown/PDF or claim the single-file report is fully checked.
