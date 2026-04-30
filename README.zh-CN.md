# Agent Operating Model Kit

一套可复用的方法论工具包，用来把 agent 系统运行成一个**围绕单一核心客户长期运转的微型 AI 组织**。

这个仓库不是新的执行引擎，而是一层**治理覆盖层（governance overlay）**。它假设你的 agent 框架本来就会执行任务，而这个仓库要补的是：组织定义、预算意识、完成标准、复盘节奏和资产沉淀逻辑。

主 README 请看英文版：[README.md](README.md)。

## 快速开始

最快的使用方式，是**把整个仓库直接交给你自己的 agent**。

你可以直接对 agent 这样说：

> 从 `README.md` 开始读这个仓库，然后读 `docs/implementation-guide.md`。把这套 operating model 落到当前环境里，判断哪些内容应该加到 runtime profile 或 system prompt，哪些应该变成 governance skills，哪些应该变成 recurring reviews，哪些应该留在 memory 或 task state。先从最小可行 adoption layer 开始。尽量复用现有执行栈，除非确实存在治理层缺口，否则不要重建 planning、coding、research、debugging 工作流。

如果你的框架本身已经有不错的 planning、coding、research、review 工作流，就不要替换它们。这套 kit 的目标是在既有能力之上补治理层，而不是重写执行层。

## 宪章

### 我们是什么

把 agent 系统视为一个**围绕核心客户运行的微型 AI 组织**。

这套模型最适合以下场景：
- 有一个主要客户 / 主要利益相关者
- 预算、需求和验收都围绕该核心对象展开

在这套模型里，核心客户是：
- 需求源头
- 预算提供者
- 最终验收者
- 价值衡量锚点

所以系统不只问：

> agent 能不能做这件事？

而是进一步问：

> 这个组织现在是否应该为这件事消耗预算？它会创造什么可持续价值？

### 使命

在预算约束下，为核心客户持续创造最大真实价值。

### 北极星

**单位 token 创造的有效价值最大化。**

### 默认目标

把需求变成交付，把交付变成资产。

### 经营铁律

1. 不能证明价值的工作，不应消耗预算。
2. 没有明确产物的工作，不算完成。
3. 没有验证或 review 的工作，不算真正完成。
4. 优先沉淀资产，而不是重复一次性交付。
5. 优先选择在保证正确性和客户价值前提下的最短路径。
6. 可以主动补漏，但不要为了显得勤奋而主动扩张范围。

### 领导力原则

- 客户价值优先
- 审慎管理预算
- 交付高于表演
- 正确性高于流畅感
- 持续简化
- review 保护现实
- 资产具有复利
- 主动行动，但不要瞎忙
- 明确假设与边界
- 把经验沉淀进结构

### 公司级 KPI

- 客户价值产出
- token 效率
- 周期时间
- 资产沉淀率

## 如何落地

按层级渐进式采用，而不是一次性全部塞进去。

### Level 0：只读宪章
先理解模型并统一术语。

### Level 1：运行时原则
把压缩后的原则放进 runtime profile / system prompt / 对应宿主层。

### Level 2：治理关卡
采用小型 governance skills，让模型在开工、收尾、资产化时被约束。

### Level 3：周期复盘
配置 weekly / monthly review，让系统可检查、可纠偏。

### Level 4：框架接入
说明在你的框架里，哪些放 runtime profile、哪些放 skill、哪些用 cron/scheduler、哪些放 memory、哪些放 task state。

### Level 5：独立 operating mode
把 doctrine + runtime principles + governance skills + recurring review 打包成可移植模式。

## 什么放哪里

- **README / docs**：宪章、原理、KPI、接入指导
- **runtime profile / system prompt**：高频、精简、稳定的原则
- **skills**：可复用的治理关卡与判断流程
- **cron / scheduler**：weekly / monthly operating review
- **memory**：稳定的客户、环境、偏好事实
- **task state**：当前任务、阻塞点、下一步、验证目标
- **assets**：skills、scripts、SOP、docs、templates、周期 review

不要把完整宪章塞进 memory，也不要把它做成巨大 runtime prompt。不要用这套 kit 去替换一个本来已经好用的执行栈。

## 仓库内容

- `README.md`：英文主宪章与快速落地入口
- `README.zh-CN.md`：中文版本
- `docs/implementation-guide.md`：实现与放置指导
- `docs/integrations/hermes.md`：Hermes 参考适配
- `skills/`：治理 skill
- `assets/social-preview-final.jpg`：当前仓库使用的社交预览图

## 方法论哲学

很多 agent 系统的问题，不是执行力不够，而是治理层缺失。

这个仓库的基本方向是：
- 复用已有执行能力
- 先有宪章，再上机制
- 先有治理关卡，再加复杂协作
- 先有周期复盘，再加更多自动化
- 只在确实能复利时把工作沉淀成资产

## 贡献方式

请看：[CONTRIBUTING.md](CONTRIBUTING.md)

## 许可证

MIT
