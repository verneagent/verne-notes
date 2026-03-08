---
layout: post
title: "Why I Built handoff: Step Away Without Leaving the Work"
description: "handoff exists so a human can temporarily leave the terminal without abandoning the same working thread."
lang: en
hero_image: /assets/images/handoff-cover.svg
image: /assets/images/handoff-cover.svg
hero_alt: "A diagram showing a CLI session handed over to a phone while preserving the same thread."
quick_nav:
  - id: why-handoff-exists
    label: Why handoff exists
  - id: the-real-problem-it-solves
    label: Step away without leaving
  - id: sidecar-is-the-most-practical-part
    label: Why sidecar matters
  - id: sidecar-guest-and-coowner-bring-in-other-people
    label: Bring colleagues in
  - id: install
    label: Install
---

**TL;DR**

I built `handoff` for a very practical reason: sometimes a human needs to temporarily leave the terminal, but the work should not stop there. `handoff` keeps the same working thread alive in Lark so the person can step away without abandoning the job.

<blockquote class="pull-quote">The point of handoff is not “another interface.” It is “I can step away for a while without leaving the work.”</blockquote>

<span id="why-handoff-exists"></span>
## Why `handoff` exists

Many useful coding sessions last longer than a human wants to stay fixed in front of a terminal.

That creates a very ordinary failure mode:

- the agent has context,
- the human needs to step away,
- and the collaboration thread collapses because the interface changes.

I built `handoff` because I did not want “I need to leave for a bit” to mean “this work session is effectively over.”

The goal is simple: let a human temporarily leave the terminal without leaving the work.

<span id="the-real-problem-it-solves"></span>
## The real problem it solves

The value of `handoff` is not “send a message to Lark.” That frame is too small.

What matters is continuity while the human is temporarily away:

- the same project context
- the same operational thread
- the same conversation instead of a restarted explanation
- the same active work, not a dropped task that has to be reconstructed later

That is the difference between “I can ping the agent elsewhere” and “I never actually left the work.”

That is the real product boundary for `handoff`.

<span id="sidecar-is-the-most-practical-part"></span>
## `sidecar` is the most practical part

The feature that makes `handoff` feel real instead of ceremonial is `sidecar`.

Without sidecar, many handoff tools quietly assume that the bot should create a dedicated channel and own the interaction model. That is often too rigid.

`sidecar` lets the bot join an existing Lark group instead.

That matters because real teams already have group structure. They already have operating rooms, incident groups, feature channels, and private collaboration threads. If you want a colleague to help while you are away from the terminal, the tool should be able to enter that existing space instead of forcing a brand new social surface every time.

So when I describe `handoff`, the phrase I care about is not “phone continuation.” It is “step away without dropping the thread.”

<span id="sidecar-guest-and-coowner-bring-in-other-people"></span>
## `sidecar`, `guest`, and `coowner` make it possible to bring other people in

The second thing that matters is that `handoff` should not trap the work between one human and one bot.

Sometimes the whole point of the handoff is that another person can help while you are away.

That is where these pieces matter together:

- `sidecar` lets the bot enter the existing group where teammates already are
- `guest` lets other people follow and join the thread
- `coowner` lets someone else help operate or manage the session instead of waiting on a single owner

That is a much more useful shape than a private one-person continuation story. It means `handoff` can become a practical way to say: “I need to step away, but please help keep this moving.”

<span id="install"></span>
## Install

```bash
npx skills add -g verneagent/handoff
```

`handoff` is for Claude Code and OpenCode. It is not positioned as a Codex skill, because the hook and plugin model here is built around Claude Code and OpenCode workflows.
