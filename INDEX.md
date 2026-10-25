---
type: index
status: active
created: 2026-10-24
tags:
  - index
  - knowledge-base
---

# 本库目录

> [!abstract] 导航用途
> 本页维护智能体库的当前目录与内容入口。两库分工与组织方法见 [[PLAN]]，修改约束见 [[AGENT]]。

## 根目录入口

- [README](README.md) — 阅读入口与根目录文件分工
- [[PLAN]] — 目标、管理范围与组织方法
- [[AGENT]] — 修改约束与变更联动
- [[90_系统/变更记录]] — Agent 工作日志与变更索引，每日一篇、条目精确到分钟

## 按分区浏览

| 分区 | 入口 |
|---|---|
| 收集 | [[00_收集/收集箱说明]] |
| 项目 | [[10_项目/项目区说明]] |
| 领域 | [[20_领域/领域区说明]] |
| 资源 | [[30_资源/资源区说明]] |
| 归档 | [[40_归档/归档区说明]] |
| 系统 | [[90_系统/系统说明]] |

## 进行中的项目

- [[10_项目/个人知识库首轮整理/项目总览|个人知识库首轮诊断与试点整理]] — 辅佐个人知识库开展首轮诊断与试点；进度与文档分工在项目内维护。
  - [[10_项目/个人知识库首轮整理/个人知识库全文研读]] — 本轮纯文本阅读覆盖、综合理解与语义保护。
  - [[10_项目/个人知识库首轮整理/两库差异与优缺点]] — 两库角色、组织、优缺点与辅助维护建议。
  - [[10_项目/个人知识库首轮整理/研读记录/README|研读记录与过程]] — 文档清单、分区与汇总台账、分区报告及执行核验过程。

## 会话记录

- [[90_系统/会话记录/2026-10-25_2115_暂存与提交|2026-10-25 · 暂存与提交]] — 仅处理本库本地提交，不推送远端。
- [[90_系统/会话记录/2026-10-25_2036_知识库探索|2026-10-25 · 知识库探索]] — 派生会话；承接个人知识库的理解、诊断与辅助整理方向。
- [[90_系统/会话记录/2026-10-25_2024_Agent维护|2026-10-25 · Agent 维护]] — 原会话；承接本库文档职责、Agent 工作日志与会话摘要机制。

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
│   ├── 个人知识库整理经验沉淀.md
│   ├── 收集箱说明.md
│   └── 智能体自定义能力变化与快照.md
├── 10_项目/
│   ├── 个人知识库首轮整理/
│   │   ├── 研读记录/
│   │   │   ├── README.md
│   │   │   ├── library-document-inventory.csv
│   │   │   ├── reading-agent-coverage.json
│   │   │   ├── reading-personal-coverage.json
│   │   │   ├── reading-structure-coverage.json
│   │   │   ├── reading-structure-manifest.csv
│   │   │   ├── reading-structure-report.md
│   │   │   ├── reading-timeline-coverage.json
│   │   │   ├── reading-timeline-manifest.csv
│   │   │   ├── reading-timeline-report.md
│   │   │   ├── reading-topics-coverage.json
│   │   │   ├── reading-topics-manifest.csv
│   │   │   └── reading-topics-report.md
│   │   ├── 两库差异与优缺点.md
│   │   ├── 个人知识库全文研读.md
│   │   ├── 任务看板.md
│   │   ├── 现状诊断.md
│   │   ├── 试点与验收.md
│   │   └── 项目总览.md
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
│       ├── work.docx
│       ├── 个人知识库维护.md
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
│   ├── README早期记录_2026-06至07.md
│   └── 归档区说明.md
├── 90_系统/
│   ├── 会话记录/
│   │   ├── 2026-10-25_2024_Agent维护.md
│   │   ├── 2026-10-25_2036_知识库探索.md
│   │   └── 2026-10-25_2115_暂存与提交.md
│   ├── 变更记录/
│   │   ├── 2026-10-24.md
│   │   ├── 2026-10-25.md
│   │   └── 2026-10-26.md
│   ├── 流程图/
│   │   └── CODE_PARA_工作流程.mmd
│   ├── 模板/
│   │   ├── Agent能力条目模板.md
│   │   ├── 每日笔记模板.md
│   │   ├── 项目笔记模板.md
│   │   └── 通用笔记模板.md
│   ├── Agent工作日志说明.md
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
- [[20_领域/知识管理/知识管理]] — 智能体库与个人知识库的长期管理、工作记录和回顾
- [[20_领域/知识管理/个人知识库维护]] — 个人知识库 `data_Lgx` 的辅助维护标准、操作边界和阶段项目承接
- [[30_资源/版本控制/Git]] — Git 与 Git Bash
- [[30_资源/开发工具/VS_Code]] — VS Code
- [[30_资源/方法论/VibeCoding]] — Vibe Coding

## 历史资料

- [[40_归档/README早期记录_2026-06至07]] — 原入口中的 2026 年 6 至 7 月维护与学习记录，不作为现行规则。

## 工具与模板入口

- CODE + PARA 流程图：[CODE_PARA_工作流程.mmd](90_系统/流程图/CODE_PARA_工作流程.mmd)。
- 模板：[[90_系统/模板/通用笔记模板]]、[[90_系统/模板/项目笔记模板]]、[[90_系统/模板/每日笔记模板]]、[[90_系统/模板/Agent能力条目模板]]。
- Agent 日记：[[90_系统/Agent工作日志说明]]；Daily Notes 与变更记录共用每日文件。
