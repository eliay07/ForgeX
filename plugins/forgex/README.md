# ForgeX Plugin

ForgeX 是一个从产品想法或现有 MVP 出发，完成研究、Product Model、用户动线、视觉方向、真实代码实现、浏览器 QA 和可追溯交付的 Codex 插件。

## 总入口

使用 `forgex` Skill。它会在以下路径中选择合适深度：

- `Explore`：从一句想法开始。
- `Rebuild`：审计并改造已有产品。
- `Patch`：完成不改变主路径的局部修改。

## 质量门

- 未确认方向，不开始正式研究。
- 未确认 Product Model，不生成最终 IA 或 UI。
- 未通过用户动线和页面状态审查，不锁定视觉方向。
- 未完成技术契约，不开始大规模实现。
- 未通过浏览器主路径、异常恢复和视觉检查，不宣称完成。

完整介绍、安装方法和使用示例见 [ForgeX GitHub](https://github.com/eliay07/ForgeX)。
