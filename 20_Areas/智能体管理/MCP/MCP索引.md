---
type: index
status: active
last_verified: 2026-10-24
tags:
  - agent-ecosystem
  - mcp
---

# MCP 索引

## 来源分析

区分客户端配置、服务提供方及会话注册，不把工具可见性当作仓库已保存配置或凭据。

## 功能分析

连接工具与数据服务；MCP 是接入方式，不代表全部工具均由 MCP 提供，连接、认证与调用须分别核验。

## 当前核验

2026-10-26：本会话工具检索可见 GitHub MCP，未实测认证、远程调用及配置来源。

## 历史清单

以下为原 2026-10-24 记录；原标注的 `available` 不能代替本轮远程调用核验。

### 原可见 MCP Server

| MCP Server | 来源范围 | 当前状态 | 配置发现 | 备注 |
|---|---|---|---|---|
| GitHub MCP Server | 当前会话运行时 | `available`；工具由会话注册表提供 | 当前会话工具名使用 `github-mcp-server-*` | 不代表个人或仓库保存了 Server 凭据/配置 |

#### GitHub MCP 暴露的工具

`actions_get`、`actions_list`、`get_commit`、`get_copilot_space`、`get_file_contents`、`get_job_logs`、`issue_read`、`list_branches`、`list_commits`、`list_copilot_spaces`、`list_issues`、`list_pull_requests`、`pull_request_read`、`search_code`、`search_issues`、`search_pull_requests`、`search_repositories`、`search_users`。

#### 已检查的配置来源

| 配置来源 | 本次观察 |
|---|---|
| 工作区 `.vscode/mcp.json` | 不存在 |
| VS Code 用户 `%APPDATA%\Code\User\mcp.json` | 文件存在但为 0 字节，未配置 Server |
| Copilot CLI `%USERPROFILE%\.copilot\config.json` | 可见 `firstLaunchAt` 元数据；不是 Server 清单，本次未读取其他配置值 |
| 当前会话注册表 | 提供 GitHub MCP Server；这是本次能确认可用的会话能力 |
| 其他 VS Code 配置档案、组织/远程服务 | 未完全访问，标为未核验 |

`.github/instructions/mermaid.instructions.md` 提到 Mermaid 相关 LM 工具，但本次会话工具发现没有暴露这些名称，故不能视为当前可调用的 MCP 工具。

管理入口：[[20_Areas/智能体管理/模块列表]]、[[20_Areas/智能体管理/当前快照]]。
