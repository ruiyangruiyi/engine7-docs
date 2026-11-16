# Interactive, Interruptible Tasks

[Back to documentation home](../../README.en.md) · [中文版](../interactive-tasks.md) · [Models and fallback](models-and-fallback.md)

**The task works — and you can step in at any time.** Engine7's interaction model puts observation, added requirements, and interruption together, so you can catch drift early, narrow the scope, and steer what comes next.

## Seeing the work happen

Work mode uses a work-focused context and reports progress, tool activity, and intermediate results through the chat channel. "Summary first", "plan first", "check as you go" — all of these can be written directly into the task.

How much is shown depends on the chat platform, progress display, and external group settings. After enabling work mode, confirm the display settings of that channel.

| Command | Behavior |
| --- | --- |
| `/work` | Show the current mode |
| `/work on` | Force work mode, effective from the next message |
| `/work off` | Force daily-conversation mode, effective from the next message |
| `/work auto` | Return to per-message automatic detection |

## Changing direction mid-task: /ps

`/ps` injects an added requirement into the **currently running task**, without waiting for the current answer to finish. It interrupts the ongoing generation so subsequent execution picks up the new direction.

```text
/ps Don't write the full plan yet — give me three candidate directions first
/ps The client is non-technical; cut the jargon and lead with practical benefits
/ps Work from the materials we already have; stop widening the search
```

With no task running, just send a normal message. On platforms with native slash commands, pick `/ps` and put the requirement into the `message` parameter; other text-command channels use `/ps your requirement`.

## Interrupting in time: /stop

`/stop` requests stopping this session's running task and clears the session's pending message queue. Once you receive the "current task stopped" receipt, you can send new requirements.

```text
/stop
```

Stopping does not undo external actions already completed (file edits, sent messages, and so on); the command targets the current session — other independent tasks and scheduled jobs need to be managed separately. Interrupt responsiveness also depends on the tools and external services mid-execution.

## Inspecting or switching models: /model

```text
/model
/model configured-model-alias
/model auto
```

Without arguments it shows the current choice, available models, and fallback-chain status; when selecting, use a reference or alias from the list. A manual selection overrides automatic routing — use `/model auto` to restore automatic choice. Switching mid-run may interrupt the previous model's query; for important tasks, stop first, confirm progress, then switch. See [Models and fallback](models-and-fallback.md).

## Other common inspection commands

| Command | Purpose |
| --- | --- |
| `/tasks` | Background tasks and their status; this list is not all foreground work |
| `/agents` | Registered agents and their run status |
| `/context` | Context usage |

## A complete intervention, start to finish

1. Send `/work on` and state the task, materials, deliverable format, and constraints clearly.
2. Watch the progress output and the first intermediate result.
3. Add requirements with `/ps`, e.g. "summary first, not the full text yet".
4. Use `/stop` when needed; check what was already done, then restate the task.
5. If the service or model is a poor fit, inspect options with `/model`; restore the fallback chain with `/model auto`.

You can form judgments while the work runs, intervene, and confirm receipts — keeping the task moving toward your goal.
