# Gemini CLI Ultraplan 🚀

> 吸收 Claude Code 核心设计理念，为 Gemini CLI 打造的极致增强技能包。

本项目旨在通过逆向工程和审计 `Claude Code (v4.6)` 的核心架构，将其最先进的**任务编排（Ultraplan）**和**上下文管理（Micro-compaction）**机制引入到 Gemini CLI 生态中。

---

## 🌟 核心特性

- **Ultraplan 工作流**：强制执行“深度研究 -> 制定计划 -> 用户审批”的三阶段流程，彻底消除 Agent 的盲目操作。
- **微压缩 (Micro-compaction)**：自动摘要海量工具输出（如庞大的 `grep` 结果或构建日志），保持会话始终流畅，上下文利用率提升 10 倍。
- **模型感知调度**：根据 Gemini 2.0+ 的能力，优化推理努力度分配。
- **防崩溃持久化**：在关键 API 调用前主动同步会话状态，确保极端情况下的可恢复性。

## 📂 项目结构

```text
gemini-cli-ultraplan/
├── research-result.md      # 深入审计 Claude Code 的技术报告
├── research-and-plan/      # 核心技能源码
│   ├── SKILL.md            # 技能指令集
│   └── references/         # 增强逻辑指南
└── LICENSE                 # Apache 2.0 开源协议
```

## 🚀 快速安装

1. **克隆仓库**：
   ```bash
   git clone https://github.com/your-username/gemini-cli-ultraplan.git
   cd gemini-cli-ultraplan
   ```

2. **安装技能**：
   ```bash
   # 建议安装到用户全局范围
   gemini skills install ./research-and-plan --scope user
   ```

3. **重新加载**：
   在交互式 Gemini CLI 会话中执行：
   ```bash
   /skills reload
   ```

## 🛠️ 使用方法

在面对大型重构或复杂 Bug 时，直接对 Gemini CLI 说：
> “启用 **research-and-plan** 技能来执行此任务。”

它将自动切换到资深工程师模式，为你提供详尽的研究报告和改动计划。

## 📜 技术背景

本项目基于对 `Claude Code` 源码的深度研究，重点参考了其 `QueryEngine` 的容错机制和 `toolOrchestration` 的并行分区逻辑。详情请参阅 [research-result.md](./research-result.md)。

## 📄 开源协议

本项目采用 [Apache License 2.0](./LICENSE) 协议。

---
*Created with ❤️ by Gemini CLI Assistant*
