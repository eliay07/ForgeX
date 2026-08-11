# ForgeX

**从一句想法或现有 MVP，到可运行、可测试、可交付的完整产品。**

ForgeX（造物引擎）是一个面向 Codex 的产品生产 marketplace。它将产品发现、竞品研究、Product Model、用户动线、信息架构、视觉方向、工程实现、浏览器测试和交付组织成一条可追溯的流水线。

ForgeX 不追求“一次提示词生成大量页面”，而是让每个下游结果都来自已经审查的上游 Artifact，并在实现完成后通过真实用户路径测试和定向返工。

> 当前版本：`v0.3`。已经具备完整工作流和专业 Skill，但仍处于真实项目验证阶段。详见[当前边界](#当前边界)。

## 核心能力

- 支持从一句话想法开始，也支持分析和重构已有产品、PRD 或代码仓库。
- 可选头脑风暴，从多个维度生成、筛选、修改和补充产品建议。
- 先发现候选竞品，再由用户确认正式研究范围，不默认深挖全部对象。
- 生成可审查的 Product Model、功能树、版本边界、假设和风险。
- 根据不同用户起点生成 Journey、Task Flow、User Flow 和 Service Blueprint。
- 设计 IA、页面地图、状态矩阵、Wireflow 和渐进披露层级。
- 先锁定 Product Identity 和关键页面状态组，再拆解 Token、组件和素材。
- 使用 Codex 修改真实代码，并记录 Execution DAG、文件所有权和运行 Trace。
- 根据典型用户编写测试用例，执行真实浏览器测试、截图检查、定向修复和回归。
- 从已确认 Artifact 组装渐进式 PRD 与完整开发包，不在最后重新生成脱节长文。

## 三种工作模式

| 模式 | 适用情况 | 典型流程 |
|---|---|---|
| `Explore` | 只有想法，方向尚不成熟 | 澄清 -> 研究 -> 产品模型 -> 动线 -> 视觉 -> 开发 -> QA -> 交付 |
| `Rebuild` | 已有 MVP、代码、PRD 或页面，需要重新分析 | 基线审计 -> 差距分类 -> 产品模型 -> 动线 -> 视觉 -> 改造 -> QA -> 交付 |
| `Patch` | 目标明确且不改变主路径的局部修改 | 影响审计 -> 局部规格 -> 实现 -> 定向 QA -> 交付 |

当修改影响目标用户、核心任务、导航、主要数据对象、权限或多个主要页面时，ForgeX 会把 `Patch` 自动升级为 `Rebuild`。

## 工作流

```text
输入想法或现有项目
        ↓
方向澄清与研究范围                     Hard Gate
        ↓
Product Model 与功能树                 Hard Gate
        ↓
用户动线、IA、页面和状态                Hard Gate
        ↓
原型、产品身份与关键页面状态组           Hard Gate
        ↓
技术契约、Execution DAG 与真实代码实现   Checkpoint
        ↓
浏览器测试、Issue、定向修复与回归         Hard Gate
        ↓
渐进式 PRD、可运行产品与开发包            Delivery
```

### 一键完成的边界

ForgeX 会自动执行低风险、可恢复的工作，并在输入冻结后并行处理竞品、Persona 路径、页面状态或测试套件。但以下决定仍需要人工确认：

- 产品方向和目标用户。
- 正式竞品研究范围。
- Product Model、版本边界和核心动线。
- 视觉方向与关键页面状态组。
- 删除、覆盖、付费、部署和外部发布。
- 无法自动解决的产品冲突与高风险 Issue。

因此，“一键完成”表示 **每个关键决策之间自动推进到真实结果**，不是绕过用户判断。

## 安装

### 从 GitHub 安装

```bash
codex plugin marketplace add https://github.com/eliay07/ForgeX.git
codex plugin add forgex@forgex
```

安装完成后开启一个新 Codex 线程，让新的 Skill 被加载。

### 本地开发安装

```bash
git clone https://github.com/eliay07/ForgeX.git
codex plugin marketplace add /absolute/path/to/ForgeX
codex plugin add forgex@forgex
```

更新 marketplace 后可运行：

```bash
codex plugin marketplace upgrade forgex
codex plugin add forgex@forgex
```

## 快速开始

### 从一句想法开始

```text
使用 ForgeX。我有一句产品想法：<你的想法>。
先判断是否需要头脑风暴，再完成研究、产品模型、动线、视觉、开发、测试修复和交付。
```

### 改造已有产品

```text
使用 ForgeX 审计当前项目。保留正确实现，读取现有 PRD、代码和页面，
从最合理的未完成节点继续改造成完整产品，不要推倒重来。
```

### 只做局部修改

```text
使用 ForgeX 的 Patch 模式完成这个修改。先说明影响范围，
实现后运行定向测试和受影响主路径回归。
```

### 验收已有产品

```text
使用 ForgeX 根据典型用户和主路径编写测试用例，
在真实浏览器中测试、保存截图证据、修复问题并完成回归。
```

## 专业 Skill

| Skill | 职责 | 主要产物 |
|---|---|---|
| `forgex` | 总入口、路径判断、调度和恢复 | Project Index、阶段状态、交接记录 |
| `product-discovery` | 方向、头脑风暴、项目审计和研究 | Direction Brief、Evidence、Opportunity Map |
| `product-modeling` | 用户、价值、原则、功能和范围 | Product Model、Feature Tree、Risk Register |
| `product-flow-design` | 动线、IA、页面、状态和低保真 | Journey、User Flow、State Matrix、Wireflow |
| `product-visual-direction` | 产品身份、视觉方向和页面状态组 | Visual DNA、Screen State Set、Tokens、Asset Plan |
| `product-engineering` | 技术契约、工作包和真实实现 | Technical Contract、Execution DAG、ChangeSet |
| `product-qa` | 用例、浏览器验证、Issue 和返工 | Test Report、Evidence、Issue、Rework Trace |
| `product-delivery` | PRD、预览、源码和开发包 | Progressive PRD、Delivery Manifest、Runbook |
| `product-loop-development` | 跨阶段产品与工程质量标准 | IA、交互、前后端契约和成熟度约束 |

ForgeX 还包含计划、主题、Web 测试、迁移、部署、Sentry、变更日志和反馈分流等辅助 Skill，由总入口按需使用。

## Artifact 与审查

ForgeX 将专业产物保存为可编辑、可版本化的 Artifact。每个 Artifact 记录：

- 状态：`hypothesis`、`ai_suggested`、`human_confirmed`、`validated` 或 `deprecated`。
- 来源、依赖、版本和前后差异。
- AI Agent、模型与运行 Trace。
- 人工接受、修改、拒绝和批注。
- Issue、责任阶段和下游影响。

审查分为三类：

- `Hard Gate`：高返工半径的人类决定，未批准不能启动下游。
- `Checkpoint`：低风险、可逆的阶段确认。
- `Observable Step`：只展示自动执行进度，不要求用户逐条点击。

## 交付内容

完整流程可交付：

- Product Brief、研究证据和机会地图。
- Product Model、Feature Tree 和版本边界。
- Journey、Task Flow、User Flow 和 Service Blueprint。
- 页面地图、状态矩阵、Wireflow 和原型。
- 视觉方向、关键页面状态组、Token、组件和素材计划。
- PRD v1.0、API/Data Contract 和 Acceptance Criteria。
- 可运行源码、构建产物或预览入口。
- 测试用例、截图证据、Issue 和回归结果。
- 决策记录、版本索引、风险和 Runbook。

## 仓库结构

```text
ForgeX/
├── .agents/plugins/marketplace.json   # Codex marketplace 注册
├── plugins/forgex/
│   ├── .codex-plugin/plugin.json      # 插件元数据
│   ├── skills/                        # 总入口、专业与辅助 Skill
│   ├── references/                    # Gate、Artifact、视觉和 QA 协议
│   ├── assets/templates/              # 项目与 Artifact 模板
│   └── THIRD_PARTY_NOTICES.md
└── README.md
```

## 验证

插件开发完成后应运行：

```bash
python3 /path/to/plugin-creator/scripts/validate_plugin.py plugins/forgex
bash plugins/forgex/skills/product-loop-development/scripts/check-product-loop.sh <project-path>
```

ForgeX 的“完成”要求至少包括：真实主路径可运行、一个异常路径可恢复、关键视口无阻断问题、Blocker/High Issue 已关闭或接受风险、交付文件真实可打开。

## 当前边界

ForgeX `v0.3` 是一套已经可安装的工作流插件，但不是独立 SaaS 或后台服务：

- Artifact、Gate 和 Trace 目前由 Skill 协议约束，尚无独立状态机服务。
- 没有专用素材 MCP；视觉生成使用当前 Codex 环境中可用的 GPT 图像或设计工具。
- 研究、代码执行和浏览器测试取决于当前 Codex 会话拥有的工具与权限。
- 尚未建立覆盖多种产品类型的公开评测集和稳定性基准。
- 不承诺在没有人工产品决策的情况下全自动发布生产系统。

下一阶段重点是 Artifact Schema 校验器、项目脚手架、标准化评测样例和真实项目前向测试。

## 方法参考与鸣谢

ForgeX 的“总导演 Skill + 专业 Skill + 阶段 Artifact + 强制质量门 + 真实运行验收”结构，参考了 GameX Plugin 在游戏策划、美术母版、素材、实现和 Playtest 之间的职责拆分方式。

ForgeX 只借鉴可泛化的方法，并将其重新设计为产品发现、Product Model、用户动线、关键页面状态组、工程契约和浏览器 QA。没有复制 GameX 的游戏专用代码、素材、MCP 服务、私有接口或运行时实现。

其他方法与第三方 Skill 来源见 [THIRD_PARTY_NOTICES.md](plugins/forgex/THIRD_PARTY_NOTICES.md)。

## License

本仓库为混合来源插件集合。第三方 Skill 沿用各自许可证；没有单独许可证的内容不在本仓库中重新授权。发布、分发或商用前请检查 [THIRD_PARTY_NOTICES.md](plugins/forgex/THIRD_PARTY_NOTICES.md) 及对应目录中的许可证文件。
