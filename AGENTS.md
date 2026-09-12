# Longs Image Generation

This repository contains Longs image-generation assets for Codex.

For any image-generation task, first read and follow:

`./Longs-ImageGen-HARNESS.md`

Treat that file as the top-level visual production controller for this repository.

## Skill loading

When the Harness routes a task to a specialized Skill, load and follow the corresponding local Skill:

- `./longs-imagegen-wechat-header/SKILL.md`
- `./longs-imagegen-xiaohongshu-cover/SKILL.md`
- `./longs-imagegen-visual-explainer/SKILL.md`
- `./longs-imagegen-kids-educational-booklet/SKILL.md`

Each Skill may require its own files under `references/`.
Read those referenced files when the Skill instructs you to do so.

Each Skill also carries `references/Longs-ImageGen-HARNESS.md` so it remains
self-contained when installed independently. The repository-root Harness is
the canonical source; keep all four portable copies synchronized with it.

## Operating rule

Do not rewrite or override Harness or Skill logic in this file.
Use this file only as the repository entry point for instruction loading.
