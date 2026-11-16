# Quick Start

[Back to documentation home](../../README.en.md) · [中文版](../quick-start.md)

## Route 1: the installer

For users who prefer a graphical wizard for companion setup.

1. Open the [official download page](https://www.twinsun.top/en/download/) and pick the installer for your system and architecture. On Mac, note the difference between Apple Silicon and Intel.
2. Follow the wizard to choose your companion, model, and chat platforms. The installer ships the runtime — no separate Node.js or Python needed.
3. Complete authorization or scanning as prompted for your platforms, check run status in the console, then send a greeting from a connected chat entry.

If you already have a companion, confirm its name and directory first, then choose to continue with it or add a new one. Before a full reconfiguration, read the wizard's coverage and backup notices.

Free-tier quotas and available services follow the current installer UI and the website; bringing your own models requires the corresponding service accounts and credentials.

## Route 2: npm self-hosting

For users who already run Node.js or deploy on servers. Requires **Node.js 22 or newer**.

```bash
npm install -g engine7
engine7 init
```

Follow the initialization prompts to choose a directory, companion, model, and platforms; once model services and platforms are configured, start it:

```bash
engine7 start
```

Configuration options and management commands are listed under `engine7 --help`. Initialization does not equal completed platform authorization — treat actual connection status and chat receipts as the source of truth.

## Hand over your first task

From a connected chat entry, send `/work on` first, then a task with a clear scope, for example:

> From the meeting notes I sent you, list decisions, action items, owners, and deadlines. Flag anything uncertain separately and give me a summary first.

While it runs, if you want to change direction:

```text
/ps Group by owner first, and start with what is due next week
```

To stop the current task immediately:

```text
/stop
```

You can restate requirements afterwards. Use `/work auto` to return to automatic mode detection. Command input varies by platform: platforms with native slash commands offer the commands in a menu or parameter form.

## Check status and get help

- `/model`: current model, configured models, and fallback-chain status.
- `/tasks`: background task list.
- `/context`: context usage.
- `engine7 --version`: installed version in a terminal.
- `engine7 doctor`: self-check report in a terminal.

For problems, start with the [FAQ](faq.md), or open an [Issue](https://github.com/ruiyangruiyi/engine7-docs/issues) with reproduction steps and sensitive information removed.
