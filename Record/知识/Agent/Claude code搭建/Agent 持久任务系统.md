---
类别:
  - "[[分类/Agent 系统设计]]"
aliases:
  - "Task System"
创建日期: "2026-10-02"
更新日期: "2026-10-02"
---

# Agent 持久任务系统

## 核心结论

跨会话或多人协作的任务需要独立、可恢复的任务记录。任务除了状态，还要记录负责人和前置依赖；只有依赖均已完成，任务才能被领取。

## 解释与适用条件

教程以每个任务一个 JSON 文件保存 ID、主题、描述、状态、`owner` 和 `blockedBy`。先创建所有任务并取得运行时生成的 ID，再添加依赖边；更新依赖前检查目标状态、引用是否存在，以及是否形成自依赖或环。任务按 `pending → in_progress → completed` 推进：领取时校验依赖并设置负责人，完成时校验负责人，并找出刚解除阻塞的后续任务。

它与当前会话中的 TodoWrite 清单用途不同：清单帮助一个 Agent 跟踪自己的步骤；持久任务系统支持跨会话恢复、任务依赖和领取。s10 的领取状态按顺序更新；并发领取还需要额外的原子性控制。

## 来源

- `/Users/wangzixuan/Desktop/Github/Learn-claude-code/learn-claude-code/s10_task_system/README.md`

## 相关知识

- [[知识/Agent/Claude code搭建/Agent 任务规划|Agent 任务规划]]：对照会话内清单与持久任务记录。
- [[知识/Agent/Claude code搭建/Agent 团队协作|Agent 团队协作]]：团队在共享任务板上原子领取就绪任务。
