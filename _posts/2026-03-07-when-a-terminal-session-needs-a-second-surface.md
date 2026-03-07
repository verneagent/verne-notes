---
layout: post
title: "When a Terminal Session Needs a Second Surface"
description: "Why I built handoff: to keep a human-agent thread alive when the terminal is no longer the right interface."
lang: en
hero_image: /assets/images/handoff-cover.svg
hero_alt: "A diagram showing a CLI session handed over to a phone while preserving the same thread."
quick_nav:
  - id: why-handoff-exists
    label: Why handoff exists
  - id: what-handoff-actually-solves
    label: What it actually solves
  - id: sidecar-is-the-most-practical-part
    label: Why sidecar matters
  - id: guest-and-coowner-change-the-shape-of-the-tool
    label: Guest and coowner
  - id: install
    label: Install
---

**TL;DR**

I built `handoff` because a strong human-agent collaboration often breaks at the moment the human leaves the terminal. The problem is usually not model quality. It is interface continuity. `handoff` keeps the same working thread alive in Lark, and `sidecar`, `guest`, and `coowner` make it usable in real team settings instead of a single-user demo.

<blockquote class="pull-quote">A long agent session usually fails at the interface boundary before it fails at the reasoning boundary.</blockquote>

<span id="why-handoff-exists"></span>
## Why `handoff` exists

Many useful coding sessions are longer than the time a human wants to stay glued to a terminal window.

That creates a very ordinary failure mode:

- the agent has context,
- the human needs to step away,
- and the collaboration thread collapses because the interface changes.

I built `handoff` to treat that as an actual systems problem instead of a social inconvenience.

The goal is simple: keep the same working thread alive when the human moves from terminal to phone.

<span id="what-handoff-actually-solves"></span>
## What `handoff` actually solves

The value of `handoff` is not "send a message to Lark." That is too small a frame.

What matters is preserving continuity:

- the same project context
- the same operational thread
- the same conversation instead of a restarted explanation

That is the difference between "I can reach the agent elsewhere" and "the collaboration remains intact."

For me, that is the real product boundary.

<span id="sidecar-is-the-most-practical-part"></span>
## `sidecar` is the most practical part

The feature that makes `handoff` feel real instead of ceremonial is `sidecar`.

Without sidecar, many handoff tools quietly assume that the bot should create a dedicated channel and own the interaction model. That is often too rigid.

`sidecar` lets the bot join an existing Lark group instead.

That matters because real teams already have group structure. They already have operating rooms, incident groups, feature channels, and private collaboration threads. A useful tool should be able to enter that space without forcing a brand new social surface every time.

So when I describe `handoff`, I do not think the most important phrase is "phone continuation." I think it is "same thread, existing group, explicit control."

<span id="guest-and-coowner-change-the-shape-of-the-tool"></span>
## `guest` and `coowner` change the shape of the tool

The second thing that makes `handoff` more than a solo utility is role support.

`guest` and `coowner` change the collaboration model:

- `guest` opens the door to broader participation
- `coowner` supports shared operation instead of a single operator bottleneck

This matters because real collaboration is often messy. One person may start the thread, another may need to observe, and a third may need to help operate or manage it. A skill that assumes a single clean owner is easier to explain, but less useful in practice.

I would rather the tool match the actual coordination pattern.

<span id="install"></span>
## Install

```bash
npx skills add -g verneagent/handoff
```

`handoff` is for Claude Code and OpenCode. It is not positioned as a Codex skill, because the hook and plugin model here is built around Claude Code and OpenCode workflows.
