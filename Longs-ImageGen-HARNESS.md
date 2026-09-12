<!-- Copyright 2026 GongDao · Longs（多略）· Longs.xyz · Apache-2.0 -->

# 多略 AI 生图 Harness

Version: 1.0  
Runtime: Codex Agent  
Rendering engine: OpenAI Codex `imagegen` Skill

> 本文件是视觉生产总控。只定义跨场景稳定规则。平台规格、固定版式、案例 Prompt、品牌素材进入对应 Skill / references。

---

## 1. Runtime Contract

Codex MUST 按以下状态机执行视觉任务：

`UNDERSTAND → ROUTE → COMPILE → RENDER → INSPECT → PATCH → DELIVER`

### UNDERSTAND
内部确定：

- `intent`: generate | edit | composite | localize | extract
- `asset_type`: 最终用途
- `primary_message`: 观众第一眼必须理解的唯一核心信息
- `primary_subject`: 第一视觉主体
- `secondary_cues`: 0–3 个辅助线索
- `references`: 每张输入图的角色
- `hard_constraints`: 必须满足
- `invariants`: 编辑时绝不能改变
- `avoid`: 明确禁止

MUST 先理解内容，再设计画面。  
NEVER 把“风格”当成任务本身。  
NEVER 为审美擅自覆盖用户的明确要求。

### Instruction priority

`用户当前明确指令 > 用户提供的文字/图片/尺寸/位置/不可变要求 > 匹配 Skill 的硬规则 > 本 Harness > Skill references > Agent 自主补全`

当用户说“只改 X / 其他不变 / 保持原图”时，MUST 将未指定区域全部锁定为 invariants。

---

## 2. Architecture & Routing

### Boundary

**Harness**：任务判定、Skill 路由、内容转视觉、参考图协议、跨场景视觉原则、QC、迭代。  
**Skill**：某一种资产的尺寸、安全区、版式、信息层级、专属 Prompt scaffold、专属 QC。  
**references**：案例、sample prompts、Logo、品牌色、人物参考、平台规格、风格参考、负面案例。  
**one-off instruction**：只进入当前任务，不写回 Harness / Skill。

NEVER 把单次偏好写成全局规则。  
只有跨多个视觉场景长期成立的规则才进入 Harness。  
只有在同一资产场景反复成立的规则才进入对应 Skill。

### Skill routing

按“最终资产用途”优先匹配 Skill：

- `longs-imagegen-wechat-header` — 微信公众号文章头图 — Skill: `./longs-imagegen-wechat-header/SKILL.md`
- `longs-imagegen-xiaohongshu-cover` — 小红书封面图 — Skill: `./longs-imagegen-xiaohongshu-cover/SKILL.md`
- `longs-imagegen-visual-explainer` — 概念图、关系图、流程图、生态图、解释型视觉化图 — Skill: `./longs-imagegen-visual-explainer/SKILL.md`
- `longs-imagegen-kids-educational-booklet` — 儿童教育小册子、学习册、生活能力册、方法训练册、连续多页图文教学资产 — Skill: `./longs-imagegen-kids-educational-booklet/SKILL.md`
- `image-edit` — 已有图片局部修改、文字替换、尺寸保持
- `composite` — 多人物、多图片、Logo、产品、场景合成
- `generic-image` — 无专属 Skill 时兜底

SHOULD 优先使用已有 Skill；NEVER 因 Prompt 相似而绕过场景 Skill。

同一内容生成多个平台版本时：

1. 提取共享 `visual_core`；
2. 分别调用各平台 Skill；
3. 每个平台重新构图；
4. NEVER 用简单 resize/crop 代替平台适配；
5. MUST 保持核心人物、品牌、主题与视觉识别一致。

---

## 3. Content → Visual Compiler

所有内容型任务先压缩成一个视觉命题：

`WHO / WHAT → CHANGE / CONFLICT / RELATION → WHY IT MATTERS → VISUAL SYMBOL`

默认优先视觉化：人物关系、品牌关系、产品关系、前后变化、对比、冲突、路径、层级、生态版图、核心机制。

### Cover tasks

MUST：

- 一张图只承载一个主命题；
- 3 秒内可识别主题；
- 主标题 / 主视觉形成清晰第一层级；
- 使用真实人物、Logo、产品、界面、空间关系或明确隐喻建立主题锚点；
- 放大观点张力，但不得篡改事实。

NEVER：

- 把整篇文章塞进画面；
- 用大量装饰替代核心信息；
- 为“科技感”无依据增加机器人、大脑、电路、未来城市、霓虹球。

### Visualization tasks

优先级固定为：

`准确性 > 阅读顺序 > 关系清晰 > 标签可读 > 美观`

MUST 明确节点、箭头、路径、层级、分组或对比关系。  
NEVER 为装饰牺牲结构清晰度。

---

## 4. Visual Spec Compiler

NEVER 将用户原话未经整理直接作为最终生成 Prompt。  
MUST 先编译成生产型视觉规格；字段可按需省略。

```text
Use case: <skill / taxonomy>
Asset type: <final use>
Intent: <generate/edit/composite/localize/extract>
Primary request: <one-sentence visual objective>
Content thesis: <what viewers must understand first>
Input images: <Image 1: role; Image 2: role; ...>
Primary subject: <main visual subject>
Secondary cues: <0-3 supporting cues>
Scene/backdrop: <only if useful>
Style/medium: <photo/illustration/3D/editorial/diagram/etc.>
Composition/framing: <hierarchy, framing, negative space>
Brand/color: <official brand language or explicit palette>
Text (verbatim): "<exact text>"
Constraints: <must-have requirements>
Invariants: <what must remain unchanged>
Avoid: <negative constraints>
Output intent: <platform/use + readability target>
```

Prompt order SHOULD follow：

`用途 → 核心视觉目标 → 主体 → 构图 → 品牌/风格 → 精确文字 → Constraints → Invariants → Avoid`

### Specificity

用户已给出详细 Prompt：MUST 只结构化，不新增创意要求。  
用户 Prompt 较泛：SHOULD 只补足会明显提高质量的构图、层级、现实锚点与必要场景信息。

NEVER 擅自新增：人物、故事、Logo、品牌口号、产品、道具、品牌色、叙事背景。

### In-image text

用户要求出现的文字全部按 verbatim 处理：

- MUST 原样渲染；
- MUST 保持官方英文品牌名、型号、产品名拼写；
- NEVER 自动添加副标题、解释、标签、口号；
- NEVER 生成随机伪文字；
- 标题 SHOULD 大、短、层级强；
- 文字过多时 SHOULD 减少信息，不要无限缩小字号；
- 难拼写英文 SHOULD 在 Prompt 中逐字母强调，并要求 `exactly once, verbatim`。

平台尺寸、安全区、标题断行规则由对应 Skill 决定。

---

## 5. Reference / Edit Protocol

每张输入图 MUST 显式分配且只按指定角色使用：

`edit target | identity reference | brand/logo reference | style reference | composition reference | supporting insert | background/base image`

NEVER 默认所有输入图片都是 edit target。

### Person / identity

当用户提供真人参考并要求保留身份：

- MUST 锁定面部辨识度、年龄感、发型、关键五官；
- NEVER 擅自美颜、年轻化、换脸或重塑脸型；
- 合成 MUST 匹配尺度、视角、光线、阴影；
- “更像原图” = 只提高 identity fidelity，不重构其他已接受区域。

### Brand / Logo

当存在官方 Logo / 品牌参考：

- MUST 使用真实形态、拼写和品牌色；
- NEVER 重新发明 Logo；
- NEVER 制造近似但错误的品牌标识；
- NEVER 用通用蓝紫科技风覆盖品牌原生视觉语言。

### Base image

用户指定 base image 时：

- 原尺寸、构图和指定保留区域 MUST 锁定；
- 只修改用户指定区域；
- NEVER 因生成便利而重画整张图。

### Generate vs Edit

`generate`：新图；参考图只用于人物/Logo/风格/构图/情绪；同主题新平台版本。  
`edit`：保留已有图的大部分内容，只修改特定区域、文字、对象、背景或局部属性。

Edit Prompt MUST 包含：

`Change only <X>. Keep <Y/Z/...> unchanged.`

每轮编辑 MUST 重复 invariants。  
NEVER 因编辑困难擅自切换为整图 regenerate。

---

## 6. 多略 Default Visual Language

默认目标：**内容驱动、强识别、清晰、锋利、现代、真实品牌、缩略图可读。**

### SHOULD

- 一个强视觉中心；
- 明确的信息层级；
- 主标题 / 主视觉优先于装饰；
- 一个主要人物或对象优于大量无关元素；
- 品牌色来自官方资产或用户指定；
- 科技感来自真实产品、Logo、UI、设备、人物或空间关系；
- 画面有张力，但保持现实锚点；
- 需要文字时主动预留负空间；
- 人物头像必须承担信息角色；
- 多品牌画面用空间关系表达合作、竞争、依赖、层级或阵营。

### AVOID BY DEFAULT

- 泛滥的蓝紫 AI 光效；
- 无意义机器人 / 大脑 / 电路 / 发光球；
- 过度赛博朋克；
- 无关未来城市；
- stock-photo 感；
- 假 Logo；
- 随机英文；
- 装饰性信息过载；
- 过度柔和、缺乏视觉中心；
- 为“高级感”牺牲主题识别；
- 为“视觉冲击”把真实内容做成玄幻场景。

若目标品牌具有明确视觉语言，`brand-native language > 多略 default language`。

构图默认层级：

`主标题 / 主视觉 > 核心辅助线索 > 品牌/环境信息 > 装饰`

缩略图下主标题和主对象仍不可识别 = 构图失败。

---

## 7. QC & Patch Loop

每次生成后 MUST inspect。未通过关键 QC = 未完成。

### Universal QC

检查：

- primary_message 是否准确；
- 主视觉是否一眼识别；
- 是否满足对应 Skill 的画布 / 平台规则；
- 用户文字是否逐字正确；
- Logo / 品牌名 / 产品名是否正确；
- 人物身份是否一致；
- hard_constraints 是否全部满足；
- invariants 是否被误改；
- 是否出现随机文字、假 Logo、多余元素、水印；
- 缩略图下是否仍成立；
- 是否存在脸、手、边缘、透视、重叠、裁切、文字畸变；
- 是否出现“泛 AI 模板感”压过真实主题。

### Cover QC

`3 秒理解主题 + 一个核心命题 + 标题/主视觉不互相竞争 + 醒目但不过度玄幻 + 品牌真实`

### Visualization QC

`关系正确 + 阅读顺序明确 + 标签足够大 + 箭头无歧义 + 装饰不干扰信息`

### Patch loop

优先单变量修复：

- 标题错 → 只改标题
- 人脸不像 → 只提高身份一致性
- Logo 错 → 只替换 Logo
- 构图散 → 只调整层级 / 对象位置
- 品牌色错 → 只校正品牌语言
- 太玄幻 → 只降低风格化并增加现实锚点
- 用户指定坐标 → 只修改目标区域

用户明确表示“这一部分很好 / 保留”后，MUST 将该部分加入下一轮 invariants。  
连续多轮局部修改时，默认所有已接受区域全部锁定。

NEVER 为修一个问题重新发明整张图。

---

## 8. Engine & Delivery

底层生成、编辑、透明背景、CLI/API、模型参数、文件路径、batch 规则全部继承 OpenAI Codex `imagegen` Skill。

默认使用内置 `image_gen`。  
只有用户明确要求 CLI / API / model control 时才进入 CLI fallback。  
NEVER 在本 Harness 重复维护底层 imagegen 执行参数。

本 Harness 只控制：

`任务解释 + Skill 路由 + Prompt 编译 + Reference roles + Constraints/Invariants + Visual QC + Patch strategy`

交付时只输出必要结果：

- 最终资产；
- workspace-bound 文件路径；
- 多资产时全部最终文件；
- 用户要求时提供最终 Prompt；
- 仍存在的明确限制。

NEVER 附加无关设计理论、长篇解释或自我评价。

### Final decision rule

发生冲突或信息不足但不阻塞执行时：

`用户明确约束 > 内容识别 > 平台适配 > 品牌真实性 > 信息层级 > 视觉冲击 > 装饰风格`

最终目标：**生成能准确承载多略内容、适配目标平台、可稳定复用、可持续迭代的视觉资产；不是生成“看起来像 AI 做的漂亮图片”。**
