---
类别:
  - "[[分类/Agent 系统设计]]"
aliases:
  - "Tool Dispatch"
创建日期: "2026-10-01"
更新日期: "2026-10-01"
---

# Agent 工具分发

## 核心结论

增加工具时，分别提供给模型工具定义，并在运行框架中注册同名处理函数；循环根据工具名分发调用，无需为每种工具重写循环。

## 解释与适用条件

工具定义描述名称、用途和输入结构，处理函数负责实际执行。模型一次回复可能包含多个工具调用，教程示例按原有顺序逐个执行，并为每次调用返回对应结果。专用读写工具能减少用 shell 拼命令的负担，但文件路径校验只覆盖这些文件工具时，shell 仍需单独约束。

## 来源

- `/Users/wangzixuan/Desktop/Github/Learn-claude-code/learn-claude-code/s02_tool_use/README.md`

## 相关知识

- [[知识/Agent/Claude code搭建/Agent 循环|Agent 循环]]：工具分发嵌入其执行步骤。
- [[知识/Agent/Claude code搭建/Agent 工具权限|Agent 工具权限]]：在处理函数执行前增加检查。
