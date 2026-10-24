---
type: index
status: active
last_verified: 2026-10-24
tags:
  - agent-ecosystem
  - mcp
---

# MCP 索引

登记 Copilot 可访问的所有来源范围中的 MCP Server，不仅是本仓库配置。对每个服务记录发现来源、作用范围、连接/授权状态、暴露工具和数据边界；不要记录凭据值。

## 当前可见的 MCP Server

| MCP Server | 来源范围 | 当前状态 | 配置发现 | 备注 |
|---|---|---|---|---|
| GitHub MCP Server | 当前会话运行时 | `available`；工具由会话注册表提供 | 当前会话工具名使用 `github-mcp-server-*` | 不代表个人或仓库保存了 Server 凭据/配置 |

### GitHub MCP 暴露的工具

`actions_get`、`actions_list`、`get_commit`、`get_copilot_space`、`get_file_contents`、`get_job_logs`、`issue_read`、`list_branches`、`list_commits`、`list_copilot_spaces`、`list_issues`、`list_pull_requests`、`pull_request_read`、`search_code`、`search_issues`、`search_pull_requests`、`search_repositories`、`search_users`。

### 已检查的配置来源

| 配置来源 | 本次观察 |
|---|---|
| 工作区 `.vscode/mcp.json` | 不存在 |
| VS Code 用户 `%APPDATA%\Code\User\mcp.json` | 文件存在但为 0 字节，未配置 Server |
| Copilot CLI `%USERPROFILE%\.copilot\config.json` | 可见 `firstLaunchAt` 元数据；不是 Server 清单，本次未读取其他配置值 |
| 当前会话注册表 | 提供 GitHub MCP Server；这是本次能确认可用的会话能力 |
| 其他 VS Code 配置档案、组织/远程服务 | 未完全访问，标为未核验 |

`.github/instructions/mermaid.instructions.md` 提到 Mermaid 相关 LM 工具，但本次会话工具发现没有暴露这些名称，故不能视为当前可调用的 MCP 工具。

新增或核验条目时遵循 [[20_领域/AgentHarness管理/管理总览]]，并使用 [[90_系统/模板/Agent能力条目模板]]。
