# Product Overview

[Back to documentation home](../../README.en.md) · [中文版](../overview.md) · [Read the full product introduction online](https://www.twinsun.top/intro/)

Engine7 · 栖 ("Qi") is a self-hostable AI companion and agent engine. Run it on your own computer or server, spend your days with it through chat entries you already use, and hand over everyday thoughts, plans, and work.

## A companion, not a widget

The companion has her own name, identity, and way of expressing herself, and she gradually learns your background and preferences. Daily conversation and work tasks can switch modes automatically or manually. Voice and other experience extensions are supported — the exact capabilities depend on the extensions, models, and services you enable.

## Memory that carries over

The mem7 long-term memory organizes people, events, preferences, and plans, preserving where information came from, when, and whose view it was. Long-term memory helps the companion understand context in later conversations, and lets updated understanding replace outdated views. Memory still needs to be read together with context — you can clarify or correct her directly.

## Tasks and collaboration

From a one-line request to materials, documents, spreadsheets, slides, or code delivery, Engine7 can invoke tools and skills to push work forward. Larger jobs can be divided across an Agent Team — actual execution depends on the skills, materials, services, and permissions installed.

**You can step in at any moment while it works.** Work mode reports progress and intermediate results; `/ps` adjusts a running task's direction, `/stop` interrupts the current task, `/model` inspects or switches models. Step-by-step usage is in [Interactive, interruptible tasks](interactive-tasks.md).

## Proactive reminders

Calendar, scheduled jobs, and context-based nudges give plans a chance to surface at the right moment. For important deadlines, set an explicit reminder and confirm the time, timezone, and delivery channel.

## Multi-channel and deployment

WeChat, Feishu, DingTalk, WeCom, Discord, Telegram, WhatsApp and other chat platforms are supported, configured per platform account and access conditions. Windows, macOS, and Linux each have an installer or self-hosting path; for download and first run see [Quick start](quick-start.md).

The workspace and persistent state are kept by your deployment environment. Changing models and migrating the workspace are two different things: model services do the reasoning, while the companion's configuration, files, and memory need to be carried over deliberately.

## Models and availability

Multiple model services can be attached and selected manually. With fallback models or services configured, Engine7 can try other candidates on failures, using cooldowns and status feedback to reduce dependence on any single service. See [Model choice and fallback](models-and-fallback.md).
