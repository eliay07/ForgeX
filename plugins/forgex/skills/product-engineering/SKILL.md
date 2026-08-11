---
name: product-engineering
description: Turn approved product, flow, visual, and data artifacts into a runnable product with Codex. Use for repository implementation, technical contracts, execution DAGs, agent work packages, frontend/backend integration, real file changes, observability, recovery, and incremental delivery.
---

# Product Engineering

实现已批准的产品，不重新发明需求。先读仓库约束、未提交改动、已确认 Artifact 和 `../../references/artifact-contracts.md`。

## 实现前契约

必须生成 `TechnicalContract`：

- 技术栈与沿用理由。
- 领域实体、字段、关系、权限和事实源。
- API 请求、响应、错误、重试、幂等与取消。
- 页面、组件、状态与路由所有权。
- 素材清单和真实路径。
- 分析事件、性能、可访问性和安全要求。
- 每个 Feature 的验收条件和测试入口。

## Execution DAG

把工作拆成有输入输出的可验证包。只有输入 Artifact 已冻结、文件所有权不冲突时才并行。每个包写：

```yaml
work_package: WP-001
requirements: []
input_artifacts: []
owned_files: []
depends_on: []
acceptance: []
tests: []
```

## 实现规则

- 优先打通一条真实纵向闭环，再扩展次要模块。
- 保留仓库正确实现和既有模式；不要覆盖不属于本任务的改动。
- UI 动作必须连接真实状态、接口或明确的本地能力。
- 长任务输出真实事件、当前对象、已完成数、下一步和心跳。失败时保留上下文，重试最小失败单元。
- 删除、覆盖、权限提升、外部写入、部署或付费必须经过确认。
- 每个 Milestone 完成后立即运行对应测试，更新 Artifact、Trace 和 Issue。

## 交接

输出 `ChangeSet`、`Runbook`、实现 Trace、预览地址与已知 Issue。不得自行宣布完成；交给 `product-qa` 以真实浏览器路径验收。

