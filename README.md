# Product Requirements Review — Cursor Agent Skill

> 一个 Cursor Agent Skill，让 AI 扮演产品经理 + CTO + 设计师，对你的产品想法进行结构化评审，从模糊灵感到完整设计文档。

[English](#english) | [中文](#中文)

---

## 中文

### 这是什么？

一个 [Cursor](https://cursor.com) 的 Agent Skill。当你在 Cursor 中分享一个产品想法时，AI 会自动按照 9 步结构化流程进行专业评审：

```
澄清想法 → 本质分析 → 竞品调研 → 技术评估 → Go/No-Go 决策
                                                    ↓
                                          Go → 品牌理念 → 系统架构 → 设计风格 → 完整设计文档
                                        No-Go → 输出详尽评审报告
```

### 它会做什么？

| 步骤 | 角色 | 做什么 |
|:---:|:---:|---|
| 1 | 产品经理 | 提出关键问题，帮你厘清模糊想法 |
| 2 | 产品经理 | 定义问题本质、发散核心场景、推理目标人群、三层检验需求真伪 |
| 3 | 分析师 | **实际搜索** data.ai / SensorTower / App Store 评论等，输出竞品对比表 |
| 4 | CTO | **实际搜索** GitHub 开源方案，评估技术难题与 Vibecode 实现成本 |
| 5 | 综合 | 做出 Go / No-Go 决策 |
| 6 | 品牌 + 产品 | 核心理念、命名、产品架构、用户流程 |
| 7 | CTO | 面向 Vibecode 的系统架构（技术选型 / 模块拆分 / 数据模型 / API） |
| 8 | 设计师 | **实际搜索** Dribbble / Behance，输出配色、字体、组件风格建议 |
| 9 | 综合 | 汇总为一份完整设计文档 |

### 亮点

- **不只是分析，而是真的去搜**：Step 3、4、8 会用 WebSearch / WebFetch 实际获取竞品数据、开源项目、设计参考，不是凭空分析。
- **需求真伪三层检验**：问题是否存在？增量价值够不够大？能不能让用户迁移？每层给出 🟢🟡🔴 判断。
- **Vibecode 原生**：技术评估和架构设计专为 AI 辅助编码优化——模块 < 300 行、类型驱动、目录即架构。
- **Go/No-Go 机制**：不盲目推进，Step 5 不通过就输出完整报告并暂停。

### 安装

#### 方式一：个人全局安装（推荐）

```bash
# 克隆到 Cursor 全局 skills 目录
git clone https://github.com/<your-username>/product-requirements-review.git \
  ~/.cursor/skills/product-requirements-review
```

#### 方式二：项目级安装

```bash
# 克隆到项目的 .cursor/skills 目录
git clone https://github.com/<your-username>/product-requirements-review.git \
  .cursor/skills/product-requirements-review
```

安装后，Cursor Agent 会自动识别并在你提出产品想法时应用。你也可以手动 `@` 附加此 Skill。

### 使用方式

在 Cursor 对话中直接说出你的产品想法即可：

```
我想做一个帮年轻人管理碎片化学习笔记的 App
```

AI 会自动进入 Step 1 开始提问，逐步推进整个评审流程。

### 文件结构

```
product-requirements-review/
├── SKILL.md    # Skill 主体（Agent 执行指令）
├── README.md   # 本文件
└── LICENSE     # MIT License
```

### 要求

- [Cursor](https://cursor.com) IDE（支持 Agent Skills 功能）
- Agent 需要有 WebSearch / WebFetch 工具访问权限（用于竞品调研、技术搜索、设计参考搜索）

---

## English

### What is this?

A [Cursor](https://cursor.com) Agent Skill that conducts structured product requirements review. Share a product idea, and the AI acts as PM + CTO + Designer to take it from vague inspiration to a complete design document.

### Workflow

```
Clarify → Essence Analysis → Competitor Research → Tech Assessment → Go/No-Go
                                                                       ↓
                                                   Go → Branding → Architecture → Design → Full Doc
                                                 No-Go → Detailed Review Report
```

### What makes it special?

- **Real research, not just analysis**: Steps 3, 4, 8 use WebSearch/WebFetch to actually gather competitor data, open-source projects, and design references.
- **3-layer demand validation**: Does the problem exist? Is the incremental value big enough? Can it drive user migration? Each layer gets a 🟢🟡🔴 verdict.
- **Vibecode-native**: Tech assessment and architecture design optimized for AI-assisted coding — modules < 300 lines, type-driven, directory-as-architecture.
- **Go/No-Go gate**: Won't blindly proceed. If Step 5 fails, outputs a full report and stops.

### Installation

#### Global (recommended)

```bash
git clone https://github.com/<your-username>/product-requirements-review.git \
  ~/.cursor/skills/product-requirements-review
```

#### Per-project

```bash
git clone https://github.com/<your-username>/product-requirements-review.git \
  .cursor/skills/product-requirements-review
```

### Usage

Just share your product idea in a Cursor conversation:

```
I want to build an app that helps young people manage fragmented learning notes
```

The AI will start with clarifying questions and guide you through the full review process.

### Requirements

- [Cursor](https://cursor.com) IDE with Agent Skills support
- WebSearch / WebFetch tool access for the agent

---

## License

[MIT](LICENSE)
