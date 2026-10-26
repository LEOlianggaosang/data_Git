---
type: index
status: active
last_verified: 2026-10-24
tags:
  - agent-ecosystem
  - hooks
---

# Hooks 索引

## 来源分析

可能来自仓库、用户、插件或宿主策略，须核对事件配置与实际运行时契约。

## 功能分析

在指定生命周期事件执行动作；不同运行时的事件、载荷与失败策略不可混用，也不等同于 Git 提交诊断开关。

## 当前核验

2026-10-26：已检查的仓库配置未见项目生命周期 Hook；[[90_系统/系统说明#会话记录|显式保存规则]]已采用，自动 Hook 未启用，其他来源不据此判定不存在。

## 历史清单

以下为原 2026-10-24 记录，不代表本轮重新验证。

### 原核验状态

本仓库未发现 `.github/hooks/`、项目自定义 `.agent.md` 或 Agent 生命周期 Hook 定义；已检查的 VS Code 内置用户配置档案也未发现自定义 Agent 文件。其他配置档案、组织策略和宿主级 Hook 尚未完全盘点。

`.vscode/settings.json` 中的 `git.diagnosticsCommitHook.enabled: true` 是 VS Code Git 提交诊断设置，不是 Copilot Agent 生命周期 Hook；两类 Hook 应分别记录。

| Hook | 来源范围 | 触发阶段 | 状态 | 配置文件 |
|---|---|---|---|---|

管理入口：[[20_领域/智能体管理/模块列表]]、[[20_领域/智能体管理/当前快照]]。
