# 更新日志

所有重要的项目变更都将记录在此文件中。

格式基于 [Keep a Changelog](https://keepachangelog.com/zh-CN/1.0.0/)，
版本号遵循 [语义化版本](https://semver.org/lang/zh-CN/)。

---

## [Unreleased]

### 待添加
- 

### 计划中
- 支持更多 IM 渠道（飞书、WhatsApp）
- 关系图谱可视化
- 情绪趋势分析图表
- 智能推荐系统

---

## [1.1.0] - 2026-03-06

### 新增 ✨
- **心理学分析功能**: 基于用词、互动模式的心理学分析
- **用词分析核心**: 情绪词/肯定词/否定词/疑问词/"我"vs"我们"分析
- **成员范围筛选**: 可配置只监测部分成员 (`watchMembers`)
- **心理报告模板**: 周度/月度心理分析报告
- **预警系统**: 用词异常、不平衡互动预警

### 改进 🔧
- **弱化频率分析**: 发言频率和响应速度降为辅助参考 (各 15%)
- **强化用词分析**: 用词分析作为核心维度 (40% 权重)
- **互动模式优化**: 互动对象分析作为核心维度 (30% 权重)
- 人物档案增加用词特征分析
- 备忘录增加心理分析摘要
- 配置文件增加 `psychologicalAnalysis.weights` 配置项

### 文档 📝
- 新增心理学分析指南 (docs/PSYCHOLOGY.md)
- 新增用词分析词库和指标说明
- 更新 README.md 配置说明
- 更新 SKILL.md 功能说明

---

## [1.0.0] - 2026-03-06

### 新增 ✨
- 群聊信息自动提取（事件、心情、地点、人物、待办）
- 人物档案自动构建
- 每日聊天摘要
- 智能查询命令
- 隐私保护（自动脱敏）
- 定时任务（每日摘要、事件提醒）

### 配置 ⚙️
- 支持多群配置
- 可配置提取详细度
- 可配置隐私脱敏规则
- 可配置数据保留期限

### 文档 📝
- 完整的 README.md
- 详细的使用指南 (docs/GUIDE.md)
- 贡献指南 (CONTRIBUTING.md)
- GitHub Issue/PR 模板

### 技术 🛠️
- MIT 许可证
- GitHub Actions CI/CD
- 符合 OpenClaw Skill 规范

---

## 版本说明

### 1.0.0
首个公开版本，包含核心功能：
- 信息提取
- 人物档案
- 备忘录
- 智能查询
- 隐私保护

---

[Unreleased]: https://github.com/YOUR_USERNAME/chat-memory-keeper/compare/v1.0.0...HEAD
[1.0.0]: https://github.com/YOUR_USERNAME/chat-memory-keeper/releases/tag/v1.0.0
