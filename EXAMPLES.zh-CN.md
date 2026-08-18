# Universal Agent Workflow Starter：中文实战示例

[返回中文版首页](./README.md) | [完整中文提示词](./PROMPT.zh-CN.md) | [English examples](./EXAMPLES.en.md)

下面的内容可以直接复制给已经加载 Universal Agent Workflow 的 Agent。

## 示例一：单 Agent 修复问题

```text
请按照 Universal Agent Workflow 工作，角色设为 SOLO。

任务：修复用户登录后偶发返回 500 的问题。
输入：当前仓库、错误日志和已有测试。
限制：
- 不改变登录接口；
- 不新增外部依赖；
- 不触碰生产环境；
- 保留我的其他未提交改动。

请先定位根因并给出简短任务启动卡。若属于 S 级或没有未决问题的
M 级任务，直接实施并验证；完成后提交任务完成卡。
```

## 示例二：规划 Agent 生成工作单

```text
请按照 Universal Agent Workflow 工作，角色设为 PLANNER。

目标：为现有应用增加批量导出功能。
请读取当前需求、接口定义、数据模型和测试。
本轮只做 RESEARCH / DECISION / PLAN，不修改代码。

比较至少两个真正可行的方案，说明成本、风险、兼容性和回滚方式。
把需要我决定的问题集中提出；决定明确后生成状态为 USER_APPROVED
或 PROPOSED 的 WORK ORDER，不得混入未经批准的新范围。
```

## 示例三：执行 Agent 实施工作单

```text
请按照 Universal Agent Workflow 工作，角色设为 EXECUTOR。

读取适用的 AGENTS.md、权威需求和这份已批准工作单：[路径或内容]
执行基线：[分支或提交]
本轮授权：IMPLEMENT + VERIFY。

严格限制在工作单允许的路径内。先运行最窄相关测试，再运行合理的
回归检查。发现冲突时停止受影响部分并继续其余工作。
完成后报告实际变更、命令、结果、偏差和剩余风险。
```

## 示例四：独立审查

```text
请按照 Universal Agent Workflow 工作，角色设为 REVIEWER。

只读审查：[提交、diff、报告或产物]
依据：[获批工作单、需求和验收标准]

检查完整变更、相关调用链、测试、产物和范围合规性。
按 P0–P3 报告具体、可定位、可操作的问题。
若无发现写 No findings，但不要将其解释为最终 ACCEPTED。
```

## 用户常用回复

```text
批准执行
```

```text
批准，但修改：这里写要调整的内容
```

```text
只做研究，不实施
```

```text
停止
```
