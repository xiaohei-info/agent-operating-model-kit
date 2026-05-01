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

## 项目特色能力

这个项目的辨识度，不只是文件结构，而是它强调的一组 operating ideas：

- **Token 就是预算** —— 模型调用、工具调用、协作开销、人的注意力都算真实消耗，不是隐形免费资源。
- **没有具体产物就不算完成** —— 看起来很忙、说得很像，不等于真正交付。
- **没有验证就不算 complete** —— 完成声明必须有与任务相匹配的新鲜证据支撑。
- **把 agent system 当成 micro AI organization** —— 围绕一个核心客户运作，而不是停留在通用助手心智。
- **把 deliverable 继续沉淀成 asset** —— 重复工作应转化成 skills、docs、scripts、templates 或 recurring reviews，而不是永远留在对话里。
- **治理执行，而不是替代执行** —— 这套 kit 的目标是增强现有宿主框架，而不是和它抢执行栈。

这些思想才是这个项目真正的产品；仓库结构只是为了把它们可移植地打包出来。

## Quickstart

如果你现在只有这个仓库链接，想先做一个正确的一轮落地：

1. 先读 [`docs/operating-doctrine.md`](docs/operating-doctrine.md) 理解方法论本体。
2. 再读 [`docs/implementation-guide.md`](docs/implementation-guide.md) 看如何映射到宿主环境。
3. 选择落地档位：
   - **Minimum**：doctrine + 压缩运行时 guidance + 手动治理关卡
   - **Standard**：minimum + 可复用 governance skills + memory boundaries
   - **Full**：standard + 周期治理 review
4. 保留宿主原有执行强项。
5. 只安装宿主真正支持的治理面。
6. 按 implementation guide 里的 smoke test 验证是否装对。

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

## 落地档位

### Minimum
适用于宿主扩展能力有限的情况。

安装：
- canonical doctrine
- 如果可能则接入压缩运行时 guidance
- 手动使用三个 governance gates

### Standard
适用于宿主可以加载 reusable skills 或等价 procedural assets 的情况。

安装：
- minimum 全部内容
- reusable governance skills
- 若支持 persistent memory，则加 memory boundaries

### Full
适用于宿主还支持定时 / 周期执行的情况。

安装：
- standard 全部内容
- weekly operating review
- monthly doctrine audit

能力映射算法与 smoke test 见 [`docs/implementation-guide.md`](docs/implementation-guide.md)。

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

## 什么叫“落地成功”

一个好的落地结果，应该让宿主系统变得：
- 在扩大执行前更明确价值
- 在宣称完成前更重视证据
- 在重复工作后更会沉淀资产
- 更有预算意识但不官僚
- 更清楚 doctrine、runtime、memory、skills、recurring review 各自该放什么

如果落地后主要增加了 ceremony，或者重复了宿主原有强工作流，那就装偏了。

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
2. [`docs/operating-doctrine.md`](docs/operating-doctrine.md)
3. [`docs/implementation-guide.md`](docs/implementation-guide.md)
4. 如有帮助再读：
   - [`AGENTS.md`](AGENTS.md)
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

然后选择最小但不失真的 adoption profile。

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
