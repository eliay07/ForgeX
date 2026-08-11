# ForgeX 工作流与质量门

本文是插件所有 Skill 的唯一阶段协议。阶段可以按任务深度裁剪，但已启用阶段的 Gate 不得伪造通过。

## 1. 三条执行路径

| 路径 | 适用情况 | 必经阶段 |
|---|---|---|
| Explore | 只有一句想法，方向尚不成熟 | 方向澄清 -> 候选参考 -> 产品模型 -> 动线 -> 视觉 -> 实现 -> QA -> 交付 |
| Rebuild | 已有 MVP、仓库、页面或 PRD，需要重做 | 基线审计 -> 差距分类 -> 产品模型 -> 动线 -> 视觉 -> 实现 -> QA -> 交付 |
| Patch | 目标明确、改动局部、没有改变主路径 | 影响审计 -> 局部规格 -> 实现 -> 定向 QA -> 交付 |

出现以下任一情况时，Patch 自动升级为 Rebuild：改变目标用户、核心任务、导航模型、主数据对象、权限模型或超过两个主要页面。

## 2. 阶段和 Gate

| 阶段 | 主要 Artifact | 审查类型 | 通过条件 |
|---|---|---|---|
| 0 工作区基线 | WorkspacePolicy、ProjectSnapshot、CurrentFlowAudit | Checkpoint | 事实与现状可复核 |
| 1 方向与研究 | InitialDirectionBrief、CandidateReference、Evidence | Hard Gate A/B/C | 用户确认方向与正式研究范围；结论有来源 |
| 2 产品模型 | ProductModel、FeatureTree、Priority、Risk | Hard Gate D | 问题、用户结果、范围和原则一致 |
| 3 动线与结构 | Journey、TaskFlow、UserFlow、IA、StateMatrix、Wireflow | Hard Gate E/F | 主路径、错误与恢复无死路 |
| 4 原型与视觉 | Prototype、ProductIdentity、VisualDirection、ScreenStateSet | Hard Gate G/H | 可操作原型通过；视觉状态组统一 |
| 5 工程实现 | TechnicalContract、ExecutionDAG、ChangeSet | Checkpoint | 纵向闭环可运行，过程可追溯 |
| 6 QA 与返工 | TestCase、Evidence、Issue、Rework | Hard Gate I | 主路径、异常、视觉和可访问性通过 |
| 7 交付 | ProgressivePRD、DeliveryManifest、Runbook | Hard Gate J | 产物从已确认 Artifact 组装且可打开 |

## 3. 审查语义

- **Hard Gate**：高返工半径的人类决定。未批准时禁止启动依赖它的下游工作。
- **Checkpoint**：低风险、可逆的中间确认。允许继续，但必须记录未解决项。
- **Observable Step**：自动执行过程，仅用于追踪，不要求用户逐条确认。
- **Stop Condition**：权限、删除、覆盖、付费、外部发布、方向冲突或证据不足等必须停下的情况。

不得把 Observable Step 做成一长排需要用户点击的确认项。不得把 AI 建议标记为人工确认。

## 4. 并行规则

可并行：

- 已确认研究范围内的多个竞品。
- 已确认用户模型下的多个 Persona 路径。
- 同一视觉方向下互不依赖的关键页面状态。
- 所有者不同且契约已冻结的工程工作包。
- 独立测试套件。

必须串行：

- 方向确认 -> 正式研究。
- Product Model -> User Flow -> IA。
- 视觉方向选择 -> 页面状态组实现。
- 技术契约 -> 代码实现。
- 缺陷定位 -> 定向返工 -> 回归验证。

## 5. 上游变更

修改已批准 Artifact 时必须：

1. 创建新版本，不覆盖旧版本。
2. 列出直接依赖和间接依赖。
3. 将受影响下游标为 `review_required` 或 `stale`。
4. 给出最小返工范围，禁止默认整条流程重跑。
