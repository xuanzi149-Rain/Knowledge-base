---
类别:
  - "[[分类/Agent 系统设计]]"
aliases:
  - "Agent Loop"
创建日期: "2026-10-01"
更新日期: "2026-10-01"
---

# Agent 循环

## 核心结论

Agent 的最小运行框架是反复调用模型：模型返回工具调用时，由程序执行工具、回传结果并继续；没有工具调用时结束。模型决定下一步，运行框架负责执行和维持对话状态。

## 解释与适用条件

每轮都要把模型回复加入消息历史，再从回复中提取实际的 `tool_use` 块。每个工具结果以对应的 `tool_use_id` 回传；没有工具调用时，不应凭空添加工具结果消息。这个循环是后续工具分发、权限和上下文管理的基础。仅有循环和 shell 工具还缺少充分的安全控制。

## 来源

- `/Users/wangzixuan/Desktop/Github/Learn-claude-code/learn-claude-code/s01_agent_loop/README.md`

## 相关知识

- [[知识/Agent/Claude code搭建/Agent 工具分发|Agent 工具分发]]：在循环的执行位置接入多种工具。
