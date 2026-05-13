# AI PM Assessor

> An expert-style Codex Skill for diagnosing AI-era Product Manager capability.

AI PM Assessor 是一个面向 **AI 时代互联网产品经理** 的能力评估 Skill。它不是题库，而是模拟一位 AI 大厂产品专家与人才发展专家，通过结构化问诊、场景推演、压力追问和证据化报告，帮助产品从业者看清自己的能力画像、长板短板、胜任风险和下一步成长路径。

这个 Skill 适合用于 AI PM 转型、自我诊断、面试准备、晋升复盘、团队人才盘点，以及产品负责人对候选人的结构化能力观察。

## Why

AI 产品经理的能力评估很容易滑向两种误区：

- 只考概念：问“什么是 RAG”“什么是 Agent”，却看不出真实产品判断。
- 只做选择题：用户选了一个看似正确的选项，但不知道背后的推导是否可靠。

真正的 AI PM 能力，体现在混乱场景下的判断：如何定义问题，如何拆用户场景，如何理解模型边界，如何设计体验和评测，如何平衡成本、延迟、合规、商业化与组织协同。

AI PM Assessor 的目标就是把这些判断“问出来”，并形成一份可复查、可行动的能力诊断报告。

## What It Does

AI PM Assessor 会按用户背景动态调整评估过程：

- 逐步采集背景，而不是一次性抛出一串问题
- 支持两种交互模式：选择题模式 / 探讨模式
- 基于行业、年限、目标岗位和 AI 产品经验生成场景
- 对用户回答进行专家追问、变量扰动和失败复盘
- 按“三层八维”框架记录能力证据
- 识别重复短板和 Derailer 风险
- 输出带证据链的最终能力画像和 30 天提升计划

## Interaction Modes

### A. Multiple-choice Mode

适合想要节奏更轻、压力更低的用户。Skill 会给出 A/B/C/D 场景选项，但不会只看选项字母。

如果用户只回复选项，Skill 会继续追问：

```text
你为什么这么选？请用 1-2 句话说明你的判断依据。
```

这样可以避免评估变成猜题。

### B. Discussion Mode

适合希望体验更像专家面试或能力问诊的用户。Skill 会给出开放式业务场景，并要求用户说明：

1. 真正要解决的问题是什么
2. 优先做哪个决策，为什么
3. 用什么指标、评测或风险兜底验证

讨论过程中，Skill 会像专业面试官一样追问判断依据、加入变量扰动，并要求用户做失败复盘。

## Assessment Framework

Skill 使用“三层八维”能力框架：

| 能力簇 | 维度 | 观察重点 |
|---|---|---|
| 战略脑 | A. 问题定义与机会判断 | 能否从现象回到用户任务、业务约束和真实机会 |
| 洞察眼 | B. 用户洞察与场景拆解 | 能否识别目标用户、动机、频次、替代方案和关键阻力 |
| 工程骨 | C. AI 能力理解与产品化 | 能否理解模型边界、上下文、工具调用、幻觉、延迟、成本和评测 |
| 洞察眼 | D. AI 原生体验与工作流设计 | 能否设计可信、可控、容错的人机协作体验 |
| 工程骨 | E. 数据指标与实验决策 | 能否设计指标、实验、评测集、样本偏差和因果判断 |
| 战略脑 | F. 商业化与增长策略 | 能否连接用户价值、获客、定价、留存和单位经济模型 |
| 战略脑 | G. 优先级与资源取舍 | 能否在资源、技术风险和商业收益之间做清晰取舍 |
| 安全盾 | H. 组织协同、伦理与风险 | 能否处理隐私、版权、合规、偏见、品牌和责任边界 |

## Expert Probing Logic

AI PM Assessor 的核心不是“出题”，而是“追问”。

每个关键场景都可能触发三层追问：

1. **决策依据追问**  
   你为什么把这个约束排在第一位？什么证据会让你改变判断？

2. **变量扰动追问**  
   如果 API 成本上涨 3 倍，竞品上线低价方案，或合规阻断上线，你会如何修正？

3. **失败复盘追问**  
   如果上线后留存没有变化，或者负面指标恶化，你如何回溯真因？

这种问诊方式能更好地区分“会背框架的人”和“能在真实项目里做判断的人”。

## Output Report

评估结束后，Skill 会输出结构化报告，包括：

- 专家委员会结论：Strong Hire / Hire / Lean Hire / No Go for Current Target
- 能力画像：例如 AI 系统产品派、商业策略派、体验创新派、交付协同派
- 八个维度的评分、判断、证据和置信度
- Top 3 优势
- Top 3 短板
- 关键 Derailer 风险
- AI 时代 PM 的真实工作风险
- 目标岗位胜任度判断
- 已观察证据与待验证假设
- 30 天提升计划
- 高杠杆练习和下一步验证建议

报告不是权威认证，而是一份基于本轮问诊证据的专家诊断。

## Installation

将本仓库复制到你的 Codex skills 目录：

```bash
mkdir -p .codex/skills
git clone https://github.com/sangxgg/ai-pm-assessor.git .codex/skills/ai-pm-assessor
```

或者复制到你的全局 Codex skills 目录，路径取决于你的本地配置。

安装后，在 Codex 中使用：

```text
Use $ai-pm-assessor to run an AI PM capability diagnosis.
```

## Repository Structure

```text
ai-pm-assessor/
├── SKILL.md
├── agents/
│   └── openai.yaml
└── references/
    ├── adaptive-questioning.md
    ├── assessment-framework.md
    └── report-template.md
```

## Design Principles

- **No fixed question bank**：每次评估都根据用户背景动态生成。
- **Evidence over vibes**：所有结论必须能回到用户回答和追问证据。
- **Conversation over test**：默认是专家问诊，不是标准化考试。
- **Pressure reveals judgment**：通过变量扰动和失败复盘观察稳定判断。
- **Actionable growth**：报告必须给出具体短板和可执行提升路径。

## Notes for Claude Code Users

Claude Code 会展示 `Write` / `Edit` 文件操作和 diff。因此，本 Skill 默认不会在评估过程中创建或持续更新 `assessment-state.md` 这类过程文件。

评估状态会在对话上下文中维护。只有当用户明确要求“保存记录”或“导出过程”时，才建议在评估结束后一次性生成文件。

## Disclaimer

AI PM Assessor 不是招聘认证，也不能替代真实项目复盘、作品集审查、深度面试或绩效数据。它的价值在于提供一套结构化、可复查、可行动的能力诊断方式。

## License

No license has been specified yet.
