---
name: product-flow-design
description: Design a product's end-to-end experience architecture from an approved Product Model. Use for journeys, task flows, user flows, service blueprints, information architecture, navigation, page maps, progressive disclosure, state matrices, content models, wireflows, and low-fidelity prototype plans.
---

# Product Flow Design

产品设计的核心不是页面列表，而是不同起始状态的用户如何顺畅到达结果。

## 流程

1. 枚举会改变下一步的用户起始状态，例如只有想法、已有材料、已有项目、中断恢复、服务失败。
2. 为每个核心 Persona 生成端到端 Journey。
3. 为每个核心目标生成 Task Flow。
4. User Flow 必须包含入口、决策、取消、错误、保存、恢复和终点。
5. Service Blueprint 映射前台、后台、AI、数据与人工动作。
6. Persona 遍历路径并报告死路，但不得代替真实用户宣布可用。
7. 在 Flow 通过后生成 Domain Model、导航、路由、页面清单、Content Model、State Matrix 和 Wireflow。

## 层级

- L0：固定壳层与全局导航。
- L1：当前主任务与一个主动作。
- L2：可收起上下文、检查器或历史。
- L3：临时决策层，如菜单、Popover、Drawer、Modal。
- L4：深层详情、版本、证据和高级设置。

不得把 L0 到 L4 全部默认展开。任何可收起区域必须保留可见、可聚焦的恢复入口。

## 每页规格

每页写目的、入口、主任务、主动作、完成去向、数据对象、默认状态、空/加载/错误/权限/恢复状态和响应式变化。每个 View 默认一个 Primary Action。

## 输出与审查

先用 Hard Gate E 审主要路径和异常恢复，再用 Hard Gate F 审 IA、页面职责、状态与移动端。最后生成 P0 可点击低保真计划，交给 `product-visual-direction`。

