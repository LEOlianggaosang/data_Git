---
type: index
status: active
last_verified: 2026-10-24
tags:
  - agent-ecosystem
  - hooks
---

# Hooks 索引

登记 Copilot 及其兼容 Agent Harness 的生命周期 Hook，包括工作区、用户配置、Agent 内联 Hook 与扩展/托管来源。每条记录需描述触发阶段、执行命令、权限、失败策略和测试方式。

## 当前可核验状态

本仓库未发现 `.github/hooks/`、项目自定义 `.agent.md` 或 Agent 生命周期 Hook 定义；已检查的 VS Code 内置用户配置档案也未发现自定义 Agent 文件。其他配置档案、组织策略和宿主级 Hook 尚未完全盘点。

`.vscode/settings.json` 中的 `git.diagnosticsCommitHook.enabled: true` 是 VS Code Git 提交诊断设置，不是 Copilot Agent 生命周期 Hook；两类 Hook 应分别记录。

| Hook | 来源范围 | 触发阶段 | 状态 | 配置文件 |
|---|---|---|---|---|

新增或核验条目时遵循 [[20_领域/AgentHarness管理/管理总览]]，并使用 [[90_系统/模板/Agent能力条目模板]]。
