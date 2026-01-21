# LLM Orchestration System

A multi-agent development framework for managing complex software projects through coordinated subagents and llm-driven reviews. This lets an agent work an a dependency tree of tasks; it reviews its own work in a fresh context to produce more reliable output that requires less effort to review and approve or revise.

## How It Works

The **Orchestrator Agent** coordinates development by launching specialized subagents:

- **Developer Subagents** - Implement stories following acceptance criteria
- **Reviewer Subagents** - Adversarially review implementations for issues
- **Judge Subagents** - Filter review feedback to prevent scope creep

Each story goes through a develop-review-judge loop (max 5 iterations) until complete or failed.

## Getting Started

First, you need some kind of project plan, even if it's just a checklist of tasks. The whole point of this is to push through all the work you have available. Ask an agent to read the ORCHESTRATOR_AGENT_KIRO.md file and then adapt your project plan to something that works with the ORCHESTRATOR_AGENT_KIRO.md instructions.

Once the project plan is in-place, start with a relatively low-usage Agent session; either ask the agent to read the ORCHESTRATOR_AGENT_KIRO.md file or even better, in Kiro do this:

```plain
/context add /wherever/you/placed/ORCHESTRATOR_AGENT_KIRO.md
```
Now, ask the agent if there's anything else it needs to know to get started orchestrating this project. Once it has everything it needs, just ask it to complete whatever tasks you want (e.g. "complete epics 1-3").

## Key Files

- `ORCHESTRATOR_AGENT_KIRO.md` - Main orchestrator instructions
- `DEVELOPER_SUBAGENTS_KIRO.md` - Developer implementation guidelines  
- `REVIEWER_SUBAGENTS_KIRO.md` - Adversarial review instructions
- `REVIEW_JUDGE_KIRO.md` - Review filtering and approval logic
- `EPICS.example.md` - Example project structure template

## Usage Tip

Add the orchestrator instructions to persistent context:

```bash
/context add ORCHESTRATOR_AGENT_KIRO.md
```

This ensures the agent retains its role after `/clear` commands, avoiding the need to re-read the instruction files.

## Features

- Epic dependency management with parallel development paths
- Automatic merge conflict detection and resolution
- Story failure handling with escalation
- Progress tracking and completion reports
- Context window protection through delegation

## Attribution

The adversarial review methodology in `REVIEWER_SUBAGENTS_KIRO.md` was derived from the BMAD-METHOD project's [adversarial review task](https://github.com/bmad-code-org/BMAD-METHOD/blob/main/src/core/tasks/review-adversarial-general.xml).
