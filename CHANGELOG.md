# Changelog · 更新日志

All notable changes to this skill will be documented in this file.

## [1.2.0] — 2026-07-25

### Added · 新增
- **多 Agent 对抗流水线 v3**：日报生成从单 Agent 升级为 5 阶段流水线（Searcher×4 → Dedup → Scorer → Adversarial → Editor）
- **Adversarial Agent（对抗审查）**：独立质量闸门，默认立场质疑一切，对标 WaltzRL/MPDF 设计理念
- **评分四维加权框架**：技术相关性 40% + 产业信号强度 25% + 可行动性 20% + 解读门槛 15%
- **去重优化规则**：story reversal（"延期→发布"）应标✅保留而非🔄跟进
- ⭐4-5 AI 技术突破强制配教学式技术解析模块（从零讲起+类比+ASCII图+对比表+一句话记住）

### Fixed · 质量改善（回溯审计验证）
- ⭐5 虚高率 69.2% → 17.6%（↓51.6pp）
- 去重失败率 0.75次/天 → 0（↓100%）
- ⚠️直觉陷阱覆盖率 8.3% → 100%（↑91.7pp）
- 低价值条目占比 ~13% → 0%（↓13pp）

### Token 参考
- 日报单次 ~250-300K tokens，~$0.45-0.90，~15-20 分钟

## [1.1.0] — 2026-07-11

### Added · 新增
- **Agent-Reach 中文平台情报源**：B站/小红书/微博/YouTube 并行搜索通道，抓取中文社交平台一手 AI/产业资讯
- 来源分级升级为四级：🟣中文平台一手资讯 > 🟢官方 > 🔵权威媒体 > ⚪券商智库
- HTML 样式新增中文平台来源标注格式

### Changed · 变更
- 搜索流程重构为两阶段并行（中文平台情报 + 英文搜索）
- 报告视角脱敏："聪明学生的信息望远镜" → "独立分析视角"
- 日报"对你意味着什么"章节 → "影响分析"

## [1.0.0] — 2026-07-11

### Added · 新增
- Initial release · 首次发布
- Three report types: 周报 (weekly), 日报 (daily), 前瞻 (preview) · 三种报告类型
- Parallel 8-channel search pipeline (2 rounds) · 两轮并行 8 路搜索流程
- Expert analysis with 4-element framework (why now → history → dissent → evolution) · 四要素专家拆解框架
- Source tier system: 🟢官方 / 🔵权威媒体 / ⚪券商智库 · 三级来源分级
- Rich HTML output with gradient covers, tagged tables, insight cards · 渐变封面 + 标签表格 + 拆解卡片
- Bilingual README with installation guides · 中英文 README 及安装指南
- MIT License · MIT 许可

[1.0.0]: https://github.com/oyj123321/claude-code-policy-tracker/releases/tag/v1.0.0
