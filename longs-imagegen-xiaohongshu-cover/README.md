# 多略生图小红书封面图

**英文技能名称：`longs-imagegen-xiaohongshu-cover`**

用于生成多略的小红书竖版封面图。

这是多略生图 Harness 体系中的一个独立 Skill。  
执行逻辑由 `SKILL.md` 定义，具体规则与可复用配方存放在 `references/` 目录中。

## Structure

```text
longs-imagegen-xiaohongshu-cover/
├── README.md
├── SKILL.md
├── agents/
│   └── openai.yaml
└── references/
    ├── Longs-ImageGen-HARNESS.md
    ├── brand-rules.md
    └── recipes.md
```

## Files

- `SKILL.md`：Skill 的主执行文件。
- `agents/openai.yaml`：Codex 界面的中英文显示名称、简短说明与默认调用示例。
- `references/Longs-ImageGen-HARNESS.md`：随 Skill 分发的共享基础规范副本，保证独立安装时可读取。
- `references/brand-rules.md`：多略生图小红书封面图的品牌与视觉规则。
- `references/recipes.md`：可复用的小红书封面生成配方。
- `README.md`：仅用于 GitHub 和人工阅读，不承担执行逻辑。

## Versioning

文件名保持稳定，不在文件名中加入版本号。  
版本历史由 Git / GitHub 负责管理。
