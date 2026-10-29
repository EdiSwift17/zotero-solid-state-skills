# Zotero 固态电池文献 Skills

两个用于 Codex 的中文 Agent Skills，帮助固态电池研究者在 Zotero 中遴选、归档和深读论文。

| Skill | 用途 |
| --- | --- |
| [`zotero-paper-deep-read`](skills/zotero-paper-deep-read/SKILL.md) | 阅读指定论文的正文及可用补充材料，按四部分十项撰写深度解析，并保存为 Zotero 子笔记。 |
| [`zotero-solid-state-paper-curation`](skills/zotero-solid-state-paper-curation/SKILL.md) | 每次选择一篇合格的固态电池论文，获取可合法访问的正文和补充材料，归档到 Zotero，并调用上述深读流程。 |

## 前提

- 安装 Zotero Desktop，并在运行环境中提供可用的 Zotero 读写能力。Skill 优先使用可用的 Zotero 连接器；若连接器不支持创建子笔记，需能操作 Zotero 原生界面。
- 深读需要论文全文；涉及补充材料时，也需要可访问的对应文件。选文 Skill 需要联网检索和下载公开可获取的论文。
- 这些 Skill 是工作流说明，不包含 Zotero 插件、论文 PDF、定时任务或自动运行服务。是否能写入 Zotero 取决于运行环境提供的工具和权限。

## 安装

将仓库中 `skills/` 下的两个目录复制到本机的 `~/.codex/skills/`，保留各自的 `SKILL.md` 和附属文件：

```bash
git clone https://github.com/EdiSwift17/zotero-solid-state-skills.git
cp -R zotero-solid-state-skills/skills/zotero-paper-deep-read ~/.codex/skills/
cp -R zotero-solid-state-skills/skills/zotero-solid-state-paper-curation ~/.codex/skills/
```

安装后在 Codex 中明确点名使用，例如：

```text
使用 $zotero-paper-deep-read 深读 Zotero 中 DOI 为 ... 的论文，并写入子笔记。
```

```text
使用 $zotero-solid-state-paper-curation 推荐一篇近六个月的钠电池卤化物固态电解质论文，归档到 Zotero 并深读。
```

`zotero-solid-state-paper-curation` 的深读步骤依赖 `zotero-paper-deep-read`，因此建议同时安装。Skill 内的分类名称、下载目录和研究方向可按个人工作流调整。

## 使用边界

论文筛选、文献来源和量化结论都需要回到原文核验。遇到付费墙或访问控制时，这两个 Skill 要求使用合法可获取版本，并如实报告缺失材料。它们不会自动绕过访问限制，也不会把仅有摘要的阅读报告称为全文深读。

## 反馈

欢迎通过 GitHub Issues 提出勘误、适配建议和改进方案。请勿在 Issue 中上传受版权保护的论文全文、私人 Zotero 数据或访问凭证。
