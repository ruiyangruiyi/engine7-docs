# FAQ

[Back to documentation home](../../README.en.md) · [中文版](../faq.md)

## Where do I download it? Do I need a dev environment?

Use the current installers from the [official download page](https://www.twinsun.top/en/download/). The installer ships the runtime — no separate Node.js or Python; the npm self-hosting route needs Node.js 22+.

## Do I have to buy model services?

You can use the free tier offered in the installer UI, or configure your own model services. Free quotas and service scope follow the current UI and website; costs, permissions, and usage of your own models are governed by the corresponding services.

## How do I get her to report as she works?

Send `/work on` and state in the task: "plan first, report progress along the way, deliver intermediate results". If you still see no process output, check the progress display and group settings of that channel. See [Interactive tasks](interactive-tasks.md).

## What is the difference between /ps and a normal message?

`/ps` is specifically for adding or changing requirements while the current task is running. With no task running, send a normal message; if `/ps` reports no task, check the session and task state first.

## Does /stop undo what was already done?

`/stop` stops the current session's running task and pending messages; it does not roll back completed external actions. To adjust files or already-sent content, instruct recovery or correction separately. Other independent tasks and scheduled jobs are managed separately.

## Why doesn't /tasks list the task that is answering me right now?

`/tasks` shows the background task list. The current foreground answer is not necessarily in it — read it together with the chat progress, the console, and `/agents`.

## Why didn't it switch models after an error?

First run `/model` to check whether a model is pinned manually, whether a fallback chain is configured, and whether all candidates are cooling down. Then check service credentials, quota, network, and capabilities. Use `/model auto` to restore automatic selection. Details in the [fallback guide](models-and-fallback.md).

## Will changing models wipe the companion's memory?

Changing a model is a different operation from deleting or migrating the workspace. The companion's configuration, memory, and files are kept by your deployment environment; before migrating machines or reconfiguring, confirm the actual directory and backups. Do not treat a reconfiguration as a mere model switch.

## Where is my data stored?

Engine7's workspace and persistent state live on the computer or server you deploy on. When external model or tool services are called, the corresponding input goes to the services you configured; data handling scope depends on your model, tool, and channel settings.

## Startup or connection fails — how do I troubleshoot?

1. In the console, check run status, installed version, and the current companion directory.
2. Check the selected model's network, credentials, and quota, and whether the chat platform has completed authorization or scanning.
3. Look at recent logs; on npm deployments run `engine7 --version` and `engine7 doctor` and record the version and self-check output.
4. Open an [Issue](https://github.com/ruiyangruiyi/engine7-docs/issues) with your system, version, channel, reproduction steps, and an error summary with sensitive information removed.

## Where can I read the official product introduction?

The [website introduction page](https://www.twinsun.top/intro/) offers online reading and download. GitHub carries the same edition as [PDF](../../materials/engine7-product-introduction.pdf) and [PPTX](../../materials/engine7-product-introduction.pptx) — currently the 2026.11 Chinese 44-page second edition.
