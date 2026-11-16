# Model Choice and Fallback

[Back to documentation home](../../README.en.md) · [中文版](../models-and-fallback.md) · [Task intervention commands](interactive-tasks.md)

Engine7 keeps the companion's persistent state separate from model selection. Model services handle the current reasoning; the workspace's configuration, memory, and files are kept by your deployment environment. You can pick models per task and configure fallback models or services for availability.

## Check the current state first

```text
/model
```

This lists configured models. When automatic routing is using the fallback chain, it also shows the chain order, the next candidate, services in cooldown, and the model actually used last.

The list comes from your deployment configuration — typing an unconfigured model name does not provision a service.

## Selecting a model manually

Copy the full model reference from the `/model` list, or use an alias you have set:

```text
/model configured-model-reference-or-alias
```

On native slash-command platforms, put the reference into the `model` parameter. When several entries match, use the full reference.

A manual selection temporarily overrides automatic routing. If a task is running, switching may interrupt the previous model's query; confirm task progress before switching — it is usually easier to resume that way.

## How the automatic fallback chain works

When fallback candidates are configured and the primary model or service hits an error that can trigger a switch, the engine continues with other models or services in the chain. Failed candidates enter their own cooldown so an unavailable service is not retried endlessly.

Fallbacks must be configured in advance, with valid credentials and quota, and be suitable for the task. Candidates can differ in tools, vision, context capacity, and output quality.

The goal here is **maximum availability**. If every candidate is unavailable, or a service the task depends on fails, human handling may still be required — the fallback mechanism is not a success guarantee for every task.

## Restoring automatic selection

```text
/model auto
```

This clears the manual model override, restores automatic selection from your configuration, and resets fallback-chain cooldowns. `/model reset` does the same.

To retry after a service recovers, run `/model auto`, then `/model` to confirm the state. Task actions already completed are not undone by a model reset.

## Configuration tips

1. Add model services, valid credentials, and model identifiers in the installer/console or your deployment configuration.
2. Configure the primary model and fallback candidates, and confirm each one actually answers a real request.
3. Use `/model` to check that automatic selection engages and the chain order matches expectations.
4. For important tasks, confirm the model supports the tools, vision, or context capacity you need.

For switches that fail, all-candidate cooldowns, or service errors, see the [FAQ](faq.md).
