# Agent Operating Model Kit

一套可复用的方法论工具包，用来把 agent 系统运行成一个**围绕单一核心客户长期运转的微型 AI 组织**。

这个仓库不是新的执行引擎，而是一套**治理层打包物**：包含完整宪章、精简高频加载面、治理 skill、周期 review prompt，以及把这些内容落到其他 agent 栈里的实施说明。

英文主入口见：[README.md](README.md)

## 这个仓库解决什么问题

很多 agent 系统不是不会执行，而是缺少：
- 稳定的客户价值定义
- 预算意识
- 可信的完成标准
- 周期性复盘
- 可复利的资产沉淀

这个仓库就是把这些治理层内容，打包成另一个 agent 可以真正拿去落地的形式。

## 打包结构

这次结构采用更清晰的 **完整宪章 / 高频加载面分层**：

- `docs/operating-doctrine.md` — 完整宪章 / 正典文档
- `AGENTS.md` — 给另一个 agent 的薄入口 / 读取路由
- `SOUL.md` — 运行时高频加载的压缩版原则
- `skills/` — 可复用治理关卡
- `templates/cron/` — weekly / monthly 周期治理 prompt
- `templates/review/` — 任务收尾模板
- `docs/implementation-guide.md` — 如何落到其他宿主栈
- `docs/integrations/hermes.md` — Hermes 具体映射

核心原则就是：

> 高频加载层保持精简；完整宪章单独做成正典文档。

## 快速开始

最快的使用方式，是把这个仓库直接交给你的 agent，并要求它先落最小可行层。

推荐提示词：

> 先读 `README.md`，再读 `AGENTS.md`、`SOUL.md`、`docs/implementation-guide.md`。把 `docs/operating-doctrine.md` 当作完整宪章参考。不要替换一个已经成熟的执行栈，而是把这套 kit 映射到当前环境里：哪些进 runtime layer，哪些做成 governance skills，哪些做成 recurring review，哪些不该放进 memory。先从最小可行 adoption layer 开始，并明确汇报你建议修改的文件、skill 和 cron。

如果你的框架已经有不错的 planning、coding、research、debugging、verification 能力，就**不要替换它们**。这个仓库的作用是给执行层加治理，不是重写执行层。

## 其他 agent 应该怎么落地

### 第一步：按顺序读

1. `README.md` — 先理解这个包的定位和落地路径
2. `AGENTS.md` — 再理解加载路由和何时读深层文档
3. `SOUL.md` — 读取高频原则压缩版
4. `docs/operating-doctrine.md` — 需要完整宪章时再读
5. `docs/implementation-guide.md` — 把内容映射到宿主栈
6. `docs/integrations/hermes.md` — 如果目标栈是 Hermes

### 第二步：先装最小有用层

不要一次性塞满，按层级渐进：

- **Level 0 — doctrine**：先统一模型和术语
- **Level 1 — runtime layer**：先落 `SOUL.md` 里的压缩原则
- **Level 2 — governance skills**：接入 `skills/` 下的三个治理关卡
- **Level 3 — recurring review**：把 `templates/cron/` 接到调度器里
- **Level 4 — framework mapping**：把 runtime / skills / cron / memory / task state 正确归位
- **Level 5 — portable mode**：形成可迁移的 operating mode

### 第三步：保持分层干净

- **完整宪章** 放文档，不放 memory
- **runtime prompt** 只留高频、压缩、稳定原则
- **可复用判断流程** 放 skill
- **周期治理动作** 放 cron / scheduler
- **memory** 只放稳定事实
- **task state** 只记录当前执行

## 什么放哪里

- **`docs/operating-doctrine.md`**：完整宪章、原理、KPI、治理逻辑
- **`AGENTS.md`**：告诉另一个 agent 先读什么、什么时候升级去读深层文档
- **`SOUL.md`**：适合高频加载的压缩版治理原则
- **`skills/`**：开工、收尾、资产化三类治理关卡
- **`templates/cron/`**：weekly / monthly 周期 review
- **`templates/review/`**：交付收尾格式
- **memory**：稳定的客户 / 环境 / 偏好事实
- **task state**：当前任务、阻塞点、下一步、验证目标
- **assets**：skills、SOP、docs、scripts、templates、周期复盘

## 可直接使用的资产

### 运行时加载面
- [`AGENTS.md`](AGENTS.md)
- [`SOUL.md`](SOUL.md)
- [`docs/operating-doctrine.md`](docs/operating-doctrine.md)

### 治理 skills
- [`skills/operating-gates/SKILL.md`](skills/operating-gates/SKILL.md)
- [`skills/delivery-review-gates/SKILL.md`](skills/delivery-review-gates/SKILL.md)
- [`skills/assetization-closeout/SKILL.md`](skills/assetization-closeout/SKILL.md)

### 周期 review prompts
- [`templates/cron/weekly-operating-review.md`](templates/cron/weekly-operating-review.md)
- [`templates/cron/monthly-operating-audit.md`](templates/cron/monthly-operating-audit.md)

### 收尾模板
- [`templates/review/task-closeout-template.md`](templates/review/task-closeout-template.md)

## 仓库结构

```text
agent-operating-model-kit/
├── README.md
├── README.zh-CN.md
├── AGENTS.md
├── SOUL.md
├── CONTRIBUTING.md
├── docs/
│   ├── operating-doctrine.md
│   ├── implementation-guide.md
│   ├── social-preview.md
│   └── integrations/
│       └── hermes.md
├── skills/
│   ├── operating-gates/
│   │   └── SKILL.md
│   ├── delivery-review-gates/
│   │   └── SKILL.md
│   └── assetization-closeout/
│       └── SKILL.md
├── templates/
│   ├── cron/
│   │   ├── weekly-operating-review.md
│   │   └── monthly-operating-audit.md
│   └── review/
│       └── task-closeout-template.md
└── assets/
    └── social-preview-final.jpg
```

## 方法论哲学

这套包有意保持克制：
- 复用宿主框架已有执行能力
- 先有宪章，再上机制
- 先有治理关卡，再加角色分化
- 先有周期复盘，再加更多自动化
- 高频加载文件保持短小
- 只有在明确能复利时才沉淀资产

## 完整宪章

完整 doctrine 见：
- [docs/operating-doctrine.md](docs/operating-doctrine.md)

## 框架集成

核心宪章保持框架无关。

当前参考适配：
- Hermes：[`docs/integrations/hermes.md`](docs/integrations/hermes.md)

## 贡献方式

见：[CONTRIBUTING.md](CONTRIBUTING.md)

## 许可证

MIT
