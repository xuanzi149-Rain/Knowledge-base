---
类别:
  - "[[分类/Agent 系统设计]]"
aliases:
  - "Tool Permission"
创建日期: "2026-10-01"
更新日期: "2026-10-01"
---

# Agent 工具权限

## 核心结论

工具权限应在执行前由运行框架检查，不能只依赖模型自行判断。教程依次检查禁止项、需要询问的规则，再由用户决定是否批准；均未命中才直接执行。

## 解释与适用条件

检查应针对具体工具及参数。被拒绝的调用仍需向模型返回对应的工具结果，使对话能够继续。教程中的命令字符串匹配和简单规则只是说明权限关口的位置，不能视为完整安全边界；实际系统还需要更可靠的命令、路径及环境限制。

## 来源

- `/Users/wangzixuan/Desktop/Github/Learn-claude-code/learn-claude-code/s03_permission/README.md`

## 相关知识

- [[知识/Agent/Claude code搭建/Agent 工具分发|Agent 工具分发]]：权限检查位于分发执行之前。
- [[知识/Agent/Claude code搭建/Agent 钩子|Agent 钩子]]：可把权限检查注册到工具执行前的钩子。
