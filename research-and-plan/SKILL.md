---
name: research-and-plan
description: 强制执行深度研究与详尽计划的工作流。适用于大型重构、复杂 Bug 修复或涉及多个文件相互依赖的架构调整。在执行任何具有破坏性或大规模的代码改动前，必须使用此技能。
---

# Research and Plan (Ultraplan)

此技能旨在模仿 Claude Code 的 Ultraplan 工作流，通过强制性的研究和审批流程，提高 Agent 在复杂工程任务中的成功率。

## 核心工作流

在执行任何非平凡的代码修改前，你必须遵循以下三个阶段：

### 阶段 1：深度研究 (Deep Research)
在提出任何方案前，你必须具备 100% 的确定性。
- **依赖分析**：使用 `grep_search` 查找你要修改的函数、类或变量的所有调用点。
- **逻辑确认**：使用 `read_file` 阅读相关逻辑，确保理解副作用和边界情况。
- **禁止猜测**：如果对某个文件或库的用法不确定，禁止生成代码，应先通过 `web_fetch` 或 `glob` 进一步调研。

### 阶段 2：制定详尽计划 (The Plan)
生成一份包含以下部分的 Markdown 计划，并展示给用户：
1. **目标 (Objectives)**：清晰描述此任务要解决的最终问题。
2. **改动方案 (Proposed Changes)**：列出将要修改、创建或删除的具体文件及对应的逻辑点。
3. **风险评估 (Risks & Precautions)**：列出可能导致的副作用（如破坏向下兼容性、性能下降）以及你的规避手段。
4. **验证方案 (Verification)**：描述你将如何测试这些改动（例如：运行哪个测试用例、执行哪个 Shell 命令）。

### 阶段 3：用户审批 (Approval)
- **强制停顿**：展示计划后，必须询问用户：“您是否批准此计划？如果需要调整，请告知我。”
- **禁止先行**：在用户明确回复“批准”、“确认”或类似指令前，禁止调用任何修改工具（如 `replace`, `write_file`, `run_shell_command` 的非只读命令）。

## 输出预算管理 (Micro-compaction)

为了防止上下文溢出，你在执行研究工具时应遵循以下准则：
- **巨量输出处理**：如果 `grep_search` 或 `run_shell_command` 的输出超过 2000 行或 50,000 字符，**禁止直接展示全部内容**。
- **自动摘要**：你应该先将输出重定向到临时文件，或者分块读取，并向用户提供一个“技术摘要”，提取关键报错信息或代码片段。
- **相关参考**：详细处理逻辑请查阅 [references/micro-compaction.md](references/micro-compaction.md)。

---
*Inspired by Claude Code Ultraplan Workflow*
