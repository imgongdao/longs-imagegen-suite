---
name: "longs-imagegen-visual-explainer"
description: "多略生图视觉化图片：把文章、笔记、框架、流程、比较、要点或其他结构化信息转化为易理解的单张位图视觉解释。适用于白板、餐巾纸草图、黑板、A4 注释页、桌面物件隐喻及悬浮 UI 等解释形式；不用于微信公众号头图、小红书封面、纯装饰海报或密集幻灯片。"
metadata:
  version: "1.0"
---
<!-- Copyright 2026 GongDao · Longs（多略）· Longs.xyz · Apache-2.0 -->

# 多略生图视觉化图片

## Shared Harness
Before planning, rendering, editing, or delivery, MUST read and follow `references/Longs-ImageGen-HARNESS.md` as the shared base specification for this Longs image-generation suite. Then apply this Skill's asset-specific rules according to the instruction priority defined by the Harness.

## 0. Required reference loading
ALWAYS read `references/brand-rules.md` before planning.
ALWAYS read `references/recipes.md` after classifying the task.
ALWAYS read `references/style-modes.md` before choosing a visual surface or presentation mode.
This skill MUST work from text-only input.
Reference images are optional aids, not prerequisites.

## 1. Mission
Create one visualized explanatory image that makes complex information easier to understand.
The image must do five things:
1. extract the true structure from the input;
2. show the relationships visually, not only verbally;
3. reduce cognitive load versus plain text;
4. keep text readable and concise;
5. feel polished enough to share publicly while remaining explanation-first.

Primary optimization target: comprehension speed.
Secondary optimization target: memorability.
Tertiary optimization target: visual polish.
Never sacrifice understanding for decoration.

## 2. What this skill is for
Use this skill when the user provides:
- an article to be visualized
- notes, bullets, or fragments to be turned into a visual explainer
- a process, workflow, or step-by-step logic
- a framework, thesis, or concept map
- a comparison that benefits from side-by-side display
- a list of takeaways, risks, opportunities, or lessons
- a breakdown of companies, products, models, or ecosystems
- a teaching use case where “showing” beats “telling”

Typical 多略 use cases:
- AI tool / workflow explanation
- strategy breakdown
- business model / market map
- company relationship diagram
- concept translation for creators and professionals
- tutorial support image
- article companion visual
- teaching image for self-media posts, courses, or whiteboard explanation

## 3. What this skill is not for
Do not use this skill for:
- 微信公众号头图
- 小红书封面图
- 16:9 video thumbnails
- dense multi-page slides
- exact chart reproduction when programmatic charting would be more accurate
- brand identity/logo design
- decorative concept art with little information value
- full long-form infographic posters with excessive tiny text

If the content is mostly persuasion and hook, route to a cover skill.
If the content is mostly explanation and structure, use this skill.

## 4. Top-level operating modes
Choose the correct mode first.

### Mode A: article-to-visual
Use when the user provides an article, paragraph set, or long explanation.
Task: extract the central structure, reduce the text, and convert it into one visual teaching image.

### Mode B: notes-to-visual
Use when the user provides bullets, fragments, or semi-structured notes.
Task: organize, group, and visualize them.

### Mode C: framework / concept visualization
Use when the input is an abstract idea, model, method, or thesis.
Task: create a clear explanatory structure with visual hierarchy.

### Mode D: process / workflow visualization
Use when the input is a sequence, operating procedure, or funnel.
Task: show steps, decision points, flows, and outputs.

### Mode E: comparison visualization
Use when the input compares options, companies, tools, or strategies.
Task: make differences obvious and organized.

### Mode F: edit / repair an existing explainer
Use when the user provides an existing visual and asks for changes.
Task: preserve what works; improve clarity and fidelity.

## 5. Core doctrine
The goal is not “make a pretty picture about the topic.”
The goal is “make the structure obvious.”

Therefore:
- extract before illustrating
- simplify before decorating
- group before styling
- label clearly
- show relationships explicitly
- prefer one central idea per image
- if there are too many ideas, choose the most decision-relevant subset

A useless failure mode is to paste many text boxes onto a pretty background.
Avoid that.

## 6. Required understanding before generation
Before generating, infer or extract these fields:
- source type
- core question the image should answer
- primary audience
- central message
- structure type
- key entities
- explanatory goal
- amount of detail appropriate for one image
- whether the image is stand-alone or a companion to an article/post
- whether exact text wording is important

Structure-type classification:
1. LIST
   - several takeaways or principles
2. FLOW
   - sequence or pipeline
3. COMPARISON
   - A vs B vs C
4. HIERARCHY
   - parent/child levels
5. MAP
   - ecosystem / landscape / grouped categories
6. CAUSE-EFFECT
   - inputs -> mechanisms -> results
7. LOOP
   - recurring cycle / feedback loop
8. MATRIX
   - 2-axis grouping / quadrant / categorization
9. STACK
   - layered architecture
10. SUMMARY
   - compressed article takeaway with several grouped sections

Audience defaults:
- Chinese creators, entrepreneurs, professionals, AI learners
- mobile and desktop readers
- limited patience for dense text
- want fast clarity and practical relevance

## 7. Output contract
Deliver exactly one primary image unless the user explicitly asks for multiple variants.

Default output requirements:
- bitmap image
- single-page visual explainer
- aspect ratio chosen according to content shape; common choices: 4:3, 3:4, 1:1, or 16:9
- readable text
- no watermark
- no cluttered edge crowding
- structured layout with obvious visual hierarchy

Text-density rule:
- the image must be skimmable
- never turn the image into a wall of text
- short labels and short callouts beat long paragraphs
- if too much material exists, summarize

## 8. Content compression rules
Before visualizing, compress the source.
Do not dump all input content into the image.

Compression sequence:
1. identify the one main thesis or teaching goal
2. identify 3–7 key blocks
3. reduce each block to a short label or short explanation
4. drop low-value detail
5. convert repeated language into one clear category
6. surface the relationships explicitly

Preferred content volume per image:
- 1 main title
- 3–7 major blocks
- 0–2 short lines per block on average
- optional legend or mini-note only if necessary

If more than 7 major blocks are truly needed:
- group them into clusters
- or ask the image to show only the most useful summary level

## 9. Visual-surface and style-mode selection
Choose one style mode based on the content and the likely best learning experience.
Do not choose randomly.
See `references/style-modes.md` for detailed rules.

Available style families:
- WHITEBOARD
- NAPKIN
- CHALKBOARD
- A4 PAPER
- DESKTOP / TABLETOP OBJECT EXPLAINER
- FUTURISTIC FLOATING UI
- CLEAN INFOCARD / LIGHT POSTER
- NOTEBOOK / STUDY PAGE

Selection rules:
- WHITEBOARD: best default for teaching, process, frameworks, grouped insights
- NAPKIN: best for fast idea sketch, entrepreneurial concept, rough-but-smart explanation
- CHALKBOARD: best for educational or classroom feel, formulas, principles, conceptual explanation
- A4 PAPER: best for clean article companion visuals, report summaries, and printable explainers
- TABLETOP OBJECT EXPLAINER: best when metaphor objects help memory
- FUTURISTIC FLOATING UI: best for AI, systems, dashboards, architecture, product relationships
- CLEAN INFOCARD / LIGHT POSTER: best when the result should be shareable and polished but not cover-like
- NOTEBOOK / STUDY PAGE: best for learning summaries and memory aids

## 10. Diagram grammar
Use visual grammar intentionally.
Possible devices:
- arrows
- grouping boxes
- connectors
- labels
- numbered steps
- icons
- object callouts
- brackets
- swimlanes
- before/after split
- quadrant axes
- stack layers
- input/output ports
- spotlight highlights

Rules:
- every connector must mean something
- arrows should indicate direction, causality, or sequence
- boxes should indicate grouping or modules
- icons should support recall, not replace meaning
- decorative 3D elements must not interfere with understanding

## 11. Text rules
Text is allowed and often necessary, but it must be compressed.

Text hierarchy:
- one clear title
- optional subtitle or framing question
- section headings
- brief labels / callouts
- optional tiny footnote only when necessary

Text rules:
- use short Chinese text by default
- keep wording direct and practical
- if the user provides exact terms or names, preserve them accurately
- if the text contains English brand or product names, keep them readable and correctly spelled
- avoid paragraph blocks
- avoid tiny unreadable details

## 12. Layout logic
Choose a layout that matches the structure type.

Layout mapping:
- LIST -> grouped cards or clustered board
- FLOW -> left-to-right or top-to-bottom sequence
- COMPARISON -> split columns or cards
- HIERARCHY -> tree or layered grouping
- MAP -> central theme with grouped clusters
- CAUSE-EFFECT -> chain or staged pathway
- LOOP -> circular flow
- MATRIX -> 2-axis grid or quadrant
- STACK -> layered architecture
- SUMMARY -> title + 3–6 section blocks

Never use a fancy layout that hides the logic.

## 13. Visual anchor strategy
A visual explainer may still need a main anchor.
Choose the best one:
1. central concept card
2. system diagram
3. object metaphor
4. illustrative scene background
5. person anchor, if the explanation revolves around a person or quote

Rule:
- if the concept is abstract, use a central structural anchor
- if the content concerns tools/systems, use product/system cards
- if the content is educational, use simpler, lighter anchors
- do not overuse portraits unless the person is core to comprehension

## 14. Style balance
The image should feel visual and helpful, not childish, not empty, and not overproduced.

Preferred qualities:
- clean
- explanatory
- structured
- smart
- slightly stylized
- easy to scan
- good contrast

Avoid:
- fantasy art replacing explanation
- noisy neon clutter
- walls of text
- excessive realism without information value
- too many unrelated decorative objects
- cheap clip-art energy

## 15. Inherited useful patterns from official imagegen references
Borrow and adapt the strongest official visual-explainer patterns:
- infographic-diagram
- scientific-educational
- ui-mockup when interface framing helps explanation
- clean poster-like educational structure

Do not blindly copy their verbosity.
Translate them into 多略-style visuals:
- clearer business value
- shorter text
- stronger practical framing
- more recognizable relation mapping

## 16. Prompt compiler
Use short labeled lines.
Do not write a bloated paragraph.

Recommended scaffold:
- Use case:
- Primary request:
- Source type:
- Audience:
- Teaching goal:
- Core question:
- Structure type:
- Title (verbatim):
- Key blocks:
- Visual surface / style mode:
- Visual anchor:
- Layout:
- Diagram grammar:
- Style / medium:
- Color direction:
- Typography:
- Constraints:
- Avoid:

Prompt rules:
- name the teaching goal explicitly
- state what the image should help the viewer understand
- define the structure type clearly
- list the key blocks or steps explicitly
- specify the chosen surface/mode
- specify exact title text when needed
- repeat readability and clarity constraints

## 17. Repair and iteration rules
Review the first output aggressively.
If it fails, do one focused repair pass.
Do not thrash randomly.

Common failures and fixes:
- too much text -> compress and remove low-value details
- pretty but unclear -> strengthen structure and labels
- structure wrong -> rebuild using the correct layout family
- background too dominant -> simplify the surface/background
- text too small -> enlarge headings and reduce block count
- relationships unclear -> add or clarify arrows, grouping, and labels
- too childish -> shift toward clean editorial or professional educational style
- too technical-looking for a simple concept -> simplify the visual grammar

Repeat invariants during repair:
- keep explanation-first
- keep the main thesis clear
- keep text readable
- keep visual hierarchy obvious
- keep the image skimmable

## 18. Quality checklist
Approve only if nearly all are true:
- the image clearly answers the central question
- the structure type is visually obvious
- the main idea is recognizable quickly
- relationships are easier to understand than in plain text
- the text is readable and not too dense
- the chosen style mode supports the explanation
- the image looks shareable and polished
- the image feels useful, not merely decorative
- no spelling errors, no watermark, no clutter

If the image is beautiful but not clearer than the source text, it failed.

## 19. Naming and delivery
Suggested filenames:
- longs-imagegen-visual-explainer-[topic-slug].png
- article-visual-[topic-slug]-v2.png
- framework-diagram-[topic-slug].png

Do not overwrite an approved existing asset unless explicitly asked.
Otherwise create a sibling versioned filename.

## 20. Boundary rules
This skill is specialized.
Do not turn every task into the same whiteboard template.
Do not maximize decoration while weakening understanding.
Do not treat “visualization” as “copying text into boxes.”
Do not force every output into a futuristic AI look.

The goal is not to impress the user with style.
The goal is to help the viewer understand faster and remember longer.
