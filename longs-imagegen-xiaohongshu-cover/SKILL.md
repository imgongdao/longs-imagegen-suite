---
name: "longs-imagegen-xiaohongshu-cover"
description: "多略生图小红书封面图：制作可独立使用、适合移动端信息流的单张竖版位图封面，以清晰标题层级和高辨识度在两秒内传达一个核心价值。已有微信公众号头图可作为可选风格参考，但不是前置条件；不用于微信公众号头图、视频封面、正文配图、长图信息图或透明背景素材。"
metadata:
  version: "1.0"
---
<!-- Copyright 2026 GongDao · Longs（多略）· Longs.xyz · Apache-2.0 -->

# 多略生图小红书封面图

## Shared Harness
Before planning, rendering, editing, or delivery, MUST read and follow `references/Longs-ImageGen-HARNESS.md` as the shared base specification for this Longs image-generation suite. Then apply this Skill's asset-specific rules according to the instruction priority defined by the Harness.

## 0. Required reference loading
ALWAYS read `references/brand-rules.md` before planning.
ALWAYS read `references/recipes.md` after classifying the request.
Treat external source images as optional inputs, not required prerequisites.
If a 微信公众号头图 exists, it is only an optional anchor.
This skill MUST still work when no prior cover exists.

## 1. Mission
Create one strong, stand-alone 小红书封面图 for 多略.
The cover must do five things at once:
1. stop the scroll in a mobile feed;
2. make the topic instantly recognizable;
3. make the benefit, conflict, warning, or sharp opinion visible in under two seconds;
4. remain readable on a small screen;
5. stay consistent with 多略’s editorial-business-tech visual language.

Primary optimization target: feed stop rate and click/open intent.
Secondary optimization target: clarity of takeaway.
Tertiary optimization target: visual polish.
Never sacrifice clarity for decoration.

## 2. Operating modes
This skill has three valid operating modes.
Choose the correct mode before planning.

### Mode A: stand-alone generation (default)
Use when:
- the user asks only for a 小红书封面图
- no approved 微信 cover exists
- no prior cover is provided
- the cover must be designed from the topic itself

Rule:
- this is the default mode
- do not assume there is a 微信 parent asset
- build the cover from the article topic, angle, entities, and 多略 brand rules

### Mode B: derived adaptation from a 微信 cover
Use when:
- the user provides or references an approved 微信公众号头图
- the user wants the 小红书 cover to follow that visual family

Rule:
- preserve thesis and useful brand/style choices
- recompute the layout for vertical mobile feed use
- never do a literal crop/stretch

### Mode C: edit / repair an existing 小红书 cover
Use when:
- the user provides an existing 小红书 cover and requests changes

Rule:
- preserve what already works
- change only what is necessary
- keep the format vertical and feed-native

## 3. When to use
Use this skill when the user asks for:
- 小红书封面图
- 小红书封面
- 小红书图文封面
- RED cover / Xiaohongshu cover
- a vertical cover for a 多略 article, post, analysis, tutorial, or opinion

Common 多略 use cases:
- AI news commentary
- company/model comparison
- product/tool interpretation
- course/tutorial promotion
- framework or viewpoint post
- practical creator/entrepreneur insight
- opinionated business-tech analysis

## 4. When not to use
Do not use this skill for:
- 微信公众号头图
- 16:9 video thumbnails
- detailed infographics or dense long posters
- article body diagrams
- pure logo assets
- transparent-background cutouts
- PPT covers
- feed carousels with multiple pages (unless explicitly requested)

## 5. Output contract
Deliver exactly one primary cover unless the user explicitly asks for multiple options.

Output requirements:
- bitmap image
- vertical 3:4 ratio
- preferred working size: 1080×1440 or 1242×1660
- optimized for mobile feed viewing
- no watermark
- no unnecessary borders

Safe-area rules:
- assume top and bottom UI overlays may visually compete with the cover
- keep critical headline text away from extreme top and bottom edges
- protect the main title, hero face/object, and the decisive cue in the central safe zone
- if a sticker/tag is used, it must not block the headline
- the cover must remain legible as a small feed thumbnail

## 6. Required understanding before generation
Before generating, extract or infer these fields.
If information is missing, infer conservatively.
Do not invent facts that alter the article’s meaning.

Required internal fields:
- topic
- post angle / verdict
- content type
- target audience
- main entities
- promise type
- urgency level
- emotional temperature
- source relationship
- whether exact text is provided

Source relationship values:
- stand-alone Xiaohongshu cover
- derived from approved WeChat cover
- modified from earlier Xiaohongshu cover

Promise-type classification:
1. BREAKDOWN
   - explain what happened / what it means
2. JUDGMENT
   - sharp viewpoint / contrarian take / verdict
3. COMPARISON
   - A vs B / different strategies / who wins
4. HOW-TO
   - practical tutorial / workflow / 101
5. LIST / TAKEAWAYS
   - 3 points / summary / key insights
6. WARNING / ALERT
   - risk, trap, outage, deception, hidden issue
7. OPPORTUNITY
   - growth hack, market gap, structural shift

Audience defaults:
- Chinese creators, entrepreneurs, professionals, AI learners, knowledge workers
- mobile-first readers with short attention spans
- willing to click when the value is obvious and immediate

## 7. Xiaohongshu-specific editorial rules
小红书 is not 微信公众号.
The cover must win in a fast-scrolling vertical feed.

Therefore:
- fewer words usually outperform longer headlines
- one strong hook is better than a complete summary
- one dominant face/object is better than many small elements
- the first visual read must happen almost instantly
- clarity beats completeness
- the cover must work even when seen for less than two seconds

Small-screen rule:
- if the headline cannot be understood in a glance on a phone, it is too complicated
- if several visual elements compete equally, simplify
- if the value proposition is hidden, rebuild hierarchy

Practicality rule:
- even when the topic is news or commentary, the cover should suggest actionable relevance
- users should feel “this is useful to me”, not merely “this is a headline”

## 8. Optional use of a prior 微信 cover
A 微信 cover is optional, not foundational.
If one exists and is approved, use it as a helpful anchor.
If none exists, proceed normally in stand-alone mode.

When a 微信 cover exists, use this transform logic:
1. keep the same thesis if it is strong
2. keep the same core entity set if they are effective
3. preserve the same color family unless vertical readability requires adjustment
4. compress the title into a shorter, more feed-native form
5. increase the dominance of the main face/object
6. reduce secondary details
7. re-stack composition vertically
8. amplify the one strongest hook

Typical transformations:
- long comparative title -> short verdict + smaller support line
- wide scene with two sides -> top/bottom or diagonal split vertical composition
- many logos -> one or two main logos + simplified support cues
- complex system illustration -> one anchor diagram + one short label

## 9. Stand-alone creation rules
When no 微信 cover exists, the skill must independently decide:
- what the actual hook is
- what the single best visual anchor is
- what the right title compression is
- what the best layout family is
- what support details to include or discard

Stand-alone priority order:
1. identify the sharpest usable angle
2. choose the fastest recognition anchor
3. compress the title for mobile feed use
4. choose the simplest effective layout family
5. add 1–3 support cues only if they strengthen the angle

Do not build a visually rich but strategically weak cover.
Do not wait for a 微信 cover to provide direction.

## 10. Text strategy
Text exists to stop the scroll and trigger the click.
Do not use the cover as a paragraph.

Default hierarchy:
- one main headline
- optional small support line
- optional small tag / label / topic chip

Text rules:
- main headline should be short, sharp, legible
- 6–18 Chinese characters per main line is usually workable; longer text requires careful line breaking
- support text must earn its place
- preserve meaning; compress wording
- if the user provides exact copy, keep the core wording and tone
- if the user only provides the article topic, generate a cover-worthy headline that matches the article angle

Typography rules:
- very large main title
- strong contrast
- 2–4 visual text blocks maximum
- avoid tiny explanatory paragraphs
- avoid long footnotes
- avoid visual clutter from too many stickers/badges

Text style options:
- bold blunt statement
- short question with a strong answer implied
- “X不是Y，而是Z” structure
- “A赢了/输了什么” structure
- “这才是关键” structure
- “真正影响在这里” structure
- “别被表象骗了” structure

## 11. Visual hierarchy
The cover should read in this order:
1. main headline
2. hero visual anchor
3. support clue / brand cue / comparison relation
4. optional small tag

Never let decoration outrank the message.
Never require the viewer to inspect the image for several seconds to understand it.

## 12. Layout families
Choose one family based on the content type.
Do not blend everything together.

### A. Big-title + one-hero cover
Use when:
- strong opinion
- warning
- single-company or single-model topic
- how-to or key insight post

Composition:
- oversized title on top/left/center stack
- one dominant person/object/product anchor
- one clean support region
- high-contrast background

### B. Vertical split comparison cover
Use when:
- A vs B
- strategy conflict
- winner/loser narrative

Composition:
- left/right diagonal split or top/bottom split
- two entities clearly separated
- short decisive title
- visible tension cue such as contrast, versus, or differentiated color systems

### C. Center-card / system cover
Use when:
- product architecture
- concept explanation
- platform relationships
- ecosystem overview

Composition:
- one central product/system block
- supporting flows/arrows/nodes around it
- title stacked around the key system
- cleaner than an infographic

### D. Portrait authority cover
Use when:
- a central founder/CEO/expert drives the story
- the article is mainly about one person’s move, thesis, or signal

Composition:
- large portrait
- short hard-hitting title
- one or two contextual cues only
- serious editorial feel

### E. Tutorial / 101 cover
Use when:
- educational content
- workflow explanation
- product onboarding

Composition:
- headline first
- product cue second
- benefit promise third
- cleaner, calmer, more instructional than drama-heavy news covers

### F. Evidence / alert cover
Use when:
- hidden issue, trap, proof, exposure, watermark, outage, scam, quota trap

Composition:
- headline first
- one evidence metaphor or UI-like proof panel
- sharp focus on the issue
- urgency without cheap sensationalism

## 13. Visual anchor selection
Pick the single fastest recognition anchor.
Priority order:
1. central real person
2. central brand/product identity
3. one concrete device/screen/system cue
4. one explanatory metaphor object
5. abstract background support

Rules:
- do not use abstract tech wallpaper as the whole story
- when a face matters, make it large and clean
- when a product identity matters, make it obvious
- when the story is abstract, choose one metaphor that explains, not several decorative metaphors
- if multiple entities appear, there must still be one primary anchor

## 14. Style and color system
Default style direction:
- strong editorial thumbnail
- business-tech
- clean but energetic
- high contrast
- polished, not messy
- contemporary creator-economy feel

Allowed energy:
- dramatic lighting
- HUD/UI overlays
- arrows, beams, split tension, cards, panels, scoreboards
- motion-like energy cues

Do not overdo:
- random neon noise
- empty sci-fi wallpaper
- childish emojis
- excessive stickers
- cheap social-media template clutter

Color rules:
- start from clarity
- use brand-associated colors if recognition benefits
- preserve readable contrast
- do not use more accent systems than needed
- align the color story with the main entity or thesis

## 15. Content-type guidance
### News / commentary
- communicate the verdict, not just the event
- one face or one company usually dominates
- title should feel urgent and useful

### Comparison
- make the difference obvious visually
- do not just show two logos; show the argument
- one side may be visually stronger if the article angle clearly favors it

### Tutorial / workflow
- benefit first
- tool identity second
- learning mood > conflict mood

### Framework / concept
- choose one clear metaphor or system block
- do not make a mini lecture slide

### Opportunity / warning
- sharpen the consequence
- make the reader feel the relevance immediately

## 16. Prompt compiler
Use short labeled lines.
Do not create one huge paragraph.

Recommended scaffold:
- Use case:
- Primary request:
- Canvas:
- Source relationship:
- Audience:
- Post angle:
- Hook:
- Title (verbatim):
- Optional support text:
- Main entities:
- Visual anchor:
- Layout family:
- Style / medium:
- Composition:
- Color direction:
- Typography:
- Constraints:
- Avoid:

Prompt rules:
- explicitly state whether the task is stand-alone, derived from 微信, or a repair edit
- if reference images are provided, label them by role
- explicitly say what must be noticed first
- explicitly request mobile readability
- if exact title text is required, quote it
- if adapting from 微信, specify what to preserve and what to simplify
- if no 微信 cover exists, state the cover must be independently optimized for 小红书 feed performance

## 17. Core reusable recipes inside the skill
### Recipe 1: stand-alone AI commentary cover
Use case: stand-alone Xiaohongshu editorial cover
Primary request: create a 小红书封面图 for a 多略 AI commentary post
Canvas: vertical 3:4 mobile cover
Source relationship: stand-alone Xiaohongshu cover
Audience: Chinese mobile readers tracking AI industry trends
Post angle: one clear, sharp verdict
Hook: make the conclusion obvious immediately
Title (verbatim): "[INSERT TITLE]"
Main entities: [person/company/model]
Visual anchor: strong portrait or company/product cue
Layout family: big-title + one-hero cover or portrait authority cover
Style / medium: editorial social thumbnail, clean, dramatic, useful
Composition: headline first, hero second, one support layer only
Constraints: topic recognition within 2 seconds; usable on a phone screen; no clutter
Avoid: generic AI wallpaper, paragraph-like text, weak focal point

### Recipe 2: stand-alone comparison / battle cover
Use case: stand-alone Xiaohongshu comparison cover
Primary request: create a 小红书封面图 comparing two AI companies, models, or strategies for 多略
Canvas: vertical 3:4 mobile cover
Source relationship: stand-alone Xiaohongshu cover
Audience: readers who want a fast takeaway from the comparison
Post angle: show the difference or winner/loser implication clearly
Title (verbatim): "[INSERT TITLE]"
Main entities: [A], [B]
Visual anchor: two entities with clear visual contrast
Layout family: vertical split comparison cover
Style / medium: dramatic editorial cover with clean hierarchy
Composition: short headline, sharp split, two entities separated, one decisive focal point
Constraints: both entities recognizable; argument visible; mobile readability high
Avoid: equal clutter on both sides, too many extra labels, messy collage

### Recipe 3: stand-alone tutorial / 101 cover
Use case: stand-alone Xiaohongshu tutorial cover
Primary request: create a 小红书封面图 for a 多略 how-to, workflow, or 101 post
Canvas: vertical 3:4 mobile cover
Source relationship: stand-alone Xiaohongshu cover
Audience: beginners and working professionals seeking practical help
Post angle: immediately show the practical benefit
Hook: fast promise of value or result
Title (verbatim): "[INSERT TITLE]"
Main entities: [tool / app / workflow cue]
Visual anchor: product cue or task metaphor
Layout family: tutorial / 101 cover
Style / medium: clean instructional social thumbnail with business-tech polish
Composition: strong title, clear product cue, simplified layout, very readable
Constraints: clarity over drama; cover must feel useful and accessible
Avoid: news-style chaos, small pseudo-UI, excessive scene complexity

### Recipe 4: derived from approved 微信 cover
Use case: Xiaohongshu cover adaptation
Primary request: create a 小红书封面图 for 多略 derived from an approved 微信公众号头图
Canvas: vertical 3:4 mobile cover
Source relationship: derived from approved WeChat cover
Audience: Chinese creators, entrepreneurs, and AI-interested professionals browsing 小红书
Post angle: preserve the same thesis as the source cover
Hook: compress the thesis into a sharper, faster-scanning cover hook
Title (verbatim): "[INSERT SHORT TITLE]"
Optional support text: "[ONLY IF NEEDED]"
Main entities: [same core entities as source]
Visual anchor: [best source anchor, made more dominant]
Layout family: [best vertical family]
Style / medium: strong editorial thumbnail, polished business-tech visual language
Composition: vertical recomposition, big headline, strong hero anchor, simplified support details, safe margins
Color direction: inherit the source palette family while improving feed contrast
Typography: oversized headline, clean hierarchy, mobile legibility first
Constraints: same story, same tone family, stronger feed readability, no clutter, no watermark
Avoid: literal crop/stretch of the 微信 banner, small unreadable text, too many tiny support elements

## 18. Repair and iteration rules
Review the first output aggressively.
If it fails the checklist, do one focused repair pass.
Do not thrash randomly.

Common fixes:
- title too long -> shorten and re-break lines
- topic not obvious -> strengthen main entity or hook
- cluttered -> remove secondary details
- weak feed presence -> enlarge title and hero anchor
- too generic -> inject topic-specific brand cues or argument cues
- too much text -> compress to one sharp statement + one small support line
- too similar to a 微信 banner when it should stand alone -> rebuild hierarchy from scratch
- visual mismatch with 多略 -> restore editorial-business-tech tone

Repeat invariants during repair:
- keep 3:4 vertical cover format
- keep mobile readability
- keep one obvious hook
- keep the article’s core angle
- keep a clean focal hierarchy

## 19. Quality checklist
Approve only if nearly all are true:
- the topic is recognizable immediately
- the benefit, conflict, or verdict is visible in under two seconds
- the main title is readable on a phone screen
- the cover has one dominant focal point
- the layout feels vertical-native, not a cropped banner
- the cover works even if no 微信 source existed
- any face/logo/product is recognizable enough
- the style matches 多略’s serious business-tech tone
- the cover would plausibly stop a feed scroll
- no spelling errors, no watermark, no junk clutter

If the answer is weak on scroll-stopping power or mobile readability, it is not done.

## 20. Naming and delivery
Suggested filenames:
- longs-imagegen-xiaohongshu-cover-[topic-slug].png
- red-cover-[topic-slug]-v2.png

Do not overwrite an approved existing asset unless the user explicitly requests replacement.
Otherwise create a sibling versioned filename.

## 21. Boundary rules
This skill is specialized.
Do not turn every 小红书 cover into the same template.
Do not require a 微信 cover.
Do not blindly copy a 微信 cover when one exists.
Do not maximize beauty while weakening the hook.
Do not confuse information density with value.

The goal is not to make a poster.
The goal is to make the right person stop, understand, and click.
