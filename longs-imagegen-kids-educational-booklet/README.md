# 多略生图儿童教育小册子

**英文技能名称：`longs-imagegen-kids-educational-booklet`**

用于将儿童教育内容转化为结构化、图文结合、适合儿童阅读与学习的教育小册子。

这是多略生图 Harness 体系中的一个独立 Skill。  
执行逻辑由 `SKILL.md` 定义，具体的视觉、角色、版式、教学与质量规则存放在 `references/` 目录中。

## Structure

```text
longs-imagegen-kids-educational-booklet/
├── README.md
├── SKILL.md
├── agents/
│   └── openai.yaml
└── references/
    ├── Longs-ImageGen-HARNESS.md
    ├── booklet-spec.md
    ├── character-system.md
    ├── illustration-language.md
    ├── page-patterns.md
    ├── qc-checklist.md
    ├── style-modes.md
    ├── teaching-patterns.md
    ├── typography-layout.md
    └── visual-language.md
```

## Files

- `SKILL.md`：Skill 主执行文件。
- `agents/openai.yaml`：Codex 界面的中英文显示名称、简短说明与默认调用示例。
- `references/Longs-ImageGen-HARNESS.md`：随 Skill 分发的共享基础规范副本，保证独立安装时可读取。
- `references/booklet-spec.md`：教育小册子的整体规格。
- `references/character-system.md`：角色一致性与人物系统。
- `references/illustration-language.md`：插画表达规则。
- `references/page-patterns.md`：页面结构与常用页面模式。
- `references/qc-checklist.md`：质量检查清单。
- `references/style-modes.md`：可选视觉风格模式。
- `references/teaching-patterns.md`：教学内容组织模式。
- `references/typography-layout.md`：字体与版式规则。
- `references/visual-language.md`：整体视觉语言。
- `README.md`：用于 GitHub 和人工阅读，不承担执行逻辑。

## Versioning

文件名保持稳定，不在文件名中加入版本号。  
版本历史由 Git / GitHub 管理。
