# Artifact 与追溯契约

所有专业产物都应是可编辑、可版本化的结构化 Artifact。Markdown 可以作为阅读视图，但不能成为唯一事实源。

## 1. 最小公共字段

```yaml
id: artifact-id
type: ProductModel
version: 0.3.0
status: hypothesis | ai_suggested | human_confirmed | validated | deprecated
owner: product-modeling
created_at: ISO-8601
updated_at: ISO-8601
sources: []
dependencies: []
decisions: []
issues: []
change_impact: []
```

## 2. Agent 运行记录

```yaml
run_id: run-id
stage: product-model
agent: product-modeling
model: model-name-or-local-codex
started_at: ISO-8601
heartbeat_at: ISO-8601
status: queued | running | waiting_human | succeeded | failed | cancelled
inputs: []
outputs: []
events: []
error: null
retry_of: null
```

长任务必须至少输出阶段事件与心跳。不得伪造精确百分比；可以展示已完成对象数、当前对象和下一步。

## 3. 建议和决定

每项 AI 建议至少包含：建议、理由、证据或依据、置信度、替代方案、下游影响。人工动作记录接受、修改、拒绝、暂缓或退回，不得只保存最终文本。

## 4. 用户偏好

```yaml
id: preference-id
statement: ""
scope: global | product-family | local
category: information | interaction | visual | ai-behavior | accessibility
status: observed | confirmed | superseded
confidence: low | medium | high
evidence:
  - date: ISO-8601
    source: user-feedback
    quote_or_summary: ""
applies_to: []
exceptions: []
supersedes: []
```

偏好必须来自明确反馈或重复证据。一次性要求默认保留在当前项目；长期档案只保存稳定规律。最新明确要求可以覆盖旧偏好，但必须保留 supersedes 关系，不静默删除历史。

## 5. Issue

```yaml
artifact: artifact-id
stage: flow
severity: blocker | high | medium | low
category: usability | logic | data | visual | accessibility | performance | reliability
expected: ""
actual: ""
evidence: []
owner: product-flow-design
status: open | fixing | verifying | resolved | accepted_risk
```

Issue 必须退回责任 Artifact；修复后创建新版本并执行受影响范围的回归测试。

## 6. 文件落地

推荐项目目录：

```text
product/
  project.md
  artifacts/
  evidence/
  decisions/
  issues/
  traces/
  prototypes/
  visual/
  delivery/
```

`product/project.md` 是索引与当前状态，不是把所有长文复制一遍。每个目录中的文件名包含稳定 ID 和版本号。
