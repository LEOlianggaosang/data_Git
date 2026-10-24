---
type: index
status: active
created: 2026-10-24
tags:
  - index
  - knowledge-base
---

# 本库目录

> [!abstract] 使用顺序
> 新资料先进入收集箱；整理时按项目、领域、资源或归档分流；需要输出时从对应项目或主题笔记开始。

## 根目录入口

- [[PLAN]] — 本库目标、CODE + PARA 工作方法及目录规划
- [[INDEX]] — 当前导航入口
- [[AGENT]] — 本库内容、路径与变更约束
- [README](README.md) — GitHub 与本库入口
- [[90_系统/变更记录]] — 本库更改历史

## 按行动浏览

| 分区 | 用途 | 入口 |
|---|---|---|
| 收集 | 尚未判断归属的新资料 | [[00_收集/收集箱说明]] |
| 项目 | 有明确结果和完成条件的限时工作 | [[10_项目/项目区说明]] |
| 领域 | 需要持续维护的责任 | [[20_领域/领域区说明]] |
| 资源 | 供未来查阅的知识、工具和方法 | [[30_资源/资源区说明]] |
| 归档 | 当前不活跃但仍要保留的内容 | [[40_归档/归档区说明]] |
| 系统 | 模板、日记、规则和维护记录 | [[90_系统/系统说明]] |

## 树状视图

```text
.
├── .github/
│   ├── copilot-instructions.md
│   └── instructions/
│       └── mermaid.instructions.md
├── .obsidian/
│   ├── app.json
│   ├── appearance.json
│   ├── core-plugins.json
│   ├── daily-notes.json
│   ├── hotkeys.json
│   ├── templates.json
│   └── workspace.json
├── .vscode/
│   └── settings.json
├── 00_收集/
│   └── 收集箱说明.md
├── 10_项目/
│   └── 项目区说明.md
├── 20_领域/
│   ├── AgentHarness管理/
│   │   ├── Harnesses/
│   │   │   └── Harnesses索引.md
│   │   ├── Hooks/
│   │   │   └── Hooks索引.md
│   │   ├── MCP/
│   │   │   └── MCP索引.md
│   │   ├── 插件/
│   │   │   └── 插件索引.md
│   │   ├── 技能/
│   │   │   └── 技能索引.md
│   │   ├── 工具/
│   │   │   └── 工具索引.md
│   │   ├── 指令/
│   │   │   └── 指令索引.md
│   │   ├── 智能体/
│   │   │   └── 智能体索引.md
│   │   └── 管理总览.md
│   ├── 领域区说明.md
│   └── 知识管理/
│       ├── 日记/
│       │   └── 日记说明.md
│       ├── work.docx
│       └── 知识管理.md
├── 30_资源/
│   ├── 开发工具/
│   │   ├── VS_Code.md
│   │   └── vscode.docx
│   ├── 方法论/
│   │   ├── VibeCoding.md
│   │   └── vibecoding.docx
│   ├── 版本控制/
│   │   ├── git.docx
│   │   ├── gitbash.docx
│   │   └── Git.md
│   └── 资源区说明.md
├── 40_归档/
│   └── 归档区说明.md
├── 90_系统/
│   ├── 流程图/
│   │   └── CODE_PARA_工作流程.mmd
│   ├── 模板/
│   │   ├── Agent能力条目模板.md
│   │   ├── 每日笔记模板.md
│   │   ├── 项目笔记模板.md
│   │   └── 通用笔记模板.md
│   ├── 变更记录.md
│   └── 系统说明.md
├── .gitignore
├── AGENT.md
├── INDEX.md
├── PLAN.md
└── README.md
```

## 主题索引

- [[20_领域/AgentHarness管理/管理总览]] — 跨工作区、用户配置、扩展与会话运行时的 Copilot 能力清单
- [[20_领域/知识管理/知识管理]] — 知识库维护、工作记录和日记
- [[30_资源/版本控制/Git]] — Git 与 Git Bash
- [[30_资源/开发工具/VS_Code]] — VS Code
- [[30_资源/方法论/VibeCoding]] — Vibe Coding

## Obsidian

- 本 vault 的配置仅位于仓库根目录 `.obsidian/`；嵌套 vault 的清理记录见 [[90_系统/变更记录]]。
- CODE + PARA 流程图：[CODE_PARA_工作流程.mmd](90_系统/流程图/CODE_PARA_工作流程.mmd)。
- [[90_系统/模板/通用笔记模板]]、[[90_系统/模板/项目笔记模板]]、[[90_系统/模板/每日笔记模板]]、[[90_系统/模板/Agent能力条目模板]] 可通过 Templates 插件使用。
- 日记位置为 `20_领域/知识管理/日记/`。
