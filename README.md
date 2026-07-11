# Claude Code Policy Tracker · 全球产业政策追踪

<p align="center">
  <strong>🇨🇳 中文</strong> &nbsp;|&nbsp;
  <strong>🇬🇧 English</strong>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Claude%20Code-skill-6C4DFF?style=flat-square&logo=claude" alt="Claude Code Skill">
  <img src="https://img.shields.io/badge/license-MIT-green?style=flat-square" alt="MIT License">
  <img src="https://img.shields.io/badge/version-1.0.0-blue?style=flat-square" alt="Version 1.0.0">
</p>

---

An AI-powered global industrial policy tracking skill for Claude Code. Generates daily, weekly, and preview reports covering China/US/EU/Japan/Korea policies across semiconductors, AI, new energy, and supply chains — output as rich, visual HTML with expert-grade analysis.

一个 AI 驱动的全球产业政策追踪 Claude Code 技能。生成日报/周报/前瞻，覆盖中美欧日韩政策、半导体/AI/新能源/产业链，输出带深度专家拆解的可视化 HTML。

---

## Table of Contents · 目录

- [Report Types · 报告类型](#report-types--报告类型)
- [Why This Exists · 为什么需要它](#why-this-exists--为什么需要它)
- [Installation · 安装](#installation--安装)
- [Usage · 使用](#usage--使用)
- [Repository Structure · 仓库结构](#repository-structure--仓库结构)
- [Contributing · 贡献](#contributing--贡献)
- [License · 许可](#license--许可)

---

## Report Types · 报告类型

| 类型 | 触发词 | 频率 | 说明 |
|------|--------|------|------|
| **周报** | 周报 / 政策周报 / weekly | 每周一 | 完整政策追踪：中国 5 大产业 + 国际 5 大领域 + 深度拆解 + 下周关注 |
| **日报** | 日报 / daily | 每日 | 当日宏观日报：重大事件 + 资产价格 + 科技突破扫描 + 专家拆解 |
| **前瞻** | 前瞻 / preview / 下周 | 每周日 | 下周前瞻：事件日历 + 核心数据预期 + 决策矩阵 |

### Weekly Report · 周报

- **🇨🇳 中国产业政策**（5 个子表）：新能源/电动车、半导体/科技、房地产/基建/城市更新、消费/以旧换新、农业/粮食
- **🌍 国际产业政策**（5 个子表）：美国 CHIPS/IRA/半导体、欧盟 CBAM/绿色工业、芯片出口管制/实体清单、全球电动车关税、日韩/东南亚科技投资
- **🧠 专家拆解**：3-4 条深度分析，每条含：为什么现在出 + 联动分析 + 历史参照 + 反对观点 + 量化预测 + 后续演化
- **🔮 下周关注**：6-9 个事件卡片
- **🎯 产业方向**：2-3 个战略方向卡片
- **📚 来源分级**：🟢官方 / 🔵权威媒体 / ⚪券商智库

### Daily Report · 日报

- **🇨🇳 中国线**：当日重大政策/事件
- **🌍 国际线**：Fed/ECB/BOJ 动态、贸易谈判、地缘事件
- **💰 关键资产价格**：资产 + 涨跌幅 + 驱动因素
- **🔬 科技突破扫描**：当日重大科学/技术突破
- **🧠 专家拆解**：2-4 课，对话式解释"为什么"+"意味着什么"
- **🎯 对你意味着什么**：短期/中期影响 + 信号追踪表
- **📌 今日一句话**

### Preview · 前瞻

- **📅 下周核心事件日历**：日期 + 时间 + 事件 + 前值 + 预期 + 重要性 + 情景分析
- **🧠 焦点深度拆解**：1-2 个最重要事件的市场推演
- **🎯 决策矩阵**：四种宏观情景 → 风险资产/避险资产/美元方向

---

## Why This Exists · 为什么需要它

**The problem:** Tracking global industrial policy is a high-effort, daily-grind task. A single report requires:

| Step | Time (manual) |
|------|---------------|
| Searching 8+ channels across CN/US/EU/JP/KR | 45–90 min |
| Reading and filtering relevant policies | 30–60 min |
| Writing expert-level analysis with historical context | 60–120 min |
| Formatting into a readable, visual report | 30–60 min |
| **Total per daily report** | **~3–5 hours** |
| **Total per weekly report** | **~6–10 hours** |

**The fix:** This skill automates the entire pipeline — multi-channel search, relevance filtering, expert analysis with dissenting viewpoints, and rich HTML output. A report that took half a day now takes one Claude Code invocation.

**核心痛点：** 全球产业政策追踪是高频、高信息密度的重复性工作。一个人手动做需要 3-10 小时/份。这个 skill 把搜索→过滤→分析→排版全流程自动化，将半天的工作压缩到一次 Claude Code 调用。

---

## Installation · 安装

### Method 1: Git Clone (Recommended)

```bash
# Clone the repository
git clone https://github.com/oyj123321/claude-code-policy-tracker.git

# Link into Claude Code skills — project-level (current project only)
mkdir -p .claude/skills
# Linux / macOS
ln -s $(pwd)/claude-code-policy-tracker .claude/skills/policy-tracker
# Windows (PowerShell, as Administrator)
New-Item -ItemType SymbolicLink -Path .claude/skills/policy-tracker -Target (Resolve-Path claude-code-policy-tracker)

# Or: user-level (all projects)
# Linux / macOS
ln -s $(pwd)/claude-code-policy-tracker ~/.claude/skills/policy-tracker
```

### Method 2: OpenSkills

```bash
npx openskills install oyj123321/claude-code-policy-tracker
```

### Method 3: Manual Copy

```bash
cp -r claude-code-policy-tracker .claude/skills/policy-tracker
```

---

## Usage · 使用

**All three report types are invoked via the same skill:**

```
/policy-tracker 日报
/policy-tracker 周报
/policy-tracker 前瞻
```

Or use natural language triggers:
- "生成今天的日报"
- "生成本周政策周报"
- "生成下周前瞻"

The skill will:
1. Execute parallel multi-channel web searches (4+4 rounds)
2. Filter and prioritize by relevance and source authority
3. Write expert analysis with historical context and dissenting viewpoints
4. Output a rich, self-contained HTML file to `D:\news\`

### Search Pipeline · 搜索流程

**Round 1 (parallel 4-way):**
1. 中国产业政策最新动态（新能源/电动车/半导体/房地产/消费/农业）
2. US CHIPS Act / IRA / semiconductor export controls latest
3. EU CBAM / green industrial policy / critical raw materials latest
4. 全球电动车关税 + 芯片管制实体清单 + 日韩东南亚半导体投资

**Round 2 (on-demand 3-4-way):**
5. 中国专项债发行进度 + 以旧换新补贴具体金额
6. EU-China EV tariff / anti-subsidy / price undertaking latest
7. 台积电/三星/SK 海力士海外工厂进展
8. 下周全球经济数据日历（前瞻专用）

---

## Repository Structure · 仓库结构

```
claude-code-policy-tracker/
├── SKILL.md          # Core skill file · 核心技能文件 (Claude Code entry point)
├── README.md         # This document · 本文档 (bilingual human-readable docs)
├── CHANGELOG.md      # Version history · 版本历史
├── LICENSE           # MIT License · MIT 许可
└── .gitignore        # Git ignore rules
```

---

## Design Principles · 设计理念

1. **聪明学生的信息望远镜** — 不是基金经理视角，不是纯新闻聚合；解释"这意味着什么"+"它跟另一件事有什么关系"+"我比别人早多久知道"
2. **每条拆解四个要素**：为什么现在出 → 历史参照 → 反对观点 → 后续演化
3. **来源分级透明**：🟢 官方一手公告 > 🔵 权威媒体 > ⚪ 券商智库
4. **金额精确**：绝不写"—"，必须填具体数字或解释为什么无法公开获取
5. **自包含 HTML**：不依赖 markdown 渲染，直接输出样式完备的 HTML 文件

---

## Contributing · 贡献

This skill is opinionated but extensible. If you have ideas for improvement:

1. Open an issue to discuss before submitting a PR
2. Keep the SKILL.md under 300 lines (Claude Code has description budget limits)
3. Maintain full bilingual parity — every Chinese sentence needs an English equivalent, and vice versa
4. If adding a new report type, update the search pipeline and writing principles sections

Contributions are welcome under the MIT license.

---

## License · 许可

MIT — see [LICENSE](./LICENSE) for full text.

随意使用、修改、分发。Use freely, modify, distribute.
