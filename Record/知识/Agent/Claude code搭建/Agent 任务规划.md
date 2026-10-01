---
类别:
  - "[[分类/Agent 系统设计]]"
aliases:
  - "TodoWrite"
创建日期: "2026-10-01"
更新日期: "2026-10-01"
---

# Agent 任务规划

## 核心结论

复杂任务可用独立的待办状态记录步骤及进度，让 Agent 持续对照原目标。规划工具改变的是任务管理状态，不直接增加执行能力。

## 解释与适用条件

教程的 `todo_write` 维护 `pending`、`in_progress`、`completed` 状态，更新前校验条目，且同一时间最多一个步骤处于进行中。运行框架还会在连续若干轮未更新计划时提醒模型。它适用于容易遗漏步骤的任务；计划仍需随实际发现调整，完成状态也不能代替结果验证。

## 来源

- `/Users/wangzixuan/Desktop/Github/Learn-claude-code/learn-claude-code/s05_todo_write/README.md`

## 相关知识

- [[知识/Agent/Claude code搭建/Agent 子任务委派|Agent 子任务委派]]：大型任务除规划外，还可把聚焦的子任务放入独立上下文。
