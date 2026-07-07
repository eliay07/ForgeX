# 前端样本库与产品身份差异化

## 一句话原则

每个产品都必须先形成自己的产品身份，再选择前端参考样本。参考样本用于降低实现下限，不用于复制旧项目、复制其他产品或复用上一个项目的视觉壳。

## 必须避免的问题

Codex 做前端时常见失败：

- 复用上一个项目的页面结构、配色、圆角、字号和文案节奏。
- 所有 AI 工具都长得像同一个浅绿色工作台。
- 只根据功能写 UI，不先定义产品名字、气质、目标用户和品牌记忆点。
- 直接套组件库默认样式，导致产品没有独立辨识度。
- 参考了一个好看的页面，但没有分析它为什么适合当前产品。
- 把参考站的具体文案、导航、品牌色、图形语言原样搬过来。

解决方式：每次开工前必须做“产品身份卡 + 样本选型表 + 不照抄声明”。

## 产品身份卡

前端实现前先填写：

```text
产品临时名称:
一句话定位:
目标用户:
使用场景:
情绪目标: 专业 / 可信 / 温暖 / 轻快 / 高效 / 创意 / 克制 / 游戏化
信息密度: 低 / 中 / 高
视觉关键词: 3 到 5 个
不适合的视觉方向:
Logo 方向:
主色方向:
辅助色方向:
组件气质: 轻量 / 工具型 / 编辑器型 / 数据型 / 内容型 / 叙事型
与上一个项目必须不同的地方:
```

如果产品没有名字、logo 方向、色彩方向和气质判断，不要开始写 CSS。

## 前端样本选择流程

每次做新产品或大改前端时：

```text
1. 选择产品类型: AI 工具 / SaaS 工作台 / 内容工具 / 数据后台 / 官网 / 移动端 / 编辑器 / 商业化页面。
2. 从样本库选 2 到 3 个参考来源。
3. 只抽象结构、组件关系、信息密度、交互模式、空间比例和状态处理。
4. 为当前产品生成独立名字、logo、色卡、字体层级和组件 token。
5. 明确哪些东西不能学。
6. 再进入实现。
```

## 样本库

### 1. 通用组件与 blocks

| 样本 | 适合参考 | 不要照抄 |
|---|---|---|
| [shadcn/ui Blocks](https://ui.shadcn.com/blocks) | dashboard、sidebar、auth、calendar、task、chart 等可组合应用结构 | 不要保留默认黑白灰视觉和示例文案 |
| [shadcn/ui Components](https://ui.shadcn.com/docs/components) | Dialog、Sheet、Popover、Command、Tabs、Table、Form 等成熟交互组件 | 不要所有产品都变成同一种 shadcn 默认样式 |
| [Radix Themes](https://www.radix-ui.com/themes/docs/overview/getting-started) | 可访问组件、主题 token、深浅色模式 | 不要把 Radix 默认品牌感当成产品品牌 |
| [Tailwind UI](https://tailwindcss.com/plus/ui-blocks) | SaaS、marketing、dashboard、settings、form 的高质量布局参考 | 商业授权组件不要直接复制进未授权项目 |
| [Untitled UI](https://www.untitledui.com/) | 专业 SaaS 组件尺寸、表单、表格、空状态和 dashboard 密度 | 不要复刻其品牌色和营销页文案 |
| [SaaS UI](https://saas-ui.dev/) | React SaaS app shell、settings、billing、auth、onboarding | 不要默认变成企业后台 |
| [Mantine UI](https://ui.mantine.dev/) | 数据型工具、表单、settings、charts、admin panels | 不要使用过多默认蓝紫色 |
| [Tremor Blocks](https://tremor.so/blocks) | 指标、图表、数据 dashboard、监控表面 | 不要把 ToC 产品做成指标后台 |
| [Flowbite Blocks](https://flowbite.com/blocks/) | landing、dashboard、forms、tables、ecommerce 常见布局 | 不要照搬 Tailwind 默认审美 |
| [Aceternity UI](https://ui.aceternity.com/) | 需要动效、微交互、展示型 hero 的局部组件 | 不要滥用发光、粒子、炫技动效 |

### 2. 真实产品截图和流程库

| 样本 | 适合参考 | 不要照抄 |
|---|---|---|
| [Mobbin](https://mobbin.com/) | 移动端、SaaS、AI 产品、onboarding、paywall、settings 等真实产品截图 | 不要复制真实产品视觉资产 |
| [Page Flows](https://pageflows.com/) | 注册、订阅、搜索、编辑、分享、升级等完整用户流程 | 不要只看单屏，要看步骤关系 |
| [UI Sources](https://www.uisources.com/) | 成熟产品的真实交互流程和页面结构 | 不要把截图当 UI kit |
| [SaaS UI Design](https://www.saasui.design/) | SaaS dashboard、pricing、settings、teams、billing、empty state | 不要把所有产品做成 SaaS 后台 |
| [SaaSFrame](https://www.saasframe.io/) | SaaS 官网、landing、pricing、feature section | 不要把工具首页做成纯营销页 |
| [Land-book](https://land-book.com/) | 官网、品牌页、产品首屏、视觉气质 | 不要用 landing 结构承载复杂工作流 |
| [Lapa Ninja](https://www.lapa.ninja/) | landing page、startup 页面、转化页 | 不要只学视觉，不学信息层级 |
| [Godly](https://godly.website/) | 高质量网页视觉参考 | 不要为普通工具强行动效化 |
| [Awwwards](https://www.awwwards.com/) | 品牌、互动、WebGL、沉浸式体验 | 不要把性能重的效果塞进普通产品 |

### 3. AI 产品和生成式交互

| 样本 | 适合参考 | 不要照抄 |
|---|---|---|
| [AI UX Playground](https://www.aiuxplayground.com/) | AI 输入、生成、解释、确认、引用、反馈等模式 | 不要把方法名堆给用户 |
| [Vercel AI Elements](https://ai-sdk.dev/elements/overview) | 对话、响应、工具调用、sources、reasoning、actions 等 AI UI 组件 | 不要让 AI UI 只剩聊天框 |
| [assistant-ui](https://www.assistant-ui.com/) | React AI chat、thread、composer、artifact 模式 | 不要默认把所有 AI 产品做成聊天产品 |
| [CopilotKit](https://www.copilotkit.ai/) | 应用内 copilot、上下文感知操作、AI 辅助工作流 | 不要让 copilot 抢主流程 |
| [Chatbot UI](https://github.com/mckaywrigley/chatbot-ui) | ChatGPT-like 基础对话产品结构 | 不要用于非聊天型主任务 |

### 4. 编辑器、工作台和复杂工具

| 样本 | 适合参考 | 不要照抄 |
|---|---|---|
| [tldraw](https://www.tldraw.com/) | 画布、工具栏、浮动面板、对象编辑 | 不要把非画布任务硬做成白板 |
| [React Flow / xyflow](https://reactflow.dev/) | 节点流程、自动化、任务依赖、可视化工作流 | 不要用节点图表达简单线性流程 |
| [Excalidraw](https://github.com/excalidraw/excalidraw) | 轻量画布、手绘感协作、工具状态 | 不要把手绘风强加给专业工具 |
| [Monaco Editor](https://microsoft.github.io/monaco-editor/) | 代码/规则/配置编辑器 | 不要用代码编辑器承载普通表单 |
| [React Resizable Panels](https://github.com/bvaughn/react-resizable-panels) | IDE-like 多面板工作区 | 不要所有面板默认展开 |

### 5. 视觉、logo 和品牌灵感

| 样本 | 适合参考 | 不要照抄 |
|---|---|---|
| [Brandfetch](https://brandfetch.com/) | 了解成熟品牌 logo、色彩和应用系统 | 不要复制品牌资产 |
| [Logo System](https://logosystem.co/) | logo 结构、符号、网格和品牌系统思路 | 不要只做一个图标，不做应用规则 |
| [Fonts In Use](https://fontsinuse.com/) | 字体气质、行业对应和排版参考 | 不要使用未授权字体 |
| [Coolors](https://coolors.co/) | 初步色板生成和对比参考 | 不要把随机色板当设计系统 |
| [Realtime Colors](https://www.realtimecolors.com/) | 快速检查色彩在页面上的主次关系 | 不要跳过语义 token |

## 产品类型与推荐样本

### AI 产品经理 / PRD 工具

推荐参考：

```text
AI UX Playground: 生成、确认、解释、反馈模式。
Vercel AI Elements: AI 响应结构、reasoning、sources、actions。
shadcn/ui Blocks: app shell、sidebar、form、dialog、tabs。
Mobbin / Page Flows: onboarding、文档生成、确认流程。
```

应形成的独立方向：

```text
产品气质: 可信、专业、低干扰、决策型。
主界面: idea 输入 + 必要确认 + 结论/PRD 阅读。
Logo: 文档、罗盘、印章、审阅标记、结构化节点等方向。
颜色: 不默认沿用上一项目的浅绿；可以根据“可信/决策/文档”选择墨蓝、石墨、深青、纸白、琥珀强调等。
```

### 一人公司创作者工具

推荐参考：

```text
Mobbin: 创作、草稿、发布、个人库流程。
tldraw / Excalidraw: 创作工具中的对象状态和浮动工具。
Aceternity UI: 少量动效作为入口反馈。
```

### SaaS / B2B 工作台

推荐参考：

```text
Untitled UI、SaaS UI、Tremor、shadcn Blocks、SaaS UI Design。
```

### 数据分析 / 监控

推荐参考：

```text
Tremor Blocks、SaaS UI Design、Mantine UI、Atlassian 产品页面。
```

### 官网 / 商业转化页

推荐参考：

```text
Land-book、Lapa Ninja、SaaSFrame、Tailwind UI marketing blocks。
```

### 沉浸式品牌体验

推荐参考：

```text
Awwwards、Godly、Active Theory、WebGL 案例。
```

## 不照抄规则

从任何样本中只能借鉴：

```text
页面结构
组件职责
空间比例
状态处理
交互方式
信息密度
视觉层级
```

不能复制：

```text
产品名
logo
品牌色
文案
图形资产
业务对象
导航标签
具体数据
旧项目的视觉壳
```

## 开工前检查清单

```text
是否为当前产品生成了独立名称。
是否有 logo 方向，而不是只放 lucide 图标。
是否有 2 到 3 个样本来源。
是否说明每个样本借鉴什么、不借鉴什么。
是否为当前产品生成独立色卡和 token。
是否明确与上一个项目不同的视觉和结构。
是否避免默认套 dashboard、landing 或旧项目壳。
是否把样本抽象成组件策略，而不是复制页面。
```

## 给 Codex 的硬约束句

```text
做前端前，先建立当前产品自己的产品身份卡和前端样本选型表。不要复用上一个项目的名称、色卡、logo、圆角、组件尺寸、首页结构或文案节奏。至少选择 2 个合适的前端样本，说明借鉴结构、组件和信息密度的原因，再生成当前产品独立的名字、logo 方向、配色 token、组件风格和不照抄清单。
```
