---
layout: post
title: "当终端不再适合作为唯一界面时"
description: "为什么我做了 handoff：因为一条强的人机协作线程，最先断掉的常常不是推理，而是界面。"
lang: zh
translation_key: handoff-second-surface
hero_image: /assets/images/handoff-cover.svg
hero_alt: "一张展示 CLI 会话如何保持同一线程交接到手机上的示意图。"
---

**TL;DR**

我做 `handoff`，不是为了“把消息发到 Lark”，而是为了在终端不再适合作为唯一界面时，保住同一条 human-agent collaboration 线程。`sidecar`、`guest` 和 `coowner` 让它不只是单人演示工具，而是能进入真实协作环境。

> 一条很长的 agent 会话，常常先死在界面边界，而不是先死在推理边界。

## 为什么会有 `handoff`

很多真正有价值的 coding session，都比人愿意一直盯着终端的时间更长。

于是就会出现一种很普通的失败方式：

- agent 还保有上下文
- 人却不得不离开终端
- 协作线程因为界面变化而断掉

我做 `handoff`，就是想把这件事当成一个真实的系统问题，而不是一个“凑合一下”的使用问题。

它真正要解决的是：当人从终端切到手机时，同一条工作线程还能继续存在。

## `handoff` 真正在保什么

`handoff` 的价值，不是“可以在 Lark 里收到一条消息”。

它真正想保住的是连续性：

- 同一个项目上下文
- 同一条操作线程
- 同一段协作，而不是重新解释一遍问题

这也是“我能在别处碰到 agent”和“这条协作线程真的还活着”之间的区别。

## `sidecar` 是最现实的部分

让 `handoff` 从“可演示”变成“可用”的关键点，是 `sidecar`。

没有 `sidecar` 的 handoff 工具，往往默认 bot 应该新建一个专用频道，并且完全接管交互方式。这通常太僵。

`sidecar` 允许 bot 直接加入一个已经存在的 Lark 群。

这很重要，因为真实团队早就有它们自己的群结构了。它们已经有事故群、功能群、临时协作群。一个有用的工具，应该能进入这些空间，而不是每次都要求大家再接受一个新的社交表面。

所以如果要我概括 `handoff`，我不会只说“手机续聊”。我会说：同一线程，现有群，显式控制。

## `guest` 和 `coowner` 让它不只是单人工具

第二个让 `handoff` 更接近真实协作的点，是角色支持。

`guest` 和 `coowner` 改变了它的协作形状：

- `guest` 让更多参与者可以进入这条线程
- `coowner` 让操作权不必只绑在一个人身上

真实协作从来不总是干净的“一人启动，一人维护”。一个人可能发起线程，另一个人想观察，第三个人可能需要一起接手。一个假设“永远只有一个干净 owner”的工具，虽然容易讲，但往往没那么好用。

我更愿意让工具去贴合真实的协作方式。

## 安装

```bash
npx skills add -g verneagent/handoff
```

`handoff` 面向 Claude Code 和 OpenCode。它不按 Codex skill 来定位，因为这里的 hook / plugin 模型本来就是按 Claude Code 和 OpenCode 的工作方式设计的。
