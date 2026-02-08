# Super Individual - AI 开发工作流程

这个项目集成了 Zevi 的 AI 开发工作流程系统，提供了一套完整的命令和最佳实践，帮助你用 AI 更高效地开发。

## 🎯 这是什么？

一套结构化的命令系统，将 AI 辅助开发转变为可预测、高质量的工作流程。每个命令代表开发周期中的一个检查点。

## 🚀 快速开始

### 第一次使用？

1. **阅读快速参考**: 查看 `QUICK_REFERENCE.md` 了解所有命令
2. **浏览命令文档**: 查看 `.cursor/commands/README.md` 获取详细说明
3. **开始第一个功能**: 从 `/explore` 开始

### 典型工作流程

```mermaid
graph LR
    A[/explore] --> B[/create-plan]
    B --> C[/execute]
    C --> D[/review]
    D --> E[/document]
    
    F[/create-issue] -.-> A
    D -.-> G[/peer-review]
    G -.-> D
    
    H[/learning-opportunity] -.-> A
```

## 📋 命令概览

### 开发流程命令
- **`/create-issue`** - 快速捕获 bug 或功能需求
- **`/explore`** - 在编码前深入理解问题
- **`/create-plan`** - 生成详细的执行计划
- **`/execute`** - 按计划实施功能
- **`/review`** - 进行全面的代码审查
- **`/peer-review`** - 获取其他 AI 模型的审查意见
- **`/document`** - 更新所有相关文档

### 学习命令
- **`/learning-opportunity`** - 深入学习新概念（三层次教学）

## 📁 项目结构

```
Super_individual/
├── .cursor/
│   └── commands/           # 所有命令的详细文档
│       ├── README.md
│       ├── create-issue.md
│       ├── explore.md
│       ├── create-plan.md
│       ├── execute.md
│       ├── review.md
│       ├── peer-review.md
│       ├── document.md
│       └── learning-opportunity.md
│
├── issues/                 # 存放创建的 issues
├── plans/                  # 存放执行计划
│
├── .cursorrules           # Cursor 配置
├── README.md              # 本文件
└── QUICK_REFERENCE.md     # 快速参考指南
```

## 💡 使用示例

### 示例 1: 添加新功能

```
你: 我想添加用户认证功能

AI: 让我们从 /explore 开始...
[AI 探索现有代码库，识别依赖关系]

你: 看起来不错，请创建计划

AI: [使用 /create-plan 创建详细计划]

你: 批准了，开始实施

AI: [使用 /execute 按步骤实施]

你: 完成后请审查

AI: [使用 /review 进行代码审查]

你: 更新文档

AI: [使用 /document 更新 README 和 CHANGELOG]
```

### 示例 2: 修复 Bug

```
你: 登录时出现错误

AI: 让我用 /create-issue 记录这个问题...
[创建结构化的 issue]

你: 现在找出原因

AI: [使用 /explore 分析问题]
[发现根本原因]

你: 修复它

AI: [使用 /execute 修复]
[使用 /review 验证]
```

### 示例 3: 学习新概念

```
你: 什么是 React Server Components？

AI: 让我用 /learning-opportunity 解释...
[提供三层次解释：核心概念 → 工作原理 → 深入探讨]
```

## 🎓 最佳实践

### 开始任何新功能时
1. ✅ 总是从 `/explore` 开始
2. ✅ 获得计划批准后再编码
3. ✅ 增量实施和测试
4. ✅ 代码审查不是可选的
5. ✅ 立即更新文档

### 保持高质量
- 🔍 **探索阶段**: 提出澄清问题
- 📝 **计划阶段**: 将大任务分解为小步骤
- ⚡ **执行阶段**: 遵循现有模式
- 🔎 **审查阶段**: 要彻底但建设性
- 📚 **文档阶段**: 保持文档与代码同步

### 上下文管理技巧
- 💾 **保存计划**: 在单独的文件中跟踪进度
- 🔄 **刷新上下文**: 当太长时开始新会话
- 🎯 **保持专注**: 一次一个功能
- 📊 **跟踪状态**: 使用表情符号更新计划

## 🛠️ 自定义

这个工作流程是完全可定制的！

### 修改现有命令
编辑 `.cursor/commands/` 中的文件以适应你的项目需求。

### 添加新命令
在 `.cursor/commands/` 中创建新的 `.md` 文件。

### 调整工作流程
根据团队偏好修改标准流程。

## 📊 工作流程对比

### 传统方式
```
❌ 直接编码 → 遇到问题 → 重构 → 返工 → 文档过时
```

### 使用这个工作流程
```
✅ 探索 → 计划 → 增量实施 → 持续审查 → 同步文档
```

**结果**: 更少的返工，更高的质量，更好的文档 🎉

## 🔧 AI 模型建议

根据任务选择合适的模型：

| 任务类型 | 推荐模型 | 原因 |
|---------|---------|------|
| 规划 & 架构 | Claude | 擅长长期思考和结构化 |
| 调试复杂 Bug | Codex | 深入理解代码 |
| UI 开发 | Gemini | 视觉和界面设计 |
| 快速迭代 | Composer | 速度优先 |

## 📚 资源

- **命令详细文档**: `.cursor/commands/README.md`
- **快速参考**: `QUICK_REFERENCE.md`
- **原始工作流程**: [Zevi's Notion](https://shorthaired-billboard-f9a.notion.site/Zevi-s-AI-Development-Workflow-2c86baffbc90810fa63bd0ee8ecffce9)

## 🤝 贡献

发现了改进这个工作流程的方法？
1. 在你的项目中测试
2. 记录效果
3. 分享你的经验

## 💬 问题和反馈

如果你在使用过程中有任何问题或建议，欢迎反馈！

---

## 🎯 下一步

1. **阅读** `QUICK_REFERENCE.md` 快速上手
2. **探索** `.cursor/commands/` 了解每个命令
3. **开始** 你的第一个功能 - 从 `/explore` 开始！

---

**提示**: 第一次使用时可能感觉有点慢，但很快你就会发现它实际上节省了大量返工时间。坚持使用这个工作流程几天，你会看到质量的提升！ 🚀

---

_基于 [Zevi's AI Development Workflow](https://shorthaired-billboard-f9a.notion.site/Zevi-s-AI-Development-Workflow-2c86baffbc90810fa63bd0ee8ecffce9) 创建_

