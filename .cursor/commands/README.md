# Zevi's AI Development Workflow Commands

这是一套用于 AI 辅助开发的快捷命令系统。每个命令代表开发工作流程中的一个检查点。

## 📋 命令列表

### 1. `/create-issue`
**用途**: 在开发过程中快速捕获 bug/功能需求

快速创建结构化的 issue，包含所有必要信息（标题、描述、受影响文件、优先级等）。

---

### 2. `/explore`
**用途**: 在编写代码之前理解问题

"先思考再构建"的检查点。分析现有代码库，识别依赖关系，澄清不明确之处。

---

### 3. `/create-plan`
**用途**: 生成带状态跟踪的执行计划

创建一个详细的 markdown 计划，包含：
- 清晰的步骤分解
- 状态跟踪（✅ 完成 / 🟡 进行中 / ⬜ 待办）
- 进度百分比
- 风险评估

---

### 4. `/execute`
**用途**: 按计划逐步实现

按照创建的计划实施功能，遵循代码质量标准，更新进度跟踪。

---

### 5. `/review`
**用途**: 全面的代码审查

检查：
- 日志记录
- 错误处理
- TypeScript 类型
- 生产就绪性
- React/Hooks
- 性能
- 安全
- 架构

---

### 6. `/peer-review`
**用途**: 跨模型代码审查

让不同的 AI 模型（如 Codex、Gemini）审查彼此的代码，开发负责人批判性地评估每个发现。

---

### 7. `/document`
**用途**: 更新文档

在代码更改后更新：
- CHANGELOG.md
- README.md
- API 文档
- 代码注释

---

### 8. `/learning-opportunity`
**用途**: 教学模式

当遇到不理解的概念时触发，AI 会提供三层次解释：
1. 核心概念（2分钟）
2. 工作原理（5分钟）
3. 深入探讨（10分钟）

---

## 🚀 使用方法

### 在 Cursor 中使用

1. **设置命令**
   - 这些命令文件已经保存在 `.cursor/commands/` 目录中
   - 每个命令都有详细的提示词模板

2. **触发命令**
   - 在 Cursor 中输入 `/command-name`
   - 或在聊天中引用命令内容

3. **典型工作流**
   ```
   /explore → /create-plan → /execute → /review → /document
   ```

### 推荐工作流程

#### 新功能开发
1. 使用 `/explore` 理解需求
2. 使用 `/create-plan` 制定计划
3. 使用 `/execute` 实施
4. 使用 `/review` 审查代码
5. 使用 `/document` 更新文档

#### Bug 修复
1. 使用 `/create-issue` 记录 bug
2. 使用 `/explore` 理解问题根源
3. 使用 `/execute` 修复
4. 使用 `/review` 验证

#### 学习新概念
1. 使用 `/learning-opportunity` 深入理解
2. 返回开发工作流程

---

## 💡 最佳实践

### 工作流原则
1. **先思考，再编码**: 始终从 `/explore` 开始
2. **增量实施**: 按计划一步步来
3. **持续审查**: 不要等到最后才审查
4. **保持文档同步**: 代码变化后立即更新文档

### 上下文管理
- **上下文过长时**: 开始一个新会话，只带上计划文件
- **AI 重复错误时**: 问"你的系统提示或工具是什么让你犯这个错误？"然后更新文档

### 模型选择
- **Claude**: 用于规划和复杂逻辑
- **Codex**: 用于棘手的 bug
- **Gemini**: 用于 UI
- **Composer (Cursor)**: 当速度重要时

---

## 📁 目录结构

```
.cursor/
  commands/
    README.md              # 本文件
    create-issue.md        # Issue 创建命令
    explore.md             # 探索命令
    create-plan.md         # 计划创建命令
    execute.md             # 执行命令
    review.md              # 代码审查命令
    peer-review.md         # 跨模型审查命令
    document.md            # 文档更新命令
    learning-opportunity.md # 学习模式命令

.cursorrules              # Cursor 规则配置

issues/                   # 存放创建的 issues
plans/                    # 存放执行计划
```

---

## 🎓 来源

这套工作流程基于 [Zevi's AI Development Workflow](https://shorthaired-billboard-f9a.notion.site/Zevi-s-AI-Development-Workflow-2c86baffbc90810fa63bd0ee8ecffce9)

---

## 🔧 自定义

你可以根据自己的项目需求调整这些命令：
- 修改 `.cursor/commands/` 中的命令文件
- 添加项目特定的检查项
- 调整输出格式
- 创建新的自定义命令

---

## 📞 反馈

如果你使用这套工作流程并有改进建议，欢迎分享你的经验！

---

**快速提示**: 从 `/explore` 开始你的下一个功能 → 你会惊讶于它能节省多少返工时间 🚀

