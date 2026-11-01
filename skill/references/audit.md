# Course audit

## Inventory and inspect configured grading

Inventory all native Lessons and internal pages in the edit view. Save observed preview/edit URLs and expected order. Count information pages separately from questions.

«Режим отображения» → «Развернуто» exposes all page contents, answers, scores, and jumps in tables. Read the dropdown's actual `mode=full` URL and navigate to that observed URL if selection alone does not navigate. This avoids opening every question form merely to inspect configured grading.

Read the rendered DOM tables and compare every source question against: its text and variants, single/multiple answer type, complete key, each score and jump, and matching pairs with aggregate correct/incorrect scores. Also check maximum grade, custom scoring, minimum questions, attempt/retry handling, and end behavior.

Configured scores do not prove final grade scaling. Teacher preview can say «Показать оценки (только для студентов)». Report that limit unless an authorized student-mode test verified actual grades; do not modify existing students' attempts or grades.

## Functional testing

Click every information-page «Далее» and compare the resulting page ID to the next manifest page. A last page must complete the Lesson. Immediate snapshots may still show the previous document after clicking; use documented `waitForURL(expectedUrl, ...)` before diagnosing a broken transition.

For a full functional audit, submit the correct answer set for every question in teacher preview. Check single choice, multiple choice, and matching separately. Exercise wrong, incomplete, and extra-option responses as needed to establish rejection/scoring behavior. Do not claim every answer combination was tested when only correct submissions and representative wrong cases were exercised.

After submitting, verify the intended feedback/continue control or next page. Verify the last question reaches completion. Record per-page/question pass/fail, inspected settings, fixes, and unresolved issues in a local report without credentials or session keys.

## Content and numbering

Compare published source fragments and inspect preserved illustrations. For numbering changes, identify headings by activity/page identity rather than a global prefix replacement: duplicate source numbers can belong to different topics. Update activity titles, internal page titles, and displayed HTML headings together. A numbering-only request leaves prose, answers, ordering, and activity boundaries intact.

Before completion, re-inventory the course, capture a result screenshot, and keep the browser open when requested.
