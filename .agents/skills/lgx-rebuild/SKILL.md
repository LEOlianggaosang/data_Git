---
name: lgx-rebuild
description: '重建系列的只读前置检查。确认当前为 Git 附加工作树且根目录仅含五项白名单；本次通过后立即交给 lgx-plan 恢复规划与声明结构，失败则停止。'
user-invocable: true
disable-model-invocation: true
---

# lgx-rebuild

重建系列的前置技能，检查职责仅为判断当前工作树是否满足起始条件。检查流程在本文件内，仅依赖 Git 元数据和目录枚举，不读取库内正文、规则、导航或日志；通过后的规划恢复显式交给 lgx-plan，不在本技能实现。

## 判定

本技能所称“新工作树”，必须同时满足：

- 当前目录就是已登记的 Git 附加工作树根目录，不是主工作树、普通克隆、子模块或工作树内的子目录。
- 根目录除 `.git`、`.github`、`.obsidian`、`.vscode`、`.gitignore` 外没有其他条目。

白名单表示允许存在，不要求五项齐全；`.git` 必须满足附加工作树身份核验。只看根目录的直接子项，不检查白名单目录的内部内容。其他点号项、带隐藏属性的项也算额外条目。不按创建时间、提交历史或 Git 状态推断“新”。

## 流程

1. 在当前目录只读核验身份，逐条检查命令是否成功：

   ```powershell
   Get-Location
   git --no-optional-locks rev-parse --show-toplevel
   git --no-optional-locks rev-parse --absolute-git-dir
   git --no-optional-locks rev-parse --git-common-dir
   git --no-optional-locks -c core.quotepath=false worktree list --porcelain
   ```

   将路径规范为 Windows 绝对路径后比较：当前目录等于工作树根目录；根目录 `.git` 为文件；Git 目录与公共 Git 目录不同；当前根目录在工作树列表中且不是首条主工作树记录。不满足则不通过，不自动切换目录或创建工作树。存在 `GIT_DIR`、`GIT_WORK_TREE`、`GIT_COMMON_DIR` 或 `GIT_INDEX_FILE` 环境覆盖而无法确认真实身份时，报告检查失败，不自行修改环境。

2. 身份通过后，用 `-Force` 枚举根目录，包含隐藏项：

   ```powershell
   $allowed = @('.git', '.github', '.obsidian', '.vscode', '.gitignore')
   $items = @(Get-ChildItem -LiteralPath '<已核验根目录绝对路径>' -Force -ErrorAction Stop)
   $extras = @($items | Where-Object { $_.Name -notin $allowed } | Sort-Object Name)
   ```

   使用实际核验的根路径，不使用示例占位符执行。仅比较条目名称，不递归、不跟随目录链接，不读取文件内容。枚举失败不能当作空目录。

3. 返回检查结果：

   - **通过**：附加工作树身份有效，额外条目为空。
   - **不通过**：身份不符合，或存在额外条目；说明原因并列出已检查到的额外条目名称及文件／目录类型。
   - **检查失败**：Git、权限或枚举错误导致无法完成判断；报告实际错误，不伪装成通过或已确认不符合。

   每次反馈包含实际检查路径、结论和原因；未完成的身份或目录检查明确标注“未检查”，不以空清单冒充已核验无额外条目。

4. 仅本次实际检查“通过”时，立即调用 lgx-plan，将规范绝对根路径、通过结论及已核验的空额外条目清单作为交接输入，进入其恢复模式。调用前明确说明接下来会由 lgx-plan 写入 PLAN.md，并通过对应技能接口尝试补齐六大英文目录与五大根文件；未实现的接口只报告待实现，不自行代建。本系列已授权该接续，不再重复询问是否启动。

   不通过或检查失败时停止，不交接。用户明确要求只检查时仅返回结果；lgx-plan 未安装、无法加载或宿主不支持接续时，报告“前置检查通过，规划恢复未启动”及实际原因，不冒充恢复完成，也不在此复制其实现。技能定义中的接续不是后台监听器或 Hook，实际宿主调用能力仍需实测。

## 边界

前置检查本身全程只读，不删除、清空、创建、修改或修复条目，不写入导航或日志，不提交或推送。自动后续仅限已声明的 lgx-plan 规划与结构恢复，不授权恢复历史正文或其他重建动作；其写入及失败由 lgx-plan 独立报告。
