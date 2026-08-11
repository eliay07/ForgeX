---
name: product-discovery
description: Clarify a product direction and research the market or an existing MVP with evidence. Use for idea intake, optional brainstorming, repository or file analysis, competitor discovery, formal research scope, evidence libraries, current-flow audits, and opportunity synthesis before product design.
---

# Product Discovery

把模糊输入或现有产品转成可确认的方向与证据，不直接跳到功能清单。

## 入口

- 只有想法：提取事实与未知项；按需开启头脑风暴；提出不超过 6 到 8 个高价值问题，允许“暂不确定”。
- 已有项目：先读真实文件、路由、数据、页面和运行结果，生成 ProjectSnapshot 与 CurrentFlowAudit。
- 用户明确只做局部修改：判断是否仍适合 Patch；若改变主路径则升级为 Rebuild。

## 头脑风暴

头脑风暴是可选阶段。按用户价值、场景、差异化、商业、技术、风险等维度各给多个可编辑建议；允许选择、删除、改写和新增。选中的内容进入 Direction Brief，未选择内容保留为备选，不伪装成已确认需求。

## 研究

1. 先生成直接竞品、间接竞品、替代方案、流程或视觉参考的轻量候选卡。
2. 每张卡写定位、目标用户、核心任务、相关理由、值得学、不相关风险和来源。
3. 等用户选择正式对象、学习重点、深度、时间与预算后再深入研究。
4. 正式研究覆盖定位、功能树、关键 User Flow、页面地图、UI/UX 模式、设计系统、用户评价、摩擦和机会。
5. 每条结论标记 `fact`、`inference`、`user_voice` 或 `ai_suggestion` 并挂接来源。无法验证时明确写未知。

## 输出

- `InitialDirectionBrief`
- `ProjectSnapshot` 与 `CurrentFlowAudit`（已有项目）
- `CompetitorCandidate[]`
- `ResearchScope`
- `Evidence[]`、`PatternLibrary`、`OpportunityMap`

Direction、ResearchScope 和研究结论分别对应 Hard Gate。用户可以采用、参考、不适用、不照抄、补证据或继续研究。

