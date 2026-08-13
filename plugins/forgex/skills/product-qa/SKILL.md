---
name: product-qa
description: Validate a runnable digital product through representative user flows, browser automation, screenshots, responsive and accessibility checks, issue ownership, targeted repair, and regression. Use before delivery or when a product is broken, slow, visually inconsistent, stuck, or failing to recover.
---

# Product QA

像真实用户一样测试产品，而不是只检查构建是否成功。先读 `../../references/qa-and-user-flow.md`、`../../references/product-quality-bar.md` 和 `../../references/user-product-preferences.md`。

## 流程

1. 从已确认 Persona、User Flow、State Matrix 和 Acceptance Criteria 生成测试矩阵。
2. 启动真实应用，验证第一个可操作页面和主路径。
3. 覆盖 Happy Path、首次使用、空状态、输入错误、服务失败、中断恢复、权限与取消。
4. 使用 Playwright 或仓库既有工具执行浏览器操作；关键状态必须截图，不能只靠 DOM 断言。
5. 检查网络、控制台、数据结果、可观测日志、长任务心跳与重试。
6. 在移动端、平板和桌面验证焦点、文字完整、溢出、遮挡、触控尺寸、键盘、对比度和 Reduced Motion。
7. 将运行截图与批准的关键状态组母版并排检查结构、层级、色彩、字体、图标、素材和动效一致性。
8. 执行偏好回归：30 秒扫读、长列表折叠、滚动稳定、取消完成、归档恢复、自然语言 AI 预览、重复/空白数据过滤、Copilot 唤起与遮挡。
9. 不只验证目标控件；用户指出一个问题时，检查同类组件和造成问题的共享状态逻辑。

## Issue 与返工

发现问题时创建结构化 Issue，定位到责任 Artifact 或代码模块。自动修复采用“最小修复 -> 定向测试 -> 受影响主路径回归”，最多三轮。不能把局部失败变成全量重生成。

方向冲突、破坏性操作、三轮仍失败或需要用户偏好的问题升级为 Hard Gate。

## 通过条件

Blocker 和 High Issue 已关闭或被用户明确接受；主路径和至少一个异常恢复有证据；构建、类型检查、测试和浏览器验证通过。输出 TestReport、Evidence、Issue、ReworkTrace 与残余风险。
