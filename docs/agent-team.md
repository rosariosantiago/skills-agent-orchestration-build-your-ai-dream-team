# Agent team

I will use the following custom agent team to build Mona's Project Pulse dashboard with GitHub Copilot CLI in a Codespace.

- **Orchestrator** (`Claude Opus 5.5 (copilot)`) - Coordinates the specialist agents, converts the implementation plan into ordered phases, assigns non-overlapping file scopes, and verifies the integrated result. Its definition lives at [.github/agents/orchestrator.agent.md](../.github/agents/orchestrator.agent.md).
- **Planner** (`Claude Opus 5.5 (copilot)`) - Researches the repository and requirements, identifies dependencies and edge cases, and produces a practical, file-assigned implementation plan without writing code. Its definition lives at [.github/agents/planner.agent.md](../.github/agents/planner.agent.md).
- **Designer** (`Gemini 3.7 Flash (copilot)`) - Owns the dashboard's UI/UX, accessibility, responsive layout, information hierarchy, and visual styling, including project cards, status badges, priority treatment, and deterministic CSS hooks. Its definition lives at [.github/agents/designer.agent.md](../.github/agents/designer.agent.md).
- **Coder** (`GPT-5.5 (copilot)`) - Implements assigned application code and support configuration, follows existing patterns, and validates behavior and runnable setup. Its definition lives at [.github/agents/coder.agent.md](../.github/agents/coder.agent.md).

The orchestrator gets the plan from the Planner, delegates work to the Designer and Coder in non-overlapping phases, runs dependent work sequentially, and combines their results into Mona's Project Pulse dashboard.
