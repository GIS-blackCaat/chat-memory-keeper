# 💬 Chat Memory Keeper / 群聊记忆管家

**Version**: 2.0.0  
**Author**: 黑猫 🐈‍⬛  
**License**: MIT

[![Version](https://img.shields.io/badge/version-2.0.0-blue.svg)](https://github.com/GIS-blackCaat/chat-memory-keeper)
[![License](https://img.shields.io/badge/license-MIT-green.svg)](LICENSE)
[![OpenClaw](https://img.shields.io/badge/OpenClaw-Skill-orange.svg)](https://openclaw.ai)
[![Platforms](https://img.shields.io/badge/platforms-DingTalk%2FWeChat%2FTelegram-green.svg)](https://github.com/GIS-blackCaat/chat-memory-keeper)

---

## 📋 概述

**群聊记忆管家** - 自动提取群聊中的事件、心情、地点、人物、待办，构建人物档案和备忘录。

**支持平台**：钉钉、企业微信、Telegram

---

## 🎯 核心功能

| 功能 | 说明 |
|------|------|
| **📝 事件提取** | 自动识别群聊中的重要事件 |
| **😊 心情记录** | 提取用户情绪和心情变化 |
| **📍 地点追踪** | 记录用户位置变化 |
| **👥 人物档案** | 构建群成员个人档案 |
| **✅ 待办管理** | 提取并跟踪待办事项 |
| **📊 记忆总结** | 定期生成群聊记忆总结 |

---

## 🚀 快速开始

### 安装

```bash
# 使用 ClawHub 安装
npx clawhub@latest install chat-memory-keeper

# 或手动安装
git clone https://github.com/GIS-blackCaat/chat-memory-keeper.git
cp -r chat-memory-keeper/skills/chat-memory-keeper ~/.openclaw/skills/
```

### 配置

```yaml
# 配置文件
chat_memory:
  enabled: true
  platforms:
    - dingtalk      # 钉钉
    - wecom         # 企业微信
    - telegram      # Telegram
  extract:
    events: true    # 事件提取
    moods: true     # 心情记录
    locations: true # 地点追踪
    people: true    # 人物档案
    tasks: true     # 待办管理
  summary:
    daily: true     # 每日总结
    weekly: true    # 每周总结
```

---

## 📝 功能详解

### 1️⃣ 事件提取

**自动识别**：
- ✅ 会议安排
- ✅ 活动计划
- ✅ 重要决定
- ✅ 项目进展
- ✅ 生日纪念日

**示例**：
```
群聊：明天下午 3 点开项目评审会
提取：
- 类型：会议
- 时间：明天 15:00
- 内容：项目评审会
- 参与人：群成员
```

---

### 2️⃣ 心情记录

**情绪识别**：
- 😊 开心/兴奋
- 😔 难过/沮丧
- 😠 生气/不满
- 😌 平静/放松
- 😰 焦虑/紧张

**示例**：
```
群聊：今天项目上线成功了，太开心了！
提取：
- 用户：张三
- 心情：😊 开心
- 原因：项目上线成功
- 时间：今天
```

---

### 3️⃣ 地点追踪

**位置记录**：
- 📍 工作地点
- 🏠 居住地点
- ✈️ 出差地点
- 🏖️ 旅游地点

**示例**：
```
群聊：我这周要去曼谷出差
提取：
- 用户：李四
- 类型：出差
- 地点：泰国曼谷
- 时间：本周
```

---

### 4️⃣ 人物档案

**档案内容**：
- 👤 基本信息（姓名、职位）
- 🎂 生日纪念日
- 🍜 饮食偏好
- 🎯 工作目标
- 📊 性格特点

**示例**：
```
人物档案：施玉
- 昵称：施主管
- 职位：市场营销
- 所在地：泰国曼谷
- 饮食偏好：不辣、喜欢甜食
- 生日：3 月 15 日
- 工作：印度市场营销
```

---

### 5️⃣ 待办管理

**待办提取**：
- ✅ 工作任务
- ✅ 个人计划
- ✅ 提醒事项
- ✅ 截止日期

**示例**：
```
群聊：记得明天提交周报
提取：
- 类型：待办
- 内容：提交周报
- 截止时间：明天
- 提醒：提前 1 小时
```

---

## 📊 记忆总结

### 每日总结

```
📅 群聊记忆日报 - 2026 年 3 月 8 日

【今日事件】
• 下午 3 点：项目评审会
• 晚上 8 点：团队聚餐

【心情记录】
• 张三：😊 项目上线成功
• 李四：😰 担心 deadline

【待办提醒】
• 明天：提交周报（张三）
• 后天：客户演示（李四）

【地点变化】
• 李四：本周曼谷出差
```

### 每周总结

```
📊 群聊记忆周报 - 2026 年第 10 周

【本周事件】
• 周一：项目启动会
• 周三：需求评审
• 周五：上线发布

【心情趋势】
• 周一：😰 紧张（项目启动）
• 周三：😌 平静（需求确认）
• 周五：😊 兴奋（成功上线）

【待办完成】
• 完成率：85%
• 未完成：2 项（延期）

【人物动态】
• 张三：负责后端开发
• 李四：负责前端开发
• 王五：产品经理
```

---

## 🔧 高级配置

### 自定义提取规则

```yaml
extraction:
  custom_rules:
    - pattern: "记得.*"
      type: reminder
    - pattern: "明天.*点"
      type: event
    - pattern: "开心 | 高兴 | 太好了"
      type: mood_happy
    - pattern: "难过 | 伤心 | 郁闷"
      type: mood_sad
```

### 提醒配置

```yaml
reminders:
  enabled: true
  advance_time: 3600  # 提前 1 小时提醒
  channels:
    - dingtalk
  format: markdown
```

### 隐私配置

```yaml
privacy:
  encrypt_data: true
  auto_delete_days: 90
  exclude_keywords:
    - "密码"
    - "机密"
    - "保密"
```

---

## 📁 文件结构

```
chat-memory-keeper/
├── SKILL.md                  # 技能说明（必需）
├── README.md                 # 本文件
├── LICENSE                   # MIT 许可证
├── CHANGELOG.md              # 变更日志
├── CONTRIBUTING.md           # 贡献指南
├── package.json              # 包配置
├── docs/                     # 文档目录
│   ├── user-guide.md         # 用户指南
│   ├── api-reference.md      # API 参考
│   └── platform-setup.md     # 平台配置
└── skills/
    └── chat-memory-keeper/
        └── SKILL.md          # 实际技能文件
```

---

## 🎯 使用场景

### 场景 1：项目团队群

```
群聊：项目攻坚队
功能：
- 会议安排自动提取
- 任务分配自动记录
- 进度更新自动追踪
- 每日站会自动总结
```

### 场景 2：家庭群

```
群聊：幸福一家人
功能：
- 生日纪念日提醒
- 家庭活动计划
- 家人心情记录
- 重要决定存档
```

### 场景 3：朋友群

```
群聊：快乐小分队
功能：
- 聚会活动安排
- 旅行计划记录
- 心情分享
- 美好回忆存档
```

---

## 🔄 版本历史

### v2.0.0 (2026-03-08)

**新增**：
- ✅ 支持钉钉、企业微信、Telegram
- ✅ 心情记录功能
- ✅ 地点追踪功能
- ✅ 人物档案构建
- ✅ 待办管理功能

**改进**：
- 📝 事件提取更准确
- 📊 总结报告更详细
- 🔒 隐私保护更完善

### v1.0.0 (2026-03-06)

**初始版本**：
- ✅ 基础事件提取
- ✅ 每日总结
- ✅ 钉钉支持

---

## 🤝 贡献

欢迎贡献！请查看 [CONTRIBUTING.md](CONTRIBUTING.md)

### 贡献方式

1. Fork 本仓库
2. 创建功能分支 (`git checkout -b feature/AmazingFeature`)
3. 提交更改 (`git commit -m 'Add some AmazingFeature'`)
4. 推送到分支 (`git push origin feature/AmazingFeature`)
5. 开启 Pull Request

---

## 📄 许可证

MIT License - 查看 [LICENSE](LICENSE) 文件

---

## 🔗 相关链接

- **OpenClaw 官方文档**: https://docs.openclaw.ai
- **ClawHub**: https://clawhub.com
- **黑猫技术博客**: https://gis-blackcaat.github.io/
- **相关 Skill**:
  - [domain-mentor](https://github.com/GIS-blackCaat/domain-mentor) - 领域学习导师
  - [methodology-matcher](https://github.com/GIS-blackCaat/methodology-matcher) - 任务方法论匹配器

---

## 📞 联系方式

- **GitHub**: [@GIS-blackCaat](https://github.com/GIS-blackCaat)
- **博客**: https://gis-blackcaat.github.io/

---

**最后更新**: 2026 年 3 月 8 日  
**维护者**: 黑猫 🐈‍⬛
