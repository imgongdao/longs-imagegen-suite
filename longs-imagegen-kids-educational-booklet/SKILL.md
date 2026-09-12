---
name: "longs-imagegen-kids-educational-booklet"
description: "多略生图儿童教育小册子：为儿童制作多页图文教育小册子。用于练习册、学习卡片、习惯或生活技能指南、阅读或自然拼读材料及其他连续教育页面；不用于单张通用视觉化图片。"
metadata:
  version: "1.0"
---
<!-- Copyright 2026 GongDao · Longs（多略）· Longs.xyz · Apache-2.0 -->

# 多略生图儿童教育小册子

Use case: `longs-imagegen-kids-educational-booklet`  
Runtime: Codex Agent  
Parent: `references/Longs-ImageGen-HARNESS.md`

## Shared Harness
Before planning, rendering, editing, or delivery, MUST read and follow `references/Longs-ImageGen-HARNESS.md` as the shared base specification for this Longs image-generation suite. Then apply this Skill's asset-specific rules according to the instruction priority defined by the Harness.

## 1. Scope

MUST route here when the final asset is a child-facing educational booklet, workbook, learning card series, habit guide, life-skill guide, reading/phonics booklet, method-training booklet, or multi-page illustrated teaching asset.

MUST NOT route here for a single generic explainer unless continuity, child pedagogy, or workbook interaction is required.

## 2. Runtime

Execute:

`INTAKE → BOOKLET_PLAN → PAGE_PLAN → CONTENT_LOCK → PATTERN_SELECT → STYLE_LOCK → CHARACTER_LOCK → RENDER → INSPECT → PATCH → SERIES_PASS → DELIVER`

Follow Harness instruction priority, reference roles, invariants, edit protocol, and universal QC.

## 3. Load References

MUST load as needed:

- `references/booklet-spec.md`
- `references/teaching-patterns.md`
- `references/page-patterns.md`
- `references/visual-language.md`
- `references/character-system.md`
- `references/illustration-language.md`
- `references/typography-layout.md`
- `references/style-modes.md`
- `references/qc-checklist.md`

MUST treat user-provided successful booklet samples as `style reference + composition reference + quality reference`, not as literal templates unless explicitly requested.

## 4. Booklet Plan

Before rendering any page, MUST establish:

`audience_age | learning_goal | booklet_thesis | page_count | page_sequence | page_roles | style_mode | character_system | recurring_visual_tokens | output_ratio`

MUST plan the full booklet before Page 1 rendering.

MUST assign each page one `page_thesis` that can be restated in one sentence.

MUST give each page one dominant teaching job:

`introduce | define | diagnose | compare | demonstrate | sequence | classify | practice | review | summarize`

SHOULD use progressive sequencing:

`recognize → understand → imitate → practice → recall → apply`

NEVER create pages that repeat the same teaching job without adding new cognitive value.

## 5. Page Plan

For every page compile:

`page_number | page_role | page_thesis | title | core_message | teaching_points | page_pattern | illustration_plan | text_blocks | interaction | recurring_tokens | constraints`

MUST select one primary page pattern; MAY combine one secondary pattern only when hierarchy stays obvious.

MUST convert abstract ideas into observable behavior, concrete objects, actions, comparisons, sequences, or simple visual metaphors.

MUST keep visual reading order explicit from top to bottom or left to right.

## 6. Content Lock

Before render, MUST lock all final copy:

- title;
- subtitles;
- labels;
- steps;
- examples;
- English words;
- phonics chunks;
- numbers and units;
- quiz/options;
- footer summary.

All locked copy is verbatim.

NEVER improvise extra educational claims, examples, slogans, labels, or decorative pseudo-text during rendering.

When source content is dense, MUST reduce, split, or move content across pages before shrinking text.

## 7. Style Lock

MUST select one `style_mode` for the booklet unless the user explicitly requests mixed styles.

MUST lock across all pages:

`medium | line language | character proportions | color logic | paper/background treatment | icon language | border language | shadow logic | illustration detail level`

Default style when unspecified: `Chinese Watercolor Picture Book Style` using `Longs Kids Default` visual language.

NEVER change art medium, character rendering, palette family, or layout vocabulary between pages without narrative reason.

## 8. Character Lock

MUST establish a character bible before first page containing:

`count | role | age band | gender/presentation | face | hair | skin tone | body proportion | clothing | palette | signature details | expression range`

Character gender is unrestricted: boy, girl, mixed children, siblings, parent-child, teacher-child, or no recurring child.

MUST preserve identity and design across pages.

If user provides character/reference images, follow Harness identity rules and use them only for assigned reference roles.

NEVER silently alter age, face, hairstyle, clothing palette, body proportion, or signature details.

## 9. Render Rules

MUST render page-by-page from locked page specs.

MUST preserve empty space around major text blocks.

MUST use illustrations to teach, not decorate.

MUST make the main action/object understandable without reading every line.

MUST keep child-facing complexity appropriate to the audience age.

SHOULD prefer 1 main scene or 2–6 clearly separated teaching modules per page.

NEVER use dense poster composition, tiny captions, fake handwriting, random English, unrelated cute objects, or decorative clutter.

## 10. Text Fidelity

Treat text as instructional content, not visual texture.

MUST inspect every visible character after render.

MUST verify Chinese characters, English spelling, phonics chunks, punctuation, numbers, units, labels, and step order against `CONTENT_LOCK`.

MUST patch any incorrect text before delivery.

For text-critical pages, SHOULD prefer deterministic text placement/overlay when runtime capabilities allow and native render cannot pass text QC reliably.

## 11. Series Consistency

After individual page QC, MUST run a full-series pass checking:

`character consistency | title hierarchy | palette | page margins | box/border system | recurring icons | illustration scale | numbering | text density | teaching progression | page rhythm`

MUST lock accepted pages as visual references for subsequent pages when useful.

NEVER allow later pages to drift into a different book.

## 12. Patch

Patch one defect class at a time.

Priority:

`factual/teaching error > text error > character drift > reading-order error > layout overflow > visual inconsistency > illustration defect > decoration`

MUST preserve already accepted regions and series-wide invariants.

NEVER regenerate the entire booklet to repair a local defect unless structure itself is invalid.

## 13. Delivery

Deliver only final approved page assets and requested compiled outputs.

MUST keep page order deterministic and filenames sortable:

`<booklet-slug>-p01`, `<booklet-slug>-p02`, ...

If multiple variants exist, append style or format after page number.
