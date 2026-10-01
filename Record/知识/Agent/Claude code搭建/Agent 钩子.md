---
类别:
  - "[[分类/Agent 系统设计]]"
aliases:
  - "Agent Hooks"
创建日期: "2026-10-01"
更新日期: "2026-10-01"
---

# Agent 钩子

## 核心结论

钩子为输入提交、工具执行前后及停止前提供固定扩展点。扩展逻辑注册到事件上，核心循环只负责触发事件，从而减少每增加一种行为就修改循环主体的需要。

## 解释与适用条件

教程使用 `UserPromptSubmit`、`PreToolUse`、`PostToolUse` 和 `Stop` 四个事件。`PreToolUse` 可阻止当前工具调用；`Stop` 可要求继续循环。该示例中输入和工具执行后的钩子返回值不改变控制流，因此“注册了钩子”不等于具备任意修改提示词或输出的能力。钩子的执行顺序及返回值约定应明确，避免扩展之间互相干扰。

## 来源

- `/Users/wangzixuan/Desktop/Github/Learn-claude-code/learn-claude-code/s04_hooks/README.md`

## 相关知识

- [[知识/Agent/Claude code搭建/Agent 工具权限|Agent 工具权限]]：执行前权限检查是钩子的一个用途。
