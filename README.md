# Gemini CLI Ultraplan 🚀

[English](./README.md) | [中文](./README.zh-CN.md)

> An ultimate enhancement skill pack for Gemini CLI, inspired by the core design principles of Claude Code.

This project aims to bring the state-of-the-art **Task Orchestration (Ultraplan)** and **Context Management (Micro-compaction)** mechanisms from `Claude Code (v4.6)` into the Gemini CLI ecosystem by reverse-engineering and auditing its core architecture.

---

## 🌟 Core Features

- **Ultraplan Workflow**: Enforces a three-stage process of "Deep Research -> Strategic Planning -> User Approval," completely eliminating blind operations by the Agent.
- **Micro-compaction**: Automatically summarizes massive tool outputs (such as large `grep` results or build logs), keeping sessions smooth and increasing context efficiency by up to 10x.
- **Model-Aware Scheduling**: Optimizes inference effort allocation based on Gemini 2.0+ capabilities.
- **Crash-Resistant Persistence**: Proactively synchronizes session state before critical API calls to ensure recoverability in extreme cases.

## 📂 Project Structure

```text
gemini-cli-ultraplan/
├── research-result.md      # Technical report on auditing Claude Code
├── research-and-plan/      # Core skill source code
│   ├── SKILL.md            # Skill instruction set
│   └── references/         # Enhancement logic guide
└── LICENSE                 # Apache 2.0 License
```

## 🚀 Quick Installation

1. **Clone the repository**:
   ```bash
   git clone https://github.com/your-username/gemini-cli-ultraplan.git
   cd gemini-cli-ultraplan
   ```

2. **Install the skill**:
   ```bash
   # Recommended for global user scope
   gemini skills install ./research-and-plan --scope user
   ```

3. **Reload skills**:
   In an interactive Gemini CLI session, run:
   ```bash
   /skills reload
   ```

## 🛠️ Usage

When facing large-scale refactors or complex bugs, simply tell Gemini CLI:
> "Enable the **research-and-plan** skill to perform this task."

It will automatically switch to "Senior Engineer Mode," providing you with detailed research reports and change plans.

## 📜 Technical Background

This project is based on deep research into the `Claude Code` source code, with key references to its `QueryEngine` fault-tolerance mechanisms and `toolOrchestration` parallel partitioning logic. For details, please refer to [research-result.md](./research-result.md).

## 📄 License

This project is licensed under the [Apache License 2.0](./LICENSE).

---
*Created with ❤️ by Gemini CLI Assistant*
