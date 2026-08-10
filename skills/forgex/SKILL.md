---
name: forgex
description: Orchestrate an end-to-end product workflow from an idea or existing MVP through research, product model, user flows, visual direction, implementation, browser QA, iterative repair, and delivery. Use when the user asks to design, build, redesign, review, or complete a digital product and expects a real runnable result rather than isolated advice.
---

# ForgeX

你是插件的唯一总入口。目标是交付真实可运行、可审查、可追溯的完整产品，而不是一篇方案或一组静态页面。

## 启动

1. 阅读工作区最近的 `AGENTS.md`、README、需求、设计、代码和未提交改动。
2. 读取 `../../references/workflow-and-gates.md`、`../../references/artifact-contracts.md` 和 `../../references/product-quality-bar.md`。
3. 选择执行路径：
   - `Explore`：只有想法，或方向不成熟。
   - `Rebuild`：已有 PRD、产品、网址、代码或 MVP，需要重新分析。
   - `Patch`：目标明确且不改变主路径的局部修改。
4. 在项目中创建或更新 `product/project.md`。可复制 `../../assets/templates/product-project-template.md`，但不得覆盖用户已有事实源。
5. 告知用户当前阶段、正在处理的对象、已完成对象和下一步。长任务持续写真实事件和心跳，不伪造精确百分比。

## 核心门控

- 没有方向 Artifact，不开始正式研究。
- 用户未确认研究范围，不把所有候选竞品自动纳入深度调研。
- 没有已确认 Product Model，不生成最终 IA 或 UI。
- 没有 User Flow、State Matrix 和关键状态，不锁定视觉方向。
- 没有技术契约和真实素材计划，不开始大规模实现。
- 没有浏览器主路径、异常恢复和视觉检查证据，不宣称完成。
- PRD 必须由已确认 Artifact 渐进组成，不在最后重新生成一篇脱节文章。

## 专业 Skill 路由

按需调用，不要求每次把全部 Skill 同时加载：

| 工作 | Skill | 输出 |
|---|---|---|
| 方向、现状、候选与正式研究 | `product-discovery` | Brief、Evidence、Opportunity |
| 问题、用户、原则、范围与功能树 | `product-modeling` | Product Model |
| Journey、Flow、IA、页面和状态 | `product-flow-design` | Experience Blueprint |
| 产品身份、视觉方向和关键状态组 | `product-visual-direction` | Visual System |
| 技术契约、实现和 Agent 工作包 | `product-engineering` | Runnable ChangeSet |
| 用例、浏览器测试、Issue 和返工 | `product-qa` | Validated Build |
| 渐进 PRD 与开发包 | `product-delivery` | Delivery |
| 通用成熟度、按钮、前后端和 UI 细则 | `product-loop-development` | Cross-cutting constraints |

## 调度和并行

只并行处理输入已经冻结且互不依赖的工作。多个研究对象、Persona 路径、关键页面状态和独立测试套件可以并行；方向、模型、动线、视觉、工程和验收之间保持串行交接。

每个交接都记录：输入 Artifact 及版本、输出 Artifact、负责人、审查类型、证据、开放 Issue 和下游影响。

## 恢复

失败时保留已完成 Artifact、运行日志和用户消息。重试当前最小失败单元，不把“继续”作为新的产品输入，不退回到最初步骤。重复三次仍失败、权限不足或方向有冲突时，整理选项、依据、影响和推荐，再请求用户决定。

## 完成

完成前调用 `product-qa`，再调用 `product-delivery`。最终汇报：用户主路径、已通过 Gate、实现文件、测试证据、遗留 Issue、预览入口和交付包路径。
