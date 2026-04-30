# Agent Operating Model Kit

一套可复用的方法论工具包，用来把 agent 系统运行成一个**围绕单一核心客户长期运转的微型 AI 组织**。

这个仓库不是新的执行引擎，而是一层**治理覆盖层（governance overlay）**。它假设你的 agent 框架本来就会执行任务，而这个仓库要补的是：组织定义、预算意识、完成标准、复盘节奏和资产沉淀逻辑。

主 README 请看英文版：[README.md](README.md)。

## 快速开始

使用这个仓库最快的方式，是**把整个仓库直接交给你自己的 agent**。

你可以直接对 agent 这样说：

> 先读 `README.md`，然后读 `docs/operating-doctrine.md`、`docs/layering.md`、`docs/adoption-playbook.md`、`docs/what-goes-where.md`。把这套 operating model 落到当前环境里，判断哪些内容应该放进 soul/profile、skills、cron、memory、docs 和 task state。先从最低可行 maturity level 开始。除非确实存在治理层缺口，否则不要重建现有执行栈。

如果你的框架本身已经有不错的 planning、coding、research、review 工作流，就不要替换它们。这套 kit 的目标是在既有能力之上补治理层，而不是重写执行层。

## 它是怎么工作的

这套 kit 不去替代已有的执行框架，而是在其上增加一层治理逻辑。

它让系统不只问：

> agent 能不能做这件事？

而是进一步问：

> 这个组织现在是否应该为这件事消耗预算？它会创造什么可持续价值？

核心思想包括：

- 用一个核心客户来锚定需求、预算和验收
- 使命是在预算约束下持续创造最大真实价值
- 北极星是：**单位 token 创造的有效价值最大化**
- 把需求变成交付，把交付变成资产
- 不能证明价值的工作，不应消耗预算
- 没有明确产物、没有新鲜验证的工作，不算真正完成

## 如何落地

推荐按层级渐进式采用，而不是一次性全部装上。

### Level 0：只读宪章
先理解模型和术语，不改运行时。

### Level 1：运行时原则
把压缩后的原则放进 runtime profile / system prompt（或你的框架对应层）。

### Level 2：治理关卡
采用小型 governance skills，让模型在开工、收尾、资产化时被约束。

### Level 3：周期复盘
配置 weekly / monthly review，让系统可检查、可纠偏。

### Level 4：框架接入
说明在你的框架里，哪些放 soul、哪些放 skill、哪些用 cron。

### Level 5：独立 operating mode
把 doctrine + runtime principles + governance skills + recurring review 打包成可移植模式。

更完整的采用路径见：[docs/adoption-playbook.md](docs/adoption-playbook.md)

## 仓库里有什么

- `docs/`：长文档，放 doctrine、KPI、layering、adoption
- `skills/`：治理 skill，不替代执行 skill
- `templates/`：可复制的 soul / cron / review 模板
- `examples/`：参考落地示例，不是唯一正确答案

## 方法论哲学

很多 agent 系统的问题，不是执行力不够，而是治理层缺失。

这个仓库的基本方向是：
- 复用已有执行能力
- 先有宪章，再上机制
- 先有治理关卡，再加复杂协作
- 先有周期复盘，再加更多自动化
- 只在确实能复利时把工作沉淀成资产

## 框架适配

仓库核心保持通用化。

具体框架的适配放在：
- `docs/integrations/`
- `examples/`

当前已有参考适配：
- Hermes：`docs/integrations/hermes.md`

## 贡献方式

请看：[CONTRIBUTING.md](CONTRIBUTING.md)

## 许可证

MIT
