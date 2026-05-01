# Agent Operating Model Kit

一套可复用的方法论工具包，用来把 agent 系统运行成一个**围绕单一核心客户长期运转的微型 AI 组织**。

这个仓库不是新的执行引擎，而是一套**治理层打包物**：包含正典宪章、可复用治理 skills、可选的运行时参考接入面，以及可选的周期治理 prompts，可叠加到已经能工作的执行栈之上。

英文主入口见：[README.md](README.md)

## 这个仓库解决什么问题

很多 agent 系统不是不会执行，而是缺少：
- 稳定的客户价值定义
- 预算意识
- 可信的完成标准
- 周期性复盘
- 可复利的资产沉淀

这个仓库把这些治理层内容打包成一种既能给人评估、也能给 agent 落地的形式。

## 应该怎么理解这个仓库

这个仓库里有几类**不同角色的产物**。它们会协作，但不是同一个概念。

### 1. 核心 skill / doctrine 产物
这些文件承载真正的方法论和可复用治理逻辑。

- [`docs/operating-doctrine.md`](docs/operating-doctrine.md) — 正典宪章 / 完整 doctrine
- [`skills/`](skills/) — 可复用治理 skills
- [`templates/review/task-closeout-template.md`](templates/review/task-closeout-template.md) — 可复用收尾模板

### 2. 接入面 / integration surfaces
这些文件帮助另一个 agent 或宿主框架把这套包映射进自己的运行环境。

- [`AGENTS.md`](AGENTS.md) — 薄入口 / 读取路由
- [`SOUL.md`](SOUL.md) — 适合高频加载的压缩运行时原则
- [`MEMORY.md`](MEMORY.md) — 长期记忆边界说明
- [`docs/implementation-guide.md`](docs/implementation-guide.md) — 如何映射到宿主栈
- [`docs/integrations/hermes.md`](docs/integrations/hermes.md) — Hermes 参考接入方式

### 3. 操作化面 / operational surfaces
这些是可选的周期治理操作面，不是所有 skill 仓库都必须有。

- [`templates/cron/`](templates/cron/) — 周期 operating review prompts

### 4. 部署说明
这些文件解释可复用部件应该如何安装、接入或改写。

- [`skills/README.md`](skills/README.md) — skill 部署说明
- [`templates/cron/README.md`](templates/cron/README.md) — 定时 / 调度工作流部署说明

## 打包原则

核心打包原则很简单：

> 正典 doctrine 要明确独立；运行时 guidance 要压缩；部署说明和运维面不要和 skill 本体混为一谈。

## 可直接使用的资产

### 正典文档与映射说明
- [`docs/operating-doctrine.md`](docs/operating-doctrine.md)
- [`docs/implementation-guide.md`](docs/implementation-guide.md)
- [`MEMORY.md`](MEMORY.md)

### 运行时 / 宿主接入参考
- [`AGENTS.md`](AGENTS.md)
- [`SOUL.md`](SOUL.md)
- [`docs/integrations/hermes.md`](docs/integrations/hermes.md)

### 治理 skills
- [`skills/operating-gates/SKILL.md`](skills/operating-gates/SKILL.md)
- [`skills/delivery-review-gates/SKILL.md`](skills/delivery-review-gates/SKILL.md)
- [`skills/assetization-closeout/SKILL.md`](skills/assetization-closeout/SKILL.md)
- [`skills/README.md`](skills/README.md)

### 可选的周期治理 prompts
- [`templates/cron/weekly-operating-review.md`](templates/cron/weekly-operating-review.md)
- [`templates/cron/monthly-operating-audit.md`](templates/cron/monthly-operating-audit.md)
- [`templates/cron/README.md`](templates/cron/README.md)

### 收尾模板
- [`templates/review/task-closeout-template.md`](templates/review/task-closeout-template.md)

## 仓库结构

```text
agent-operating-model-kit/
├── README.md
├── README.zh-CN.md
├── AGENTS.md
├── SOUL.md
├── MEMORY.md
├── CONTRIBUTING.md
├── docs/
│   ├── operating-doctrine.md
│   ├── implementation-guide.md
│   ├── social-preview.md
│   └── integrations/
│       └── hermes.md
├── skills/
│   ├── README.md
│   ├── operating-gates/
│   │   └── SKILL.md
│   ├── delivery-review-gates/
│   │   └── SKILL.md
│   └── assetization-closeout/
│       └── SKILL.md
├── templates/
│   ├── cron/
│   │   ├── README.md
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

## For Agents

如果你是负责接入这个仓库的 agent，请把它当成**映射参考包**，而不是盲目覆盖包。

### 建议阅读顺序
1. [`README.md`](README.md)
2. [`AGENTS.md`](AGENTS.md)
3. [`docs/implementation-guide.md`](docs/implementation-guide.md)
4. [`docs/operating-doctrine.md`](docs/operating-doctrine.md)
5. 视需要再读：
   - [`SOUL.md`](SOUL.md)
   - [`MEMORY.md`](MEMORY.md)
   - [`skills/README.md`](skills/README.md)
   - [`templates/cron/README.md`](templates/cron/README.md)
   - [`docs/integrations/hermes.md`](docs/integrations/hermes.md)

### 最小落地任务
判断这套包在宿主环境里分别应该落成什么：
- canonical doctrine
- reusable skills
- runtime guidance
- durable memory boundaries
- scheduled / recurring governance

不要假设仓库里的每个面都必须安装。有些是**核心产物**，有些是**接入参考**，有些只是**可选操作化面**。

如果宿主框架已经有强的 planning、coding、research、debugging、verification 或 scheduling 工作流，应复用它们，只补足真正有价值的治理部件。

## 框架集成

核心 doctrine 保持框架无关。

当前参考接入：
- Hermes：[`docs/integrations/hermes.md`](docs/integrations/hermes.md)

## 贡献方式

见：[CONTRIBUTING.md](CONTRIBUTING.md)

## 许可证

MIT
