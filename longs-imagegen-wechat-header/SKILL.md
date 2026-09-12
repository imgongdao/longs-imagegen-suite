---
name: "longs-imagegen-wechat-header"
description: "多略生图微信公众号头图：创建或优化适合移动端识别、点击和突出文章核心观点的横版编辑型封面。用于微信公众号头图、封面或首图；小红书封面、视频封面、正文信息图、长图及 Logo 任务应交由其他对应技能。"
metadata:
  version: "1.0"
---
<!-- Copyright 2026 GongDao · Longs（多略）· Longs.xyz · Apache-2.0 -->

# 多略生图微信公众号头图

## Shared Harness
Before planning, rendering, editing, or delivery, MUST read and follow `references/Longs-ImageGen-HARNESS.md` as the shared base specification for this Longs image-generation suite. Then apply this Skill's asset-specific rules according to the instruction priority defined by the Harness.

## 0. Reference loading
- ALWAYS read `references/brand-rules.md` before a new generation or major redesign.
- AFTER classifying the article, read `references/recipes.md` and select the closest recipe; combine at most two recipes.
- For a narrow edit to an approved image, do NOT recompose from recipes unless the user asks for redesign. Preserve the existing composition and repeat edit invariants.
- This skill does not replace the base image-generation skill. Use the base imagegen workflow for generate/edit mode, image-role labeling, literal text handling, reference-image roles, invariants, and targeted iteration.

## 1. Mission
Create one strong 微信公众号头图 for 多略.
Optimize in this order:
1. topic recognition;
2. sharp article thesis;
3. mobile click-through;
4. authority / credibility;
5. visual polish.

The image is an editorial argument, not decoration.
The viewer should understand both **what this is about** and **what the article is saying** within 1–2 seconds.

## 2. Trigger
Use for:
- 微信公众号头图
- 微信公众号封面图
- 公众号首图
- 微信文章横版封面
- matching landscape cover for a 多略 article

Common content:
- AI news / product releases / outages / lawsuits / funding / policy
- company / model / platform comparison
- strategic commentary
- tools / workflows / 101 tutorials
- ecosystem maps
- benchmarks / scores / model capability shifts
- industry structure / methodology / concepts

Do not use for:
- 小红书封面
- 视频号/短视频封面
- 文章正文长信息图
- slide cover
- logo extraction
- transparent cutout

## 3. Output contract
- Deliver exactly ONE primary cover unless the user explicitly asks for variants.
- Raster bitmap.
- Default aspect ratio: **2.35:1**.
- Preferred working size: **1920×818** or another clean equivalent near 2.35:1; 1800×766 / 900×383 are acceptable equivalents.
- No watermark.
- No meaningless decorative frame around the entire image.
- Protect title, main face/object, and essential brand cue from edge cropping.
- Keep the dominant message readable in a compressed mobile preview.

## 4. Pre-generation parse
Extract internally:
- `topic`
- `article_title`
- `article_thesis`
- `content_type`
- `main_entities`
- `secondary_entities`
- `visual_evidence`
- `audience`
- `urgency`
- `emotional_temperature`
- `exact_text`
- `reference_images`
- `must_preserve`

Do not invent facts, scores, quotes, product names, or causal claims.
If the user supplies a sharp thesis, preserve it; do not neutralize it.

## 5. Content classification
Choose ONE primary class:
- `NEWS_ANALYSIS` — event + interpretation
- `CONFLICT_COMPARISON` — A vs B / competing strategies
- `BENCHMARK_DUEL` — capability / score / model comparison
- `ECOSYSTEM_FLOW` — split, merger, platform map, product family, migration
- `PERSON_POWER` — one executive/person + strategic action
- `TOOL_TUTORIAL` — 101 / how-to / workflow
- `FRAMEWORK_CONCEPT` — abstract thesis / method / architecture
- `INVESTIGATIVE_EVIDENCE` — hidden mechanism, watermark, proof, forensic angle
- `CINEMATIC_LAUNCH` — creative model / media model / visually dramatic release

## 6. Title policy
The headline is usually the strongest visual object.

Rules:
- Use the user's article title when it is already sharp.
- If too long for a cover, compress without changing the claim.
- Prefer 1–3 lines.
- Use one main title block; do not scatter the title into unrelated labels.
- Highlight only the most important 1–3 tokens/phrases with accent color.
- Chinese headline can mix English product/model names naturally.
- Product names, version numbers, people names, company names must be exact.
- Supporting copy is optional and subordinate.
- Do not convert a strong judgment into bland corporate wording.

## 7. Composition selection
Choose the layout from `references/recipes.md` after classification.
Default priority:
1. thesis-driven composition;
2. entity recognition;
3. visual explanation;
4. decoration.

Preferred visual structures:
- large headline + one hero anchor
- split-screen conflict
- two portraits framing a center mechanism
- central product / model node + competitors
- source platform -> branching / merging destinations
- portrait + evidence card / policy context
- forensic object + magnifier / detection interface

Do not default to a generic centered poster.
Do not use a random collage.

## 8. Visual anchor rules
Pick the fastest-recognition anchor:
1. central person, when the person's action is the story;
2. product/model identity, when the product is the story;
3. relationship diagram, when the relationship is the story;
4. evidence object, when proof/mechanism is the story;
5. grounded metaphor, only when literal entities are insufficient.

People:
- large enough to read emotionally;
- photorealistic / editorial, not waxy or cartoonish;
- serious, analytical, forceful, or neutral expression by default;
- use pose and gaze to reinforce conflict or direction;
- one strong portrait beats multiple tiny portraits.

Brands:
- use recognizable official-like marks/colors when appropriate;
- brand identity supports the thesis, never replaces it;
- organize multiple brands hierarchically;
- do not create a logo sticker wall.

Interfaces / diagrams:
- use only to explain the article mechanism;
- simplify aggressively;
- no dense pseudo-UI or unreadable microtext.

## 9. Prompt compiler
Use short labeled lines. Fill only relevant fields.

```text
Use case: 多略微信公众号头图
Primary request: [what cover to create]
Canvas: landscape 2.35:1, mobile-first WeChat article cover
Content class: [classification]
Audience: [audience]
Article thesis: [sharp verdict / why it matters]
Title (verbatim): "[exact cover title]"
Supporting text (optional): "[short subordinate line]"
Main entities: [people / companies / products / objects]
Visual anchor: [one dominant anchor]
Layout recipe: [recipe name]
Style / medium: [editorial / cinematic / tech-business / forensic / instructional]
Composition: [hierarchy and placement]
Color direction: [dominant neutral + brand accents]
Typography: [large bold headline, highlighted tokens]
Evidence / mechanism: [arrows / cards / UI / chart / magnifier / architecture, only if useful]
Constraints: [exact text, safe margins, recognizable entities, no watermark]
Avoid: [generic sci-fi, clutter, pastel softness, tiny text, random props, logo wall]
```

## 10. Reference image roles
When images are provided, label roles explicitly:
- `Image 1: edit target`
- `Image 2: face/reference likeness`
- `Image 3: logo/brand reference`
- `Image 4: composition/style reference`

Do not assume every reference is an edit target.
For an approved existing cover, edit only requested elements and preserve all stated invariants.

## 11. First-pass QC
Reject or repair if any answer is NO:
- Is the topic obvious in 1–2 seconds?
- Is the article's thesis visible, not merely the subject?
- Is the title the first or second strongest object?
- Is there one dominant focal anchor?
- Does every major visual element carry meaning?
- Are brand colors used intentionally rather than decoratively?
- Are faces/products/logos recognizable enough?
- Is the image mobile-readable?
- Is the visual density organized rather than chaotic?
- Does it look like serious tech/business editorial media rather than stock art?

## 12. Repair loop
Make targeted edits; do not restart without reason.

Failure -> repair:
- title weak -> enlarge, shorten, increase contrast, remove competing elements
- topic unclear -> strengthen main entity / brand / evidence anchor
- thesis unclear -> visualize conflict, direction, cause, evidence, or consequence
- generic -> add article-specific mechanism/evidence
- too empty -> add structured explanatory layer, not decoration
- too crowded -> remove third-tier labels / duplicate logos / low-value UI
- too fantasy -> ground in real editorial materials, photography, UI, devices, architecture
- too dark -> lift local contrast behind title/face without flattening the mood
- brand mismatch -> restore brand-associated accents and official-like identity cues
- face weak -> improve likeness using the face reference; preserve composition
- text error -> re-render exact wording; simplify surrounding typography

Repeat invariants on every edit.

## 13. Delivery
Suggested project filename:
- `longs-imagegen-wechat-header-[topic-slug].png`
- `longs-imagegen-wechat-header-[topic-slug]-v2.png`

Do not overwrite an approved asset unless explicitly asked.

## 14. Hard boundaries
- NEVER make “beautiful but unclear” the target.
- NEVER add fake data or fake quotes to make the cover look richer.
- NEVER use abstract AI circuitry as the only story when concrete entities exist.
- NEVER force minimalism; 多略 covers may be information-rich when hierarchy remains strong.
- NEVER force visual density either; every element must earn its place.
- NEVER use soft, friendly, pastel lifestyle aesthetics as the default.
- NEVER dilute a sharp article position merely to look neutral.
