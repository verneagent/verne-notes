---
layout: post
title: "我为什么做 handoff：临时离开，也不用离开工作"
description: "handoff 的目标不是多一个界面，而是让人临时离开终端时，工作线程不断。"
lang: zh
translation_key: handoff-step-away-without-leaving
hero_image: /assets/images/handoff-cover.svg
image: /assets/images/handoff-cover.svg
hero_alt: "一张展示 CLI 会话如何保持同一线程交接到手机上的示意图。"
---

**TL;DR**

我做 `handoff`，是因为人有时需要临时离开终端，但不应该因此离开工作本身。`handoff` 的目标不是“多一个界面”，而是让同一条工作线程在你暂时离开时还能继续存在。

> `handoff` 的重点不是“换个地方聊”，而是“人离开一会儿，工作也不要断”。

## 为什么会有 `handoff`

很多真正有价值的 coding session，都比人愿意一直盯着终端的时间更长。

于是就会出现一种很普通的失败方式：

- agent 还保有上下文
- 人却不得不离开终端
- 协作线程因为界面变化而断掉

我做 `handoff`，就是不想让“我先离开一下”自动变成“这条工作线程基本结束了”。

它真正要解决的是：当人从终端切到手机时，同一条工作线程还能继续存在。

## `handoff` 真正在保什么

`handoff` 的价值，不是“可以在 Lark 里收到一条消息”。

它真正要保住的是：人在临时离开时，工作不要跟着断。

也就是说，它想保住的是连续性：

- 同一个项目上下文
- 同一条操作线程
- 同一段协作，而不是重新解释一遍问题
- 同一件还在进行中的工作，而不是事后再花一轮时间把现场拼回来

这也是“我能在别处碰到 agent”和“我其实没有离开这项工作”之间的区别。

## `sidecar` 是把同事拉进来的关键

让 `handoff` 从“可演示”变成“可用”的关键点，是 `sidecar`。

没有 `sidecar` 的 handoff 工具，往往默认 bot 应该新建一个专用频道，并且完全接管交互方式。这通常太僵。

`sidecar` 允许 bot 直接加入一个已经存在的 Lark 群。

这很重要，因为真实团队早就有它们自己的群结构了。它们已经有事故群、功能群、临时协作群。如果你想在自己临时离开时请同事帮忙，一个有用的工具就应该能进入这些空间，而不是每次都要求大家再接受一个新的社交表面。

所以如果要我概括 `handoff`，我不会只说“手机续聊”。我会说：临时离开，但工作不断，而且能把同事拉进来一起帮。

## `guest` 和 `coowner` 让同事真的能接手帮忙

第二个重要的点是，`handoff` 不应该把工作锁死在“一个人 + 一个 bot”里。

很多时候，handoff 的意义就在于：你离开一下，但别人可以继续帮你推进。

这时这几个能力就变成一套组合：

- `sidecar` 让 bot 进入现有群
- `guest` 让其他人可以跟进这条线程
- `coowner` 让别人可以一起操作或接手维护，而不是所有动作都卡在单一 owner 身上

这比“私人续聊工具”更有用，因为它支持一种很真实的场景：我先离开，但请大家一起帮我把这件事继续推进。

## 安装

```bash
npx skills add -g verneagent/handoff
```

`handoff` 面向 Claude Code 和 OpenCode。它不按 Codex skill 来定位，因为这里的 hook / plugin 模型本来就是按 Claude Code 和 OpenCode 的工作方式设计的。
