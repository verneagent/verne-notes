---
layout: post
title: "Why I Built lark-suite for Team Docs and Project Tracking"
description: "lark-suite exists so an agent can help write team documents, keep project status visible, and move work into a shared Lark wiki instead of leaving it in chat."
lang: en
hero_image: /assets/images/lark-wiki-cover.svg
image: /assets/images/lark-wiki-cover.svg
hero_alt: "A diagram showing an agent helping write team documents and push progress into a shared Lark wiki."
quick_nav:
  - id: why-i-built-lark-suite
    label: Why lark-suite exists
  - id: what-i-actually-wanted-from-it
    label: Docs and project tracking
  - id: why-a-team-wiki-matters-to-an-agent
    label: Why the wiki matters
  - id: where-this-sits-next-to-the-official-lark-mcp
    label: Relation to official MCP
  - id: install
    label: Install
---

**TL;DR**

I built `lark-suite` because I wanted an agent to do something concrete for a team: write useful documents, keep project progress visible, and push work into the shared wiki instead of leaving it scattered across chats and terminals. The point is not abstraction. The point is operational documentation.

<blockquote class="pull-quote">If an agent can help think, summarize, and plan, but cannot write back into the team's actual document system, most of that value stays private and temporary.</blockquote>

<span id="why-i-built-lark-suite"></span>
## Why I built `lark-suite`

I did not build `lark-suite` because I wanted a philosophically narrower interface.

I built it because I wanted an agent to help with a very specific class of team work:

- draft team documents
- update project status pages
- keep work logs and rollout notes in one place
- turn messy session output into reusable internal documentation

That is the gap I kept seeing in practice.

An agent session could produce something useful, but the useful part often stopped one step too early:

- the reasoning happened
- the summary happened
- maybe even the plan happened
- but the team document never got updated

That meant the outcome stayed local to the terminal or the chat thread. The rest of the team never really got the benefit.

`lark-suite` exists to close that last mile.

<span id="what-i-actually-wanted-from-it"></span>
## What I actually wanted from it

The job was not “integrate Lark.”

The job was much more specific:

- let an agent read the existing wiki structure
- create the right page in the right place
- inspect and write document blocks cleanly
- help maintain ongoing project pages instead of only one-off notes
- fill a few gaps where browser automation is still the practical path

That is why the skill looks the way it does. It is centered on document authoring and project progress management.

I wanted it to support flows like these:

- “turn this debugging session into an internal incident note”
- “update the weekly project page with today’s progress”
- “create a rollout checklist in the wiki and fill the first draft”
- “read the current milestone page, then append what changed today”

Those are team documentation jobs. They are not generic API exercises.

<span id="why-a-team-wiki-matters-to-an-agent"></span>
## Why a team wiki matters to an agent

An agent becomes more useful when it can move from private reasoning into shared operational memory.

A team wiki is where that usually happens.

It is where teams keep:

- current project status
- decisions
- rollout steps
- debugging notes that should survive the session
- documents other people can actually read later

If an agent cannot help at that boundary, a lot of its value stays trapped in temporary surfaces.

That is the real reason I built `lark-suite`: not because a narrower interface is elegant, but because a team needs its documents and progress pages to stay current.

<span id="where-this-sits-next-to-the-official-lark-mcp"></span>
## Where this sits next to the official Lark MCP

The official `lark-openapi-mcp` is still the broader choice if you want general Lark coverage.

`lark-suite` is for a narrower but very practical workflow:

- shared docs
- wiki pages
- project status updates
- structured writing back into the team knowledge base

That is why I still describe it as narrower, but the reason for that narrowness is concrete: I wanted a better writing and project-tracking path, not a more abstract architecture story.

<span id="install"></span>
## Install

```bash
npx skills add -g verneagent/lark-suite
```

`lark-suite` is for Claude Code and OpenCode.
