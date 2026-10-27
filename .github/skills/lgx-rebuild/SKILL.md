---
name: lgx-rebuild
description: '重建系列的只读前置检查。用户调用 lgx-rebuild 或要求检查是否为新工作树时，确认当前为 Git 附加工作树，并检查根目录是否存在五项白名单之外的条目。'
user-invocable: true
disable-model-invocation: true
---

# lgx-rebuild

重建系列的前置技能，唯一职责是判断当前工作树是否满足起始条件。全部流程在本文件内，仅依赖 Git 元数据和目录枚举，不读取库内正文、规则、导航、日志、其他技能或脚本。

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

3. 返回结果后结束：

   - **通过**：附加工作树身份有效，额外条目为空。
   - **不通过**：身份不符合，或存在额外条目；说明原因并列出已检查到的额外条目名称及文件／目录类型。
   - **检查失败**：Git、权限或枚举错误导致无法完成判断；报告实际错误，不伪装成通过或已确认不符合。

   每次反馈包含实际检查路径、结论和原因；未完成的身份或目录检查明确标注“未检查”，不以空清单冒充已核验无额外条目。

## 边界

全程只读，不删除、清空、创建、修改或修复任何条目，不写入导航或日志，不提交或推送。通过仅表示此前置条件满足，不代表授权重建，也不自动调用系列中的后续技能。
