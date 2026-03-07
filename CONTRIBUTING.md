# 贡献指南

感谢你有兴趣为 Chat Memory Keeper 做出贡献！🎉

## 如何贡献

### 1. 提交新功能

我们欢迎任何有价值的功能改进！

**步骤**:
1. Fork 本仓库
2. 创建功能分支：`git checkout -b feat/your-feature`
3. 提交改动：`git commit -m "feat: add your feature"`
4. 推送到分支：`git push origin feat/your-feature`
5. 创建 Pull Request

### 2. 修复 Bug

发现 Bug？请提交修复！

**步骤**:
1. 创建 Issue 描述 Bug
2. Fork 并创建修复分支：`git checkout -b fix/issue-123`
3. 提交修复：`git commit -m "fix: resolve issue #123"`
4. 创建 PR 并关联 Issue

### 3. 改进文档

文档和代码一样重要！

**可以改进的地方**:
- 修正错别字/语法错误
- 补充使用示例
- 翻译文档
- 改进排版

### 4. 报告问题

发现问题？请提交 Issue！

**好的 Issue 应包含**:
- 问题描述（清晰具体）
- 复现步骤（如何触发）
- 期望行为（应该怎样）
- 实际行为（实际怎样）
- 环境信息（OpenClaw 版本、IM 渠道等）

---

## 开发流程

### 1. 设置开发环境

```bash
# Fork 仓库
git clone https://github.com/YOUR_USERNAME/chat-memory-keeper.git
cd chat-memory-keeper

# 创建分支
git checkout -b feat/your-feature-name
```

### 2. 本地测试

```bash
# 链接到 OpenClaw
ln -s $(pwd)/skills/chat-memory-keeper ~/.openclaw/skills/chat-memory-keeper

# 测试技能
openclaw send "@机器人 整理今天"
```

### 3. 提交代码

```bash
# 提交
git add .
git commit -m "feat: add your feature description"

# 推送
git push origin feat/your-feature-name
```

### 4. 创建 PR

1. 访问你的 Fork
2. 点击 "Compare & pull request"
3. 填写 PR 描述
4. 等待审核

---

## 代码规范

### 提交信息格式

```
<type>: <description>

[optional body]

[optional footer]
```

**type 类型**:
- `feat`: 新功能
- `fix`: 修复 bug
- `docs`: 文档更新
- `style`: 格式调整
- `refactor`: 重构
- `test`: 测试相关
- `chore`: 构建/工具

**示例**:
```
feat: add mood trend analysis

- Add weekly mood chart
- Add mood-based recommendations
- Add emoji support for mood tags

Closes #45
```

### 文件命名

- 技能文件：`SKILL.md` (大写)
- 文档文件：`GUIDE.md` (大写)
- 配置文件：`chat-memory-config.json` (小写)
- 档案模板：`_template.md` (下划线前缀)

### Markdown 规范

- 使用 UTF-8 编码
- 标题使用 `#` 符号
- 代码块指定语言
- 表格对齐

---

## 审核流程

1. **自动检查**: GitHub Actions 运行格式检查
2. **人工审核**: 维护者审核代码质量和功能实用性
3. **合并**: 审核通过后合并到主分支

**审核标准**:
- ✅ 功能实用，有明确使用场景
- ✅ 代码规范，符合项目风格
- ✅ 文档完整，包含使用示例
- ✅ 无隐私安全问题

---

## 功能建议

### 优先级分类

| 优先级 | 说明 | 示例 |
|--------|------|------|
| P0 | 核心功能，影响使用 | 信息提取错误 |
| P1 | 重要功能，强烈需求 | 新的 IM 渠道支持 |
| P2 | 改进功能，提升体验 | 更好的查询语法 |
| P3 | 优化功能，锦上添花 | UI 美化 |

### 功能建议模板

```markdown
## 功能描述
简要描述功能

## 使用场景
什么情况下会用到

## 期望效果
希望达到什么效果

## 替代方案
目前如何绕过这个问题
```

---

## 常见问题

### Q: 我可以提交商业功能吗？
A: 可以，但需声明利益相关，且功能需有普适价值。

### Q: 多久能审核通过？
A: 通常 3-7 个工作日，复杂功能可能更长。

### Q: 如何成为维护者？
A: 持续贡献高质量内容后，会被邀请成为维护者。

### Q: 支持哪些 IM 渠道？
A: 目前支持钉钉、企业微信，欢迎提交其他渠道的适配。

---

## 致谢

所有贡献者都会被记录在 [CONTRIBUTORS.md](CONTRIBUTORS.md) 中。

感谢每一位让 Chat Memory Keeper 变得更好的人！❤️

---

<div align="center">

准备好贡献了吗？[开始 Fork](https://github.com/YOUR_USERNAME/chat-memory-keeper/fork)

</div>
