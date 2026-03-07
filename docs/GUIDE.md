# Chat Memory Keeper 使用指南

## 目录

1. [快速开始](#快速开始)
2. [核心功能](#核心功能)
3. [详细用法](#详细用法)
4. [配置说明](#配置说明)
5. [最佳实践](#最佳实践)
6. [故障排除](#故障排除)

---

## 快速开始

### 1. 安装

```bash
# 方式 1: ClawHub
npx clawhub@latest install chat-memory-keeper

# 方式 2: Git
git clone https://github.com/YOUR_USERNAME/chat-memory-keeper.git
cp -r chat-memory-keeper/skills/chat-memory-keeper ~/.openclaw/skills/
```

### 2. 配置群聊

编辑 `~/.openclaw/memory/chat-memory-config.json`:

```json
{
  "groups": [
    {
      "id": "your-group-id",
      "name": "你的群名称",
      "enabled": true
    }
  ]
}
```

### 3. 开始使用

在群里正常聊天，机器人会自动监听并提取信息。

---

## 核心功能

### 信息提取

| 要素 | 说明 | 示例 |
|------|------|------|
| **📅 时间** | 消息时间、事件时间 | "明天下午 3 点" |
| **👤 人物** | 提及的人名、角色 | "张三"、"产品经理" |
| **📍 地点** | 地理位置、场所 | "北京"、"公司会议室" |
| **🎯 事件** | 计划、任务、约定 | "下周上线"、"周五聚餐" |
| **💭 心情** | 情绪状态、感受 | "好累"、"太开心了" |
| **🔖 主题** | 讨论话题、项目 | "双 11 活动" |

### 人物档案

记录每个人的：
- 基本信息（角色、公司、地点）
- 关系网络（上级、同事、朋友）
- 近期状态（心情、事件）
- 待跟进事项

### 备忘录

每日自动整理：
- 事件记录（会议、约定）
- 心情记录（成员情绪）
- 待办事项（任务、截止）
- 话题摘要（讨论要点）

---

## 详细用法

### 查询命令

在群里@机器人：

| 命令 | 说明 | 示例 |
|------|------|------|
| `整理今天` | 整理今日聊天摘要 | `@机器人 整理今天` |
| `查 {人名}` | 查看人物档案 | `@机器人 查 张三` |
| `查 {日期}` | 查看备忘录 | `@机器人 查 3 月 6 日` |
| `查 待办` | 查看所有待办 | `@机器人 查 待办` |
| `查 事件` | 查看近期事件 | `@机器人 查 事件` |
| `导出` | 导出数据 | `@机器人 导出` |

### 配置命令

| 命令 | 说明 | 示例 |
|------|------|------|
| `开启监听` | 启用群聊监听 | `@机器人 开启监听` |
| `关闭监听` | 暂停监听 | `@机器人 关闭监听` |
| `开启摘要` | 启用每日摘要 | `@机器人 开启摘要` |
| `摘要改为 9 点` | 修改摘要时间 | `@机器人 摘要改为 9 点` |

---

## 配置说明

### 完整配置示例

```json
{
  "enabled": true,
  "groups": [
    {
      "id": "dingtalk-group-123",
      "name": "产品讨论群",
      "enabled": true,
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
  "privacy": {
    "maskPhoneNumbers": true,
    "maskIdCards": true,
    "retentionDays": 365
  },
  "notifications": {
    "dailySummary": true,
    "summaryTime": "22:00",
    "upcomingEvents": true,
    "eventReminderHours": 24
  }
}
```

### 配置项说明

| 配置项 | 说明 | 可选值 |
|--------|------|--------|
| `enabled` | 是否启用 | `true`/`false` |
| `groups[].extractLevel` | 提取详细度 | `basic`/`standard`/`detailed` |
| `extraction.*` | 提取开关 | `true`/`false` |
| `privacy.mask*` | 脱敏设置 | `true`/`false` |
| `privacy.retentionDays` | 保留天数 | 数字 |
| `notifications.summaryTime` | 摘要时间 | `"22:00"` |

---

## 最佳实践

### 群聊场景建议

| 场景 | 推荐配置 |
|------|----------|
| **工作群** | 提取事件 + 待办，关闭心情 |
| **朋友群** | 提取心情 + 事件，关闭待办 |
| **家庭群** | 提取事件 + 地点，简化模式 |
| **项目群** | 全量提取，详细模式 |

### 使用技巧

1. **定期整理**: 每周回顾一次备忘录
2. **及时更新**: 发现错误手动修正档案
3. **合理脱敏**: 敏感信息开启自动脱敏
4. **适度使用**: 避免过度记录侵犯隐私

### 隐私建议

- ✅ 开启手机号、身份证脱敏
- ✅ 设置合理的保留期限
- ✅ 定期导出备份重要数据
- ✅ 不存储原始聊天消息

---

## 故障排除

### 问题 1: 不提取信息

**检查**:
```bash
# 1. 检查配置
cat ~/.openclaw/memory/chat-memory-config.json

# 2. 检查技能是否加载
ls ~/.openclaw/skills/chat-memory-keeper/

# 3. 检查群 ID 是否正确
# 在群里@机器人发送"群 ID 是什么"
```

**解决**:
```
用户：@机器人 重新加载配置
```

### 问题 2: 提取不准确

**解决**:
```
用户：@机器人 重新分析刚才的消息
```

### 问题 3: 档案重复

**解决**:
```
用户：@机器人 合并 张三 和 老张 的档案
```

### 问题 4: 隐私担忧

**解决**:
```
用户：@机器人 删除我的所有数据
→ 执行删除并确认
```

---

## 扩展开发

### 添加新的提取规则

在 `skills/chat-memory-keeper/scripts/extractors/` 下添加：

```python
# custom_extractor.py
def extract_custom_entities(message):
    # 自定义提取逻辑
    pass
```

### 集成外部系统

```python
# 同步到 CRM
def sync_to_crm(profiles):
    pass

# 同步到日历
def sync_to_calendar(events):
    pass
```

---

## 相关文件

| 文件 | 说明 |
|------|------|
| `memory/chat-memory-config.json` | 主配置文件 |
| `memory/profiles/*.md` | 人物档案 |
| `memory/memos/*.md` | 备忘录 |
| `memory/events/*.json` | 事件索引 |

---

## 扩展阅读

- [OpenClaw 官方文档](https://docs.openclaw.ai/)
- [ClawHub 技能市场](https://clawhub.ai/)
- [贡献指南](../CONTRIBUTING.md)

---

<div align="center">

有问题？[提交 Issue](https://github.com/YOUR_USERNAME/chat-memory-keeper/issues)

</div>
