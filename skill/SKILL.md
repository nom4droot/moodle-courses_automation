---
name: moodle-courses
description: Create, migrate, edit, and audit Moodle or СЭО 3KL courses, including native Lessons, quizzes, file-based Assignments, grading, and navigation.
---

# Moodle courses

Use the available browser-control tools and their current documentation. This skill supplies Moodle-specific workflow; it does not grant access or permission to modify a course.

## Activity and source mapping

Russian Moodle «Лекция» is the native Lesson activity (`/mod/lesson/`), not a Page resource (`/mod/page/`). Inspect an existing example's internal pages, question placement, navigation, and grading before reproducing its design. Separate Quizzes are a different structure: follow the user's choice.

Map source sections, themes, subthemes, and questions explicitly. Read document paragraphs and tables in order. In Word tests, run highlighting can mark correct choices; bold often marks question stems. Matching tables can supply the pairs. Never invent a missing key. Record unresolved questions and ask only for information needed to resolve them.

## Structure and numbering

Preserve source order and activity boundaries unless asked otherwise. A numbering-only request means renumber existing themes sequentially in their existing order, update child numbers consistently, and normalize punctuation and spacing in numeric prefixes. Do not merge split themes, reorder topics, rename descriptive text, or rewrite content. Duplicate source numbering is not permission to restructure.

Keep a task-local manifest of observed course/activity/page URLs, original titles, expected content, source keys, counts, and planned changes. Reobserve the course before resuming; a timed-out submit may have succeeded, so do not recreate activities blindly.

## Authoring

Read [Lesson workflow](references/lesson-workflow.md) for authoring, imports, HTML, images, and navigation details. For file-based student submissions, read [Assignment workflow](references/assignments.md). For comprehensive testing, read [Course audit](references/audit.md).

Use semantic HTML with readable headings, paragraphs, lists, and restrained inline styles. Preserve meaning, tables, and illustrations. Compress bitmap images to practical web dimensions before embedding; large base64 HTML can break the browser-control connection. Do not claim complete image fidelity after checking only text.

Verify published content, page order, question types, all keys and scores, correct/incorrect jumps, theory buttons, and lesson endings. Distinguish configured scores and teacher-preview behavior from actual student-grade persistence. A sample check is not a full functional audit.

Remove superseded resources only within the user's scope and after verifying their replacements. Honor the tool's deletion rules; unrelated course content is outside the scope of replacement.

## Browser continuity and reporting

If the user wants the browser left open, call `markHandoff()` before ending each unfinished turn, or `markDeliverable()` for a finished course view. Marks are turn-scoped. Retain the existing tab for routine recovery. After an explicit disconnect, use current inventory: a new browser ID may retain the same provider tab ID. Never store credentials, session keys, user identities, or student records in this reusable skill.

Report concrete counts, the scope of testing, unresolved exceptions, and a course link. Never present an interrupted migration or audit as complete.
