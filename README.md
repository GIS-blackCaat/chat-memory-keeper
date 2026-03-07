# Chat Memory Keeper / 群聊记忆管家

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![OpenClaw Skill](https://img.shields.io/badge/OpenClaw-Skill-blue.svg)](https://docs.openclaw.ai/tools/skills)
[![Languages](https://img.shields.io/badge/languages-EN%2FCN-red.svg)](README.md)
[![Version](https://img.shields.io/badge/version-2.0.0-green.svg)](CHANGELOG.md)

> **English**: Intelligent conversation analyzer for IM bots. Automatically extracts events, moods, tasks, and builds user profiles from group chats.
>
> **中文**: 智能群聊对话分析工具。自动从群聊中提取事件、心情、任务，构建人物档案和备忘录。

---

## 🌟 Features / 功能特性

| Feature / 功能 | English / 英文 | 中文 / Chinese |
|----------------|----------------|----------------|
| **Event Extraction** | ✅ Meetings, appointments, plans | ✅ 会议、约定、计划 |
| **Mood Tracking** | ✅ Emotional state analysis | ✅ 情绪状态分析 |
| **Profile Building** | ✅ Auto-build user profiles | ✅ 自动构建人物档案 |
| **Task Management** | ✅ Extract action items | ✅ 提取待办事项 |
| **Psychological Analysis** | ✅ Word choice & patterns | ✅ 用词和模式分析 |
| **Multi-channel** | ✅ DingTalk/WeChat/Telegram | ✅ 钉钉/微信/Telegram |
| **Privacy First** | ✅ Local storage only | ✅ 仅本地存储 |

---

## 🚀 Quick Start / 快速开始

### 1. Install / 安装

```bash
# Via ClawHub / 通过 ClawHub
npx clawhub@latest install chat-memory-keeper

# Or Git / 或 Git
git clone https://github.com/YOUR_USERNAME/chat-memory-keeper.git
cp -r chat-memory-keeper/skills/chat-memory-keeper ~/.openclaw/skills/
```

### 2. Configure / 配置

Create `~/.openclaw/memory/chat-memory-config.json`:

```json
{
  "enabled": true,
  "groups": [
    {
      "id": "your-group-id",
      "name": "My Group / 我的群",
      "enabled": true
    }
  ],
  "psychologicalAnalysis": {
    "enabled": true,
    "reportFrequency": "weekly"
  },
  "privacy": {
    "maskPhoneNumbers": true,
    "retentionDays": 365
  }
}
```

### 3. Use / 使用

In group chat / 在群聊中：

```
@bot summarize today / @机器人 整理今天
@bot check Zhang San / @机器人 查 张三
@bot check tasks / @机器人 查 待办
```

---

## 📊 How It Works / 工作原理

```
┌─────────────┐     ┌──────────────┐     ┌─────────────┐
│  Group Chat │ ──> │  AI Analysis │ ──> │   Profiles  │
│  群聊对话    │     │  AI 分析      │     │   人物档案   │
└─────────────┘     └──────────────┘     └─────────────┘
       │                    │                    │
       │                    │                    │
       ▼                    ▼                    ▼
┌─────────────┐     ┌──────────────┐     ┌─────────────┐
│   Events    │     │    Moods     │     │   Tasks     │
│   事件      │     │    心情      │     │   待办      │
└─────────────┘     └──────────────┘     └─────────────┘
```

---

## 🧠 Psychological Analysis / 心理分析

### Analysis Dimensions / 分析维度

| Dimension / 维度 | Weight / 权重 | Metrics / 指标 |
|------------------|---------------|----------------|
| **Word Choice / 用词** | 40% | Emotion words, pronouns, affirmations |
| **Interaction / 互动** | 30% | Reply patterns, response time |
| **Frequency / 频率** | 15% | Message count (reference) |
| **Speed / 速度** | 15% | Avg reply time (reference) |

### Example Report / 报告示例

```markdown
## Psychological Profile: Zhang San

### Word Analysis / 用词分析
- Affirmation words: 24% (High cooperation / 高配合度)
- Negation words: 3% (Low, may avoid disagreement / 低，可能避免反对)
- "We" vs "I": 12% vs 18% (Team oriented / 团队导向)

### Interaction Patterns / 互动模式
- Most replies to: Li Si (58%)
- Avg response time: 2 minutes
- Active hours: 9:00-18:00

### Insights / 洞察
✅ Cooperative team player / 合作的团队成员
⚠️ May need encouragement to express disagreements / 可能需要鼓励表达不同意见
```

---

## 🔒 Privacy & Security / 隐私与安全

### Data Storage / 数据存储

| Data Type / 数据类型 | Storage / 存储 | Retention / 保留 |
|---------------------|----------------|------------------|
| User Profiles / 人物档案 | Local / 本地 | Permanent / 永久 |
| Daily Memos / 每日备忘 | Local / 本地 | 365 days |
| Raw Messages / 原始消息 | ❌ Not stored / 不存储 | N/A |

### Privacy Features / 隐私功能

- ✅ **Local Only** - No cloud sync / 仅本地，无云端同步
- ✅ **Auto-Redaction** - Phone, ID, bank info / 自动脱敏
- ✅ **Configurable** - Set retention period / 可配置保留期
- ✅ **Export/Delete** - Full data control / 完全数据控制

---

## 📁 File Structure / 文件结构

```
chat-memory-keeper/
├── skills/chat-memory-keeper/
│   └── SKILL.md              # Skill definition / 技能定义
├── docs/
│   ├── GUIDE_EN.md           # English guide / 英文指南
│   ├── GUIDE_CN.md           # 中文指南
│   └── PSYCHOLOGY.md         # Analysis docs / 分析文档
├── memory/
│   ├── chat-memory-config.json  # Config / 配置
│   ├── profiles/                # User profiles / 人物档案
│   └── memos/                   # Daily memos / 每日备忘
├── README.md                   # This file / 本文件
├── LICENSE                     # MIT License
├── CONTRIBUTING.md             # Contribution guide / 贡献指南
└── package.json                # NPM config / NPM 配置
```

---

## 🌍 Supported Channels / 支持渠道

| Channel / 渠道 | Text / 文本 | Image / 图片 | File / 文件 | Stream / 流模式 |
|----------------|-------------|--------------|-------------|-----------------|
| **DingTalk / 钉钉** | ✅ | ✅ (Stream) | ✅ (Stream) | ✅ |
| **WeChat Work / 企微** | ✅ | ✅ | ✅ | ⏳ Coming |
| **Telegram** | ✅ | ✅ | ✅ | ⏳ Coming |
| **Slack** | ⏳ Coming | ⏳ Coming | ⏳ Coming | ⏳ Coming |

---

## ⚙️ Advanced Configuration / 高级配置

### Full Config Example / 完整配置示例

```json
{
  "version": "2.0.0",
  "enabled": true,
  "groups": [
    {
      "id": "dingtalk-group-xxx",
      "name": "Product Team / 产品团队",
      "enabled": true,
      "watchMembers": [],
      "extractLevel": "standard"
    }
  ],
  "extraction": {
    "events": true,
    "moods": true,
    "locations": true,
    "people": true,
    "tasks": true
  },
  "psychologicalAnalysis": {
    "enabled": true,
    "reportFrequency": "weekly",
    "weights": {
      "wordAnalysis": 0.40,
      "interactionPattern": 0.30,
      "messageFrequency": 0.15,
      "responseSpeed": 0.15
    }
  },
  "privacy": {
    "maskPhoneNumbers": true,
    "maskIdCards": true,
    "maskBankAccounts": true,
    "retentionDays": 365
  },
  "notifications": {
    "dailySummary": true,
    "summaryTime": "22:00",
    "channel": "dingtalk"
  }
}
```

---

## 🧪 Testing / 测试

### Test Commands / 测试命令

```bash
# Check installation / 检查安装
ls ~/.openclaw/skills/chat-memory-keeper/

# Check config / 检查配置
cat ~/.openclaw/memory/chat-memory-config.json

# View profiles / 查看档案
ls ~/.openclaw/memory/profiles/

# View memos / 查看备忘
ls ~/.openclaw/memory/memos/
```

### Test in Chat / 在聊天中测试

```
@bot test memory
@bot analyze this conversation
@bot show my profile
```

---

## 🤝 Contributing / 贡献

We welcome contributions in:

- 🌍 **Translations** - Help translate to more languages
- 🐛 **Bug fixes** - Report and fix issues
- ✨ **Features** - New analysis capabilities
- 📚 **Docs** - Improve documentation

See [CONTRIBUTING.md](CONTRIBUTING.md) for details.

欢迎贡献：

- 🌍 **翻译** - 帮助翻译更多语言
- 🐛 **Bug 修复** - 报告和修复问题
- ✨ **功能** - 新的分析能力
- 📚 **文档** - 改进文档

详见 [CONTRIBUTING.md](CONTRIBUTING.md)。

---

## 📄 License / 许可证

MIT License - See [LICENSE](LICENSE) file.

---

## 🙏 Acknowledgments / 致谢

- [OpenClaw](https://github.com/openclaw/openclaw) - AI assistant framework
- [ClawHub](https://clawhub.ai/) - Skill marketplace
- All contributors / 所有贡献者

---

<div align="center">

**Let AI remember what matters** 🧠

**让 AI 记住重要的事**

[Documentation](docs/) | [Issues](https://github.com/YOUR_USERNAME/chat-memory-keeper/issues) | [Discussions](https://github.com/YOUR_USERNAME/chat-memory-keeper/discussions)

Made with ❤️ by [Your Name](https://github.com/YOUR_USERNAME)

</div>
