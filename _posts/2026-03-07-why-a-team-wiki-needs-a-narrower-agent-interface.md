---
layout: post
title: "Why a Team Wiki Needs a Narrower Agent Interface"
description: "Why I built lark-wiki instead of treating a team wiki as just another generic API surface."
lang: en
hero_image: /assets/images/lark-wiki-cover.svg
image: /assets/images/lark-wiki-cover.svg
hero_alt: "A diagram showing an agent interface narrowing into a structured team wiki document."
quick_nav:
  - id: why-lark-wiki-exists
    label: Why lark-wiki exists
  - id: a-team-wiki-is-not-just-another-api-surface
    label: Why generic API access is not enough
  - id: why-this-is-narrow-on-purpose
    label: Why narrow is better here
  - id: where-it-sits-next-to-the-official-lark-mcp
    label: Relation to official MCP
  - id: install
    label: Install
---

**TL;DR**

I built `lark-wiki` because many agent workflows become weak exactly where knowledge should move into a shared wiki. A team wiki is not just another API surface. It is a structured writing surface. `lark-wiki` is intentionally narrow so an agent can read wiki trees, inspect document blocks, write structured content, and bridge a few browser-only gaps without pretending to be a universal Lark layer.

<blockquote class="pull-quote">A team wiki is not merely a place to store outputs. It is where an agent workflow either becomes reusable or evaporates.</blockquote>

<span id="why-lark-wiki-exists"></span>
## Why `lark-wiki` exists

Many agent workflows feel complete until the moment the result needs to live somewhere durable.

That is where a surprising amount of useful work collapses:

- the agent can reason
- the agent can draft
- but the knowledge never lands properly in the team's wiki

That gap matters more than it looks. If a workflow cannot write back into the place where teams actually keep reusable knowledge, the workflow remains local and temporary.

I built `lark-wiki` to close that gap.

<span id="a-team-wiki-is-not-just-another-api-surface"></span>
## A team wiki is not just another API surface

The wrong way to think about wiki integration is: "I already have API access, so I already have the problem solved."

That frame misses what makes a wiki hard.

A wiki is not just a document bucket. It has:

- page trees
- document blocks
- authoring flow
- comments
- a very specific expectation of how structured knowledge should be written back

Once you care about those things, a generic integration layer often becomes too broad and too indifferent to the actual writing path.

<span id="why-this-is-narrow-on-purpose"></span>
## Why this is narrow on purpose

`lark-wiki` is intentionally narrower than a general Lark connector.

It focuses on the parts an agent actually needs when the job is "read, write, and shape shared documentation":

- read wiki pages and trees
- create wiki pages
- inspect document blocks
- write structured block content
- cover a few browser-driven gaps such as inline comments

I do not see that narrowness as a limitation. I see it as interface discipline.

The skill does not need to be everything. It needs to be direct at the one boundary where a lot of agent workflows fail.

<span id="where-it-sits-next-to-the-official-lark-mcp"></span>
## Where it sits next to the official Lark MCP

The official `lark-openapi-mcp` is the broader choice. If you want general Lark OpenAPI coverage, that is the right direction.

`lark-wiki` is for a different need: wiki and doc authoring flow from an agent.

That is why I compare them by shape rather than by status:

- official MCP: broad, official, general-purpose
- `lark-wiki`: narrow, direct, optimized for document-heavy workflows

This is not a replacement story. It is a boundary story.

<span id="install"></span>
## Install

```bash
npx skills add -g verneagent/lark-wiki
```

`lark-wiki` is for Claude Code and OpenCode.
