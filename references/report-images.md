# Report Images

Images are optional. Use them only when a visual would make a specific work item easier to understand, such as a verified experiment setup, a real interface change, a process the author implemented, or a chart based on confirmed data. A page that looks sparse is not by itself a reason to add an image.

## Ask and place

1. Identify the specific work item and explain briefly what the image would clarify.
2. Ask once: `这项工作配一张图会更容易看懂。你想用 AI 生成图片、由你提供图片，还是不需要图片？`
3. If the author chooses no image, continue without one. Do not ask again for that item.
4. If the author provides an image, use the supplied file as-is unless they ask for edits. Preserve its meaning and place it directly below that item's fields. If it is a local file, copy it into a report-local `images/` directory so both deliverables remain portable; do not overwrite existing assets.
5. If the author chooses AI generation, create one image for that item using the built-in image-generation tool when available. Base it on confirmed content, do not invent measurements, UI details, people, results, or data. Prefer a clear explanatory illustration or diagram; if it is illustrative rather than a faithful record, label it `示意图`. Save the final image beside the reports in `images/`, use a descriptive filename, and inspect it before insertion. Ask for a correction or omit it if it misrepresents the work.
6. Embed the approved image in Markdown with a relative path and render the same image below the corresponding item in the PDF. Keep it out of headings and do not let it split or displace the required field paragraphs. Record an image caption only when useful and approved.

If image generation is unavailable, explain that limitation and ask whether the author wants to provide an image or proceed without one. Do not silently switch to an API or another generation method.

Images illustrate the report; they are not evidence. Keep evidence in the `证据` field as a verifiable file, test result, commit, source, or author-provided reference. Do not put text-heavy factual claims into generated images; keep report wording in the Markdown body.
