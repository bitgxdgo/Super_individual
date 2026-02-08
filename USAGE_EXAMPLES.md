# 使用示例 - 实战演练

本文档提供真实的使用场景示例，帮助你快速掌握 AI 开发工作流程。

---

## 📝 示例 1: 添加用户认证功能

### 场景
你需要在应用中添加用户认证功能，包括登录、注册和会话管理。

### 工作流程

#### 步骤 1: 探索阶段

**你的输入**:
```
我需要添加用户认证功能。让我们使用 /explore 来理解如何最好地实现它。
```

**AI 使用 `/explore` 的输出**:
```markdown
## 探索摘要

### 问题理解
- 需要完整的用户认证系统
- 包括注册、登录、登出功能
- 需要会话管理和持久化
- 需要保护特定路由

### 技术范围
受影响的文件:
- `src/api/auth.ts` (新建)
- `src/middleware/authMiddleware.ts` (新建)
- `src/routes/userRoutes.ts` (修改)
- `src/models/User.ts` (新建)
- `src/utils/jwt.ts` (新建)

关键依赖:
- bcrypt (密码哈希)
- jsonwebtoken (JWT 令牌)
- express-session (可选)

潜在影响:
- 需要数据库迁移添加 users 表
- 现有路由需要添加认证中间件
- 前端需要处理认证状态

### 需要澄清
1. 使用 JWT 还是 session？
2. 需要支持社交登录吗？
3. 密码复杂度要求？
4. Token 过期时间？

### 现有模式
- 项目使用 Express.js
- 数据库是 PostgreSQL
- 已有错误处理中间件

### 建议的方法
- 使用 JWT 进行无状态认证
- bcrypt 进行密码哈希
- 中间件保护路由
- Refresh token 机制
```

---

#### 步骤 2: 澄清需求

**你的输入**:
```
1. 使用 JWT
2. 暂时不需要社交登录
3. 密码至少 8 位，包含字母和数字
4. Access token 15分钟，Refresh token 7天

请创建执行计划。
```

---

#### 步骤 3: 创建计划

**AI 使用 `/create-plan` 的输出**:
```markdown
# 用户认证功能实现计划

**总体进度**: `0%`

## TLDR
实现基于 JWT 的用户认证系统，包含注册、登录、Token 刷新和路由保护。

## 实现步骤

### ⬜ 步骤 1: 数据库和模型
**目的**: 创建用户数据模型和数据库表
**文件**:
- `src/models/User.ts`
- `src/migrations/001_create_users_table.sql`

**任务**:
- [ ] 定义 User 接口和类型
- [ ] 创建数据库迁移脚本
- [ ] 实现密码哈希方法
- [ ] 添加用户验证方法

---

### ⬜ 步骤 2: JWT 工具函数
**目的**: 创建 JWT 生成和验证工具
**文件**:
- `src/utils/jwt.ts`

**任务**:
- [ ] 实现 generateAccessToken
- [ ] 实现 generateRefreshToken
- [ ] 实现 verifyToken
- [ ] 添加错误处理

---

### ⬜ 步骤 3: 认证 API 端点
**目的**: 实现注册、登录、登出 API
**文件**:
- `src/api/auth.ts`
- `src/routes/authRoutes.ts`

**任务**:
- [ ] POST /api/auth/register
- [ ] POST /api/auth/login
- [ ] POST /api/auth/refresh
- [ ] POST /api/auth/logout
- [ ] 输入验证和错误处理

---

### ⬜ 步骤 4: 认证中间件
**目的**: 保护需要认证的路由
**文件**:
- `src/middleware/authMiddleware.ts`

**任务**:
- [ ] 实现 authenticate 中间件
- [ ] Token 验证逻辑
- [ ] 用户信息注入到 request
- [ ] 错误响应处理

---

### ⬜ 步骤 5: 集成到现有路由
**目的**: 保护现有的 API 端点
**文件**:
- `src/routes/userRoutes.ts`
- `src/routes/index.ts`

**任务**:
- [ ] 添加认证中间件到保护路由
- [ ] 更新路由配置
- [ ] 测试受保护路由

---

### ⬜ 步骤 6: 测试 & 验证
**目的**: 确保认证系统正常工作
**任务**:
- [ ] 测试注册流程
- [ ] 测试登录流程
- [ ] 测试 Token 刷新
- [ ] 测试受保护路由访问
- [ ] 测试错误场景

---

## 风险 & 注意事项
- Token 密钥必须保密（环境变量）
- 密码必须始终哈希，绝不存储明文
- 需要防止暴力破解攻击（考虑速率限制）
- Refresh token 应该可以撤销

## 成功标准
- [ ] 用户可以成功注册
- [ ] 用户可以登录并获得 token
- [ ] Token 可以用于访问受保护路由
- [ ] Token 过期后可以刷新
- [ ] 密码安全存储（哈希）
- [ ] 所有错误情况得到妥善处理
```

**保存位置**: `plans/user-authentication-plan.md`

---

#### 步骤 4: 执行实施

**你的输入**:
```
计划看起来很好！让我们使用 /execute 开始实施。从步骤 1 开始。
```

**AI 执行过程**:
```markdown
**总体进度**: `17%`

### 🟡 步骤 1: 数据库和模型
正在实现...

[AI 创建 User.ts 文件]
[AI 创建数据库迁移文件]
[实施密码哈希方法]

- [x] 定义 User 接口和类型
- [x] 创建数据库迁移脚本
- [x] 实现密码哈希方法
- [ ] 添加用户验证方法
```

继续每个步骤...

---

#### 步骤 5: 代码审查

**你的输入**:
```
实施完成了。请使用 /review 进行全面的代码审查。
```

**AI 使用 `/review` 的输出**:
```markdown
## 代码审查报告

### ✅ 看起来不错
- 密码使用 bcrypt 正确哈希
- JWT 签名使用环境变量密钥
- 错误处理完善
- TypeScript 类型定义清晰

### ⚠️ 发现的问题

#### 🟡 **中等** [src/api/auth.ts:45] - 缺少速率限制
- **问题**: 登录端点没有速率限制，容易受到暴力破解攻击
- **建议**: 添加 express-rate-limit 中间件
- **影响**: 安全风险

#### 🔵 **轻微** [src/utils/jwt.ts:12] - Token 过期时间硬编码
- **问题**: Token 过期时间在代码中硬编码
- **建议**: 移到配置文件或环境变量
- **影响**: 可维护性

#### 💡 **建议** [src/models/User.ts:67] - 可以添加邮箱验证
- **问题**: 没有邮箱验证流程
- **建议**: 考虑添加邮箱验证功能
- **影响**: 用户体验和安全性提升

## 审查摘要

**总体评估**: 良好

**必须修复** (阻碍合并):
- [ ] 添加登录速率限制

**建议修复**:
- [ ] 将 Token 过期时间移到配置
```

---

#### 步骤 6: 更新文档

**你的输入**:
```
修复了审查中的问题。现在使用 /document 更新文档。
```

**AI 使用 `/document` 的输出**:
```markdown
## 文档更新摘要

### 更新的文件
- [x] CHANGELOG.md
- [x] README.md
- [x] API_DOCS.md (新建)

### CHANGELOG 条目
```markdown
## [Unreleased]

### Added
- 用户认证系统 (#001)
  - JWT 基础的认证
  - 注册、登录、登出 API
  - Token 刷新机制
  - 路由保护中间件
  - 速率限制防护
```

---

## 🐛 示例 2: 修复分页 Bug

### 场景
用户报告分页功能在边缘情况下失败。

### 工作流程

#### 步骤 1: 记录 Issue

**你的输入**:
```
使用 /create-issue: 当用户在最后一页时点击"下一页"，应用崩溃。
```

**AI 输出**:
```markdown
# 分页边缘情况导致应用崩溃

## TL;DR
当用户在数据的最后一页点击"下一页"按钮时，应用抛出未捕获的异常导致崩溃。

## 当前 vs 预期
**当前**: 在最后一页点击"下一页"会导致应用崩溃
**预期**: 应该禁用"下一页"按钮或显示友好提示

## 受影响的文件
- `src/components/Pagination.tsx`
- `src/hooks/usePagination.ts`
- `src/api/dataService.ts`

## 类型 & 优先级
- 类型: bug
- 优先级: high
- 工作量: small

## 注意事项
- 可能影响所有使用分页的列表页面
- 需要检查其他边缘情况（如空数据、第一页）
```

**保存位置**: `issues/2024-01-15-pagination-crash.md`

---

#### 步骤 2: 探索问题

**你的输入**:
```
使用 /explore 找出根本原因。
```

**AI 分析**:
```markdown
## 探索摘要

### 问题理解
- Pagination 组件没有检查是否有下一页
- API 调用假设总是有数据返回
- 错误处理不完善

### 技术范围
受影响的文件:
- `src/components/Pagination.tsx` - UI 组件
- `src/hooks/usePagination.ts` - 分页逻辑
- `src/api/dataService.ts` - API 调用

### 根本原因
1. `usePagination` hook 没有计算 `hasNextPage`
2. API 响应没有包含总页数信息
3. 组件没有禁用按钮的逻辑

### 建议的修复
1. 在 API 响应中添加 `totalPages` 和 `hasMore`
2. Hook 中计算 `hasNextPage` 状态
3. 组件根据状态禁用按钮
```

---

#### 步骤 3: 快速修复

**你的输入**:
```
这是个小 bug，直接使用 /execute 修复，不需要详细计划。
```

**AI 修复并更新**:
```markdown
✅ 修复完成

### 更改内容
1. **dataService.ts**: API 响应添加 totalPages
2. **usePagination.ts**: 添加 hasNextPage 计算
3. **Pagination.tsx**: 根据状态禁用按钮
4. **添加边缘情况测试**
```

---

#### 步骤 4: 审查和文档

**你的输入**:
```
使用 /review 快速审查，然后 /document 更新 CHANGELOG。
```

---

## 🎓 示例 3: 学习 React Server Components

### 场景
你想在项目中使用 React Server Components，但不太了解。

**你的输入**:
```
使用 /learning-opportunity: 我想了解 React Server Components，特别是它如何适用于我们的项目。
```

**AI 教学输出**:
```markdown
# React Server Components

## 🎯 核心概念（2分钟阅读）

### 这是什么？
React Server Components (RSC) 是一种新的组件类型，可以在服务器上渲染，不会发送任何 JavaScript 到客户端。

### 为什么它存在？
解决的问题：
- 减少客户端 JavaScript 包大小
- 改善初始加载性能
- 直接访问服务器资源（数据库、文件系统）

### 什么时候使用？
适合：
- 数据获取繁重的组件
- 不需要交互的内容展示
- SEO 重要的页面

示例场景：
- 博客文章列表
- 产品详情页
- 仪表板数据展示

---

## ⚙️ 工作原理（5分钟阅读）

[详细解释机制、权衡、示例代码...]

---

## 🔍 深入探讨（10分钟阅读）

[技术实现、高级模式、常见陷阱...]

---

## 📚 在我们的项目中

基于你的代码库，RSC 最适合用于：
1. `src/pages/Dashboard.tsx` - 数据繁重
2. `src/pages/ProductList.tsx` - SEO 重要
3. `src/components/StaticContent.tsx` - 无交互

建议的迁移策略：
[具体步骤...]
```

---

## 🔄 示例 4: 大型功能重构

### 场景
需要重构支付系统以支持多种支付方式。

### 完整工作流程

```
1. /create-issue
   → 记录重构需求和动机

2. /explore
   → 深入分析现有支付系统
   → 识别所有依赖和影响
   → 列出需要澄清的问题

3. [讨论和澄清]

4. /create-plan
   → 创建分阶段的重构计划
   → 每个阶段可独立测试
   → 包含回滚策略

5. /execute (阶段 1)
   → 实施第一阶段
   → 更新进度

6. /review (阶段 1)
   → 审查第一阶段代码

7. [重复 5-6 直到完成所有阶段]

8. /peer-review
   → 获取另一个模型的审查意见
   → 验证架构决策

9. /document
   → 更新所有文档
   → 添加迁移指南

10. /learning-opportunity (可选)
    → 如果遇到新的设计模式
    → 深入学习
```

---

## 💡 实用技巧

### 何时跳过某些步骤

**小 Bug 修复**:
```
/create-issue → /explore (快速) → /execute → /document
```

**简单功能添加**:
```
/explore → /execute → /review
```

**复杂新功能**:
```
完整流程，不要跳过任何步骤
```

---

### 组合命令使用

**快速迭代**:
```
你: 修复这个bug，审查，然后更新文档
AI: [依次使用 /execute, /review, /document]
```

**学习驱动开发**:
```
你: 我不太懂这个设计模式，先教我，然后我们实现它
AI: [使用 /learning-opportunity, 然后 /explore, /create-plan, /execute]
```

---

## 🎯 常见场景速查

| 场景 | 推荐命令流程 | 预计时间 |
|------|-------------|---------|
| 新功能（中等） | explore → create-plan → execute → review → document | 2-4 小时 |
| 新功能（大型） | 同上 + peer-review | 1-2 天 |
| Bug 修复（简单） | create-issue → execute → review | 30分钟 |
| Bug 修复（复杂） | create-issue → explore → execute → review | 1-2 小时 |
| 重构 | explore → create-plan → execute (分阶段) → peer-review → document | 1-3 天 |
| 学习新技术 | learning-opportunity → explore (应用到项目) | 1-2 小时 |

---

## 📈 效果对比

### 传统开发方式
```
开始编码 → 遇到问题 → 重构 → 发现更多问题 → 再重构 → 文档过时
时间: 8 小时，质量: 中等，文档: 过时
```

### 使用工作流程
```
explore (30分) → plan (30分) → execute (4小时) → review (30分) → document (30分)
时间: 6 小时，质量: 高，文档: 同步
```

**节省**: 2小时 + 更高质量 + 更好文档 🎉

---

## 🚀 开始你的第一个任务

准备好了吗？选择一个真实的任务：

1. **如果是新功能**: 从 `/explore` 开始
2. **如果是 bug**: 从 `/create-issue` 开始
3. **如果要学习**: 从 `/learning-opportunity` 开始

记住：第一次可能感觉慢，但很快你会发现它实际上更快、质量更高！

---

**提示**: 保存你成功使用这个工作流程的案例，建立你自己的最佳实践库！ 📚

