---
类别:
  - "[[分类/Agent 系统设计]]"
aliases:
  - "Subagent"
创建日期: "2026-10-01"
更新日期: "2026-10-01"
---

# Agent 子任务委派

## 核心结论

子 Agent 可以用新的消息历史处理聚焦的子任务，只把最终结论交还父 Agent，减少中间工具输出占用父上下文。

## 解释与适用条件

教程中的委派是同步运行的嵌套循环：父 Agent 调用 `task`，子 Agent 使用独立的 `messages[]`，完成后返回最终文本。这是消息隔离，不是进程或文件系统隔离；双方共享工作目录，子任务的文件写入仍会影响同一工作区。教程还通过不给子 Agent `task` 工具来限制委派层级，并沿用工具权限和生命周期钩子。

## 来源

- `/Users/wangzixuan/Desktop/Github/Learn-claude-code/learn-claude-code/s06_subagent/README.md`

## 相关知识

- [[知识/Agent/Claude code搭建/Agent 任务规划|Agent 任务规划]]：规划确定步骤，委派处理适合独立完成的步骤。
- [[知识/Agent/Claude code搭建/Agent 上下文压缩|Agent 上下文压缩]]：两者都帮助控制父任务的上下文负担。
