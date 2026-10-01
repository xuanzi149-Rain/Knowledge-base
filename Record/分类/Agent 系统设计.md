# Agent 系统设计

记录 Agent 运行框架中可复用的循环、工具、安全、扩展与上下文管理方法。

- [[知识/Agent/Claude code搭建/Agent 循环|Agent 循环]]：模型调用、工具执行与结果回传的基本循环。
- [[知识/Agent/Claude code搭建/Agent 工具分发|Agent 工具分发]]：工具定义与处理函数的注册和分发。
- [[知识/Agent/Claude code搭建/Agent 工具权限|Agent 工具权限]]：执行前的禁止、规则匹配与批准关口。
- [[知识/Agent/Claude code搭建/Agent 钩子|Agent 钩子]]：输入、工具和停止节点的扩展机制。
- [[知识/Agent/Claude code搭建/Agent 任务规划|Agent 任务规划]]：复杂任务的步骤与进度状态。
- [[知识/Agent/Claude code搭建/Agent 子任务委派|Agent 子任务委派]]：以独立消息历史处理聚焦子任务。
- [[知识/Agent/Claude code搭建/Agent 技能按需加载|Agent 技能按需加载]]：先展示目录，需要时加载全文。
- [[知识/Agent/Claude code搭建/Agent 上下文压缩|Agent 上下文压缩]]：控制长任务的当前会话容量。
- [[知识/Agent/Claude code搭建/Agent 持久记忆|Agent 持久记忆]]：选择并复用跨会话信息。

返回 [[首页]]。
