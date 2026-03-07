---
layout: post
title: "为什么团队 Wiki 需要一个更窄的 Agent 接口"
description: "为什么我做了 lark-wiki，而不是把团队知识库简单地当成另一个通用 API 面。"
lang: zh
translation_key: team-wiki-narrow-interface
hero_image: /assets/images/lark-wiki-cover.svg
image: /assets/images/lark-wiki-cover.svg
hero_alt: "一张展示 agent 接口如何收窄到结构化团队 wiki 文档的示意图。"
---

**TL;DR**

我做 `lark-wiki`，是因为很多 agent 工作流真正变弱的地方，恰恰是知识应该进入团队 wiki 的那一步。团队 wiki 不是一个普通的 API 面，它本质上是一个结构化写作界面。`lark-wiki` 故意做窄，就是为了让 agent 在 wiki/doc 写作流上更直接，而不是假装自己是一个通用 Lark 层。

> 团队 wiki 不只是结果的存放处。它决定了一条 agent workflow 最终是变成可复用方法，还是就地蒸发。

## 为什么会有 `lark-wiki`

很多 agent workflow 看上去已经完整了，直到你要把结果写进一个真正长期存在的地方。

问题往往就在这一步暴露：

- agent 能推理
- agent 能起草
- 但知识没有真正落进团队 wiki

这个缺口比看起来更重要。一个不能把知识写回团队长期知识库的 workflow，很难真正变成团队能力。

我做 `lark-wiki`，就是想把这个缺口补上。

## 团队 Wiki 不是另一个普通 API 面

如果把 wiki 集成简单理解成“我已经有 API 了，所以问题已经解决了”，通常会错。

因为 wiki 难的地方，不在“能不能调接口”，而在它其实是一个写作界面：

- 有页面树
- 有 block 结构
- 有作者流
- 有评论
- 有一种特定的“知识该怎么写回去”的预期

一旦你真的在乎这些东西，一个太宽的通用层，往往就会对真正的写作路径显得不够敏感。

## 为什么这里要故意做窄

`lark-wiki` 故意比通用 Lark 连接层更窄。

它只盯着 agent 在 wiki/doc 写作场景里真正需要的几件事：

- 读 wiki 页面和目录树
- 创建 wiki 页面
- 读 block 结构
- 写结构化 block 内容
- 在 API 不够时，用浏览器脚本补少量能力，比如 inline comment

我不把这种“窄”看成缺点。我把它看成接口纪律。

它不需要什么都做。它只需要在那条最容易让 agent workflow 失效的边界上，做得够直接。

## 它和官方 Lark MCP 的关系

官方 `lark-openapi-mcp` 是更广的选择。如果你的目标是通用 Lark OpenAPI 覆盖，它是对的方向。

`lark-wiki` 解决的是另一类需求：wiki 和 doc 写作流。

所以我更愿意按“形状”来比较，而不是按“身份”来比较：

- 官方 MCP：更广、官方、通用
- `lark-wiki`：更窄、更直接、偏向文档工作流

这不是一个“替代谁”的故事，而是一个“边界在哪里”的故事。

## 安装

```bash
npx skills add -g verneagent/lark-wiki
```

`lark-wiki` 面向 Claude Code 和 OpenCode。
