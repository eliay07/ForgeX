---
name: product-modeling
description: Build and review a structured Product Model from confirmed direction and research. Use for problem statements, personas, context scenarios, outcomes, principles, product directions, feature trees, prioritization, non-goals, assumptions, risks, metrics, and feasibility decisions.
---

# Product Modeling

只读取已确认的 Direction 与研究 Artifact。把“我们可以做什么”约束成“为谁、解决什么、这版做什么和如何判断成功”。

## 必须生成

1. 问题陈述：用户、情境、阻碍、现有替代与代价。
2. Persona 与 Context Scenario：只保留会改变产品决策的差异。
3. 用户结果和产品指标。
4. 3 到 5 条可用于取舍的产品原则。
5. 2 到 4 个真正不同的产品方向及权衡。
6. 功能树：一级任务域、二级能力、三级功能；必要时延伸 L4/L5，但不把全部层级平铺在一个页面。
7. P0、P1、P2、Later 和 Won't。
8. Non-goals、Assumption Register、Risk Register 和早期技术可行性。

## 约束

- 每个 Feature 必须关联问题、Persona、预期结果和证据。
- 优先级不能只写“重要”；说明频率、用户价值、业务价值、风险和依赖。
- AI 推荐必须提供理由、置信度、替代方案和下游影响。
- 用户可逐项修改或批量接受；人工未批准的内容保持 `ai_suggested`。

## 输出

生成 `ProductModel`、`FeatureTree`、`PriorityMap`、`AssumptionRegister` 和 `RiskRegister`，通过 Hard Gate D 后交给 `product-flow-design`。

