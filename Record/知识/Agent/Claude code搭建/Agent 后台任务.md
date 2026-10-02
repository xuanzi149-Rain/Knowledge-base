---
类别:
  - "[[分类/Agent 系统设计]]"
aliases:
  - "Background Tasks"
创建日期: "2026-10-02"
更新日期: "2026-10-02"
---

# Agent 后台任务

## 核心结论

耗时命令可以显式转入后台，让 Agent 循环先取得任务 ID 并继续处理不依赖该命令的工作；完成结果在后续轮次作为通知交付。

## 解释与适用条件

教程只在 Bash 工具参数 `run_in_background=true` 时使用后台线程。原工具调用立即得到含 `bg_id` 的占位结果；后台完成后，运行框架在后续模型调用前收集结果，以独立的 `<task_notification>` 注入消息，而不重复使用原 `tool_use_id`。执行前权限检查仍在主线程进行。

命令失败或工作线程异常应标记为失败。后台完成本身不会唤醒已停止的 Agent；要到循环再次运行时才会收集通知。教程的进程组清理负责生命周期管理，不构成沙箱隔离。

## 来源

- `/Users/wangzixuan/Desktop/Github/Learn-claude-code/learn-claude-code/s11_background_tasks/README.md`

## 相关知识

- [[知识/Agent 定时调度|Agent 定时调度]]：后台任务处理已启动命令的耗时执行；定时调度决定将来何时启动工作。
