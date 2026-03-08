---
layout: post
title: "我为什么做 lark-wiki：为了团队文档和项目进度管理"
description: "我做 lark-wiki，不是为了抽象地追求更窄接口，而是为了让 agent 真正能写团队文档、更新项目进度，把工作写回共享 wiki。"
lang: zh
translation_key: lark-wiki-team-docs
hero_image: /assets/images/lark-wiki-cover.svg
image: /assets/images/lark-wiki-cover.svg
hero_alt: "一张展示 agent 帮助团队撰写文档并维护项目进度 wiki 的示意图。"
---

**TL;DR**

我做 `lark-wiki`，不是为了追求一个抽象上更优雅的窄接口，而是因为我想让 agent 真正能帮团队做事：写文档、更新项目页面、维护进度记录，把工作从终端和聊天里推进到共享 wiki 里。

> 如果 agent 能帮你思考、总结、规划，但不能把结果写回团队真正会看的文档系统，那大部分价值就会停留在私人会话里。

## 为什么会有 `lark-wiki`

我做 `lark-wiki`，不是因为我想讨论“接口收窄”这件事本身。

我想解决的是一类很具体的团队工作：

- 起草团队文档
- 更新项目状态页
- 维护工作记录和 rollout note
- 把一次 session 里的结果整理成团队以后还能读的文档

我反复遇到的真实问题是：agent session 明明已经产出了有价值的东西，但总是在最后一步断掉。

- 推理发生了
- 总结发生了
- 计划也许已经成形了
- 但团队文档没有被更新

结果就是：价值停留在终端里，停留在聊天里，停留在少数几个人脑子里。

`lark-wiki` 要补的，就是这最后一公里。

## 我真正想要它做什么

这里的任务不是“接入 Lark”这么宽。

这里的任务更具体：

- 让 agent 读到现有 wiki 结构
- 在正确的位置创建页面
- 干净地读写文档 block
- 持续维护项目页面，而不只是写一次性的 note
- 在 API 不够的地方，用浏览器自动化补上

这就是为什么这个 skill 长成现在这个样子。它的中心不是“通用平台接入”，而是“文档撰写和项目进度维护”。

我想支持的，是这种任务：

- “把这次调试过程整理成内部 incident note”
- “把今天的进展补到本周项目页面里”
- “在 wiki 里创建 rollout checklist 并先起草一版”
- “先读现在的 milestone 页面，再把今天的变更补进去”

这些是团队文档工作，不是通用 API 练习。

## 为什么团队 wiki 对 agent 很重要

agent 真正变得有用，不是因为它会在私人会话里说很多聪明话，而是因为它能把这些内容推进到团队共享记忆里。

团队 wiki 往往就是那个地方。

团队会在那里放：

- 当前项目状态
- 决策记录
- rollout 步骤
- 调试笔记
- 以后其他人还能读懂的团队文档

如果 agent 不能帮你处理这层边界，它的很多价值就会一直卡在临时表面里。

所以我做 `lark-wiki` 的真正原因，不是“更窄比较优雅”，而是“团队文档和项目进度页需要保持最新”。

## 它和官方 Lark MCP 的关系

官方 `lark-openapi-mcp` 依然是更广的选择，如果你的目标是通用 Lark 覆盖，它是对的方向。

`lark-wiki` 解决的是另一类更具体的需求：

- 团队文档
- wiki 页面
- 项目状态更新
- 把结构化内容写回团队知识库

所以我仍然会说它更窄，但这个“窄”不是抽象追求，而是很具体的产品取向：我想要一条更好的“写团队文档、管项目进度”的路径。

## 安装

```bash
npx skills add -g verneagent/lark-wiki
```

`lark-wiki` 面向 Claude Code 和 OpenCode。
