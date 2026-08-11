---
name: product-visual-direction
description: Create and lock a coherent product identity and visual direction before UI implementation. Use for reference boards, visual DNA, three design directions, GPT-generated key screen state concepts, design tokens, component language, imagery plans, responsive behavior, motion, and visual review.
---

# Product Visual Direction

借鉴 GameX 的“先整页、后拆解”：先锁定产品的关键状态组母版，再生成组件、素材和代码。先读取 `../../references/visual-master-and-assets.md` 与 `../../references/product-quality-bar.md`。

## 顺序

1. 从 Product Model、User Flow 和页面状态中提取产品人格、任务密度、情绪与实现约束。
2. 搜索或整理高质量完整产品参考，只抽取结构、层级、状态和视觉规律。
3. 生成三个在结构与气质上真正不同的方向；每个写 Visual DNA、适用场景、风险、成本、借鉴与不照抄项。
4. 人工选择一个方向或明确局部融合，形成唯一 Product Identity 与 Visual DNA。
5. 从 User Flow 选 4 到 8 个关键状态，使用 GPT 图像生成或设计工具生成一致的页面状态组。图片生成失败要标记失败并允许指定页面重试；不要自动多轮自审生图。
6. 视觉检查通过后，拆解 Design Token、组件、图标、素材、动效和响应式规范。

## 约束

- 主要产品页面必须齐全，不只生成首页。
- 状态组共享导航、组件语法、色彩角色、字体和信息层级。
- 生图是视觉方向和 bitmap 素材，不替代真实可交互页面。
- 页面必须有清楚焦点；避免所有模块卡片化、同权重和解释文字堆叠。
- 所有生成图保存提示词、版本、目标页面和来源。

## 输出

`ProductIdentity`、`VisualDirection[]`、`ScreenStateSet`、`DesignTokens`、`ComponentLanguage`、`AssetPlan`、`MotionSpec`。方向、状态组和设计系统分 Checkpoint 审查，最终通过 Hard Gate H 后交给工程。

