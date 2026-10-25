---
type: agent-ecosystem-item
category: plugin
scope: VS Code 用户环境
status: installed
created: 2026-10-26
last_verified: 2026-10-26
tags:
  - agent-ecosystem
  - plugin
  - mermaid
  - vscode
---

# Mermaid Preview：本地预览与功能迁移

> [!abstract] 核心结论
> Mermaid Preview 2.2.0 专注于免账号的本地预览；账号、云端同步和 AI 功能已迁移到另一个名为 **Mermaid** 的扩展。截图显示的是功能迁移说明，不是报错。已确认本机存在这两个扩展的安装文件，但未核验启用、登录或当前 Agent 可调用状态。

## 分类与用途

- 类型：VS Code 插件。
- 用途：手写 Mermaid 图表的本地预览、语法高亮、Markdown 渲染与图片导出。
- 状态：`installed`；仅确认本机安装文件，不标为 `configured` 或 `available`。
- 归属：[[20_领域/AgentHarness管理/插件/插件索引]]。这是现用插件的管理参考，不作为已停用资料放入归档区。

## 范围与来源

- 范围：当前 Windows 用户的 VS Code 扩展安装目录；不是仓库依赖或项目配置。
- 信息来源：2026-10-25 用户提供的 VS Code 截图，编辑器标签为 `MermaidPreviewChanges.md`。
- 原文定位：Mermaid Preview 2.2.0 随包文档 `docs\MermaidPreviewChanges.md`，标题为 **What Changed in Mermaid Preview**。
- 来源核验：2026-10-25 已核对本机文档与 GitHub 上游原文；2026-10-26 归档时重新读取本机文档及两个扩展的清单，未重新访问线上来源。

## 安装位置与兼容性

| 角色 | 本机显示名称 | 扩展 ID | 已核验版本 |
|---|---|---|---|
| 截图对应的扩展 | Mermaid Preview | `vstirbu.vscode-mermaid-preview` | `2.2.0` |
| 承接云端与 AI 功能的扩展 | Mermaid | `MermaidChart.vscode-mermaid-chart` | `2.8.2` |

本机取证位置：

- Mermaid Preview 安装目录：`C:\Users\LGX\.vscode\extensions\vstirbu.vscode-mermaid-preview-2.2.0`。
- 截图原文：`C:\Users\LGX\.vscode\extensions\vstirbu.vscode-mermaid-preview-2.2.0\docs\MermaidPreviewChanges.md`。
- Preview 版本与发布者证据：同一安装目录下的 `package.json`。
- Mermaid 安装目录：`C:\Users\LGX\.vscode\extensions\mermaidchart.vscode-mermaid-chart-2.8.2`。
- Mermaid 显示名称、版本与发布者证据：其安装目录下的 `package.json`。

两个扩展清单中的 VS Code 版本要求均为 `^1.77.0`。上述路径是本机证据位置，不是 vault 附件或可移植依赖；升级、切换配置档案或换设备后应重新定位。

## 功能分工与使用建议

| 需求 | 应使用的扩展 |
|---|---|
| 手写图表、实时预览、Markdown 渲染、PNG/SVG 导出 | Mermaid Preview 即可 |
| 登录账号、云端保存、关联项目、同步与冲突检测 | Mermaid |
| AI 聊天、AI 辅助生成或重新生成图表 | Mermaid |

本机已存在迁移目标 Mermaid 2.8.2 的安装文件，无需仅因这条提示重复安装。需要云端或 AI 功能时，应核对 Mermaid 是否启用及账号是否登录，并从该扩展入口操作；继续调用 Mermaid Preview 的旧同步命令只会显示迁移提示。

## 原文中文翻译

以下为随包公告的完整中文翻译；此节保留公告语境，不将其中的安装步骤理解为本机尚未安装。

### Mermaid Preview 有哪些变化

#### Mermaid Preview 2.2.0

**Mermaid Preview 现在是一个仅用于本地预览的扩展。**

所有需要 Mermaid 账号的功能，都已迁移到 **Mermaid** 扩展。要继续使用这些功能，请安装该扩展。

### 已迁移到 Mermaid 扩展的功能

以下功能已不再属于 Mermaid Preview：

- **Sync Diagram｜同步图表**：将图表保存回你的 Mermaid 账号。
- **Connect Diagram｜关联图表**：将本地图表关联到一个 Mermaid 项目。
- **Link Diagram｜链接图表**：在代码中插入 Mermaid 图表 ID。
- **Login / Logout｜登录／退出登录**：Mermaid 账号与登录功能。
- **Cloud diagram browser｜云端图表浏览器**：在侧边面板中浏览 Mermaid 项目和图表。
- **Download diagram｜下载图表**：将云端图表下载到编辑器。
- **Refresh｜刷新**：重新同步云端图表列表。
- **Smart sync & conflict detection｜智能同步与冲突检测**：比较本地版本与远程版本。
- **AI chat & Regenerate Diagram｜AI 聊天与重新生成图表**：使用 AI 辅助生成图表。

如果你在 Mermaid Preview 中运行这些命令，只会显示一条提示，不会实际执行同步、关联或链接操作。

### 仍然保留，仍在本地使用

Mermaid Preview 保留所有无需账号即可使用的功能：

- 实时预览图表，支持平移、缩放和重置。
- 导出为 **PNG** 和 **SVG**。
- 在 Markdown 预览中显示 Mermaid 图表。
- 自动识别 Markdown、HTML、Hugo 和 reStructuredText 中的 Mermaid 内容块，并提供 **Edit Diagram｜编辑图表** 链接。
- 为 `.mmd` 和 `.mermaid` 文件提供语法高亮。
- 在空文件中提供图表模板，输入时提供代码片段。
- **Create Diagram｜创建图表**和 **Diagram help｜图表帮助**。
- 本地侧边栏首页与预览设置。
- 主题、最大缩放比例、文本大小上限和边数上限设置。

### 如何继续使用已迁移的功能

1. 从 VS Code 扩展市场安装 **Mermaid** 扩展。
2. 登录你的 Mermaid 账号。
3. 在该扩展中，继续使用同步、关联、链接和云端侧边面板等功能。

### 现在只会显示迁移提示的命令

| 原命令 | 功能迁移位置 |
|---|---|
| **Mermaid Preview: Sync Diagram** | Mermaid 扩展 |
| **Mermaid Preview: Connect Diagram** | Mermaid 扩展 |
| **Mermaid Preview: Link Diagram** | Mermaid 扩展 |

## 权限与数据边界

- Preview 的本地预览不需要 Mermaid 账号，但“本地预览”不等于扩展绝不联网。随包 `README.md` 的 Settings 部分说明，**Share usage analytics** 默认开启；关闭后停止记录和发送使用分析及日志，且受 VS Code 自身遥测设置约束。本次未读取或修改用户的实际开关值。
- Mermaid 的云端工作流涉及账号与远端图表读写，不属于仅本地的预览流程；使用前应核对授权及服务的数据政策。AI 功能的账号、额度和依赖条件以当前官方说明为准，本次未实际调用。
- 本次仅读取非敏感的扩展元信息与文档；未登录账号、执行同步、上传图表或改动扩展及用户配置，不保存凭据。

## 验证记录

- **2026-10-25**：通过截图中的文档名定位本机原文，并读取 GitHub 上游同名文件，内容一致。
- **2026-10-26**：重新读取两个本机 `package.json`，确认 Mermaid Preview `2.2.0`、Mermaid `2.8.2` 及显示名称；重新读取迁移公告和 Preview 的遥测说明。
- **未核验**：扩展是否启用、当前使用的配置档案、Mermaid 登录状态、账号权限、云端连接和当前 Agent 工具可调用性。其他配置档案、组织策略和远程服务不在此次核验范围内。

## 来源与关联

- [GitHub 原文：What Changed in Mermaid Preview（固定提交）](https://github.com/vstirbu/vscode-mermaid-preview/blob/f46f40aa93f02d05496a8d1ba1a4da7ebd202622/docs/MermaidPreviewChanges.md)
- [Mermaid Preview 扩展市场页面](https://marketplace.visualstudio.com/items?itemName=vstirbu.vscode-mermaid-preview)
- [Mermaid 扩展市场页面](https://marketplace.visualstudio.com/items?itemName=MermaidChart.vscode-mermaid-chart)
- [[20_领域/AgentHarness管理/插件/插件索引]]
- [[20_领域/AgentHarness管理/管理总览]]
- [[30_资源/开发工具/VS_Code]]
