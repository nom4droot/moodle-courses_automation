# Lesson workflow

These observations were exercised on Moodle 4.5 / СЭО 3KL. Read current UI state; labels and defaults can vary.

## Create native Lessons

Enable editing in the active browser session, choose the intended section, and add «Лекция». Chrome and an in-app browser can have different login/editing states. Inspect grade/navigation settings rather than assuming defaults match an example.

A new Lesson offers importing questions, adding an information page, or adding a question page. Information pages use «Заголовок страницы» and «Содержание страницы». Under «Содержимое 1», set the description to «Далее» and the jump to «Следующая страница». Leave unused button slots empty. Use separate information pages for source subthemes when that matches the requested example.

## HTML and images

TinyMCE: «Инструменты» → «Исходный код» → fill the dialog textbox → save the dialog → save the Moodle page. Scope to the correct editor when the form contains several.

TinyMCE may convert data-URI images into Moodle draft files and temporarily disable the page-save button. Inspect enabled state and let processing finish. Do not resubmit an unknown outcome. Check published images after scrolling into view; lazy images initially report `complete=false` and zero natural width.

Resize/compress images before insertion. One observed 10 MB base64 HTML payload restarted the control connection; a roughly 0.5 MB version succeeded. These are observations, not universal limits. When editing existing HTML, preserve current Moodle image URLs and unrelated markup.

## Question import

Lesson accepts Moodle XML for single choice, multiple choice, and matching. In the importer choose «Формат Moodle XML», then «Выберите файл...» → «Загрузить файл» → «Вложение». Use the documented browser filechooser API with an absolute local path. Upload, verify the filename, import, then verify counts and resulting page order.

For multiple correct choices, use `single=false` and positive fractions totaling 100. Verify the resulting Lesson scores; Quiz fraction semantics do not necessarily carry through unchanged. Unsupported question types may be skipped. Do not assume description questions become native information pages.

Placement matters: importing with `pageid=0` puts questions at the start. An observed information-page insertion link with `pageid=0` inserts before the first page. One useful workflow is to import questions, then insert information pages at the start in reverse order. Derive links from observed UI and record new IDs after saving.

## Scoring observations

The tested standard importer made correct choices score 1 / next-page jump, wrong choices score 0 / current-page jump. Multiple-answer questions require the exact set of correct choices. Matching has separate correct/incorrect scores and jumps. Check site behavior if uncertain.

The user's examined example used maximum grade 5, custom scoring, one attempt per question, and ordinary sequential navigation. These values belong to that example; they are not defaults for all future courses.
