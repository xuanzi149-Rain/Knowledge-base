---
类别:
  - "[[分类/Agent 系统设计]]"
aliases:
  - "Skill Loading"
创建日期: "2026-10-01"
更新日期: "2026-10-01"
---

# Agent 技能按需加载

## 核心结论

先向模型提供技能名称和简短描述组成的目录；任务需要某项技能时，再读取完整 `SKILL.md`。这样可以避免每轮都把全部技能正文放进系统提示。

## 解释与适用条件

教程启动时扫描技能目录并建立注册表，`load_skill(name)` 按注册名称返回完整内容，随后作为工具结果进入当前对话。名称查找不应直接当作任意文件路径。按需加载适合规则或领域资料较多、但每次任务只需其中一部分的情形；已加载的正文仍会占用当前会话上下文。

## 来源

- `/Users/wangzixuan/Desktop/Github/Learn-claude-code/learn-claude-code/s07_skill_loading/README.md`

## 相关知识

- [[知识/Agent/Claude code搭建/Agent 上下文压缩|Agent 上下文压缩]]：按需加载减少初始输入；压缩处理会话继续增长的问题。
