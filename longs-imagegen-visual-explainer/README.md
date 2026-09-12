# 多略生图视觉化图片

**英文技能名称：`longs-imagegen-visual-explainer`**

用于将文章、笔记、框架、流程、对比、要点或其他结构化信息，转化为更容易理解、记忆和分享的视觉化解释图片。

这是多略生图 Harness 体系中的一个独立 Skill。  
执行逻辑由 `SKILL.md` 定义，具体的品牌规则、生成配方与视觉呈现模式存放在 `references/` 目录中。

## Structure

```text
longs-imagegen-visual-explainer/
├── README.md
├── SKILL.md
├── agents/
│   └── openai.yaml
└── references/
    ├── Longs-ImageGen-HARNESS.md
    ├── brand-rules.md
    ├── recipes.md
    └── style-modes.md
```

## Files

- `SKILL.md`：Skill 主执行文件。
- `agents/openai.yaml`：Codex 界面的中英文显示名称、简短说明与默认调用示例。
- `references/Longs-ImageGen-HARNESS.md`：随 Skill 分发的共享基础规范副本，保证独立安装时可读取。
- `references/brand-rules.md`：多略生图视觉化图片的品牌与解释性视觉规则。
- `references/recipes.md`：可复用的视觉化解释生成配方。
- `references/style-modes.md`：可选视觉表面与呈现模式。
- `README.md`：用于 GitHub 和人工阅读，不承担执行逻辑。

## Versioning

文件名保持稳定，不在文件名中加入版本号。  
版本历史由 Git / GitHub 管理。
