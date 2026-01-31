# PR 文档归档目录

> **目录定位**：本目录用于归档所有 Pull Request 的 Pre-Post 文档，记录完整的开发历程。

---

## 📁 目录结构

```
04_project_management/
├── pr_documents/         ← PR 文档归档（你在这里）
│   ├── feature/          ← 功能开发 PR
│   ├── fix/              ← Bug 修复 PR
│   ├── refactor/         ← 重构 PR
│   └── docs/             ← 文档更新 PR
│
├── brainstorm/           ← 头脑风暴记录
│   ├── {tag}_{YYYY-MM-DD}_{topic}.md
│   └── README.md
│
└── README.md             ← 本文件
```

---

## 📝 PR 文档命名规范

### 文档命名格式

```
{YYYY-MM-DD}_PR-{简短标题}_{Pre|Post|全流程}.md
```

### 示例

```
2026-01-31_PR-btree-index_Pre.md
2026-01-31_PR-btree-index_全流程.md
2026-01-31_PR-fix-leak_Post.md
```

### 目录分类

| 类型 | 目录 | 说明 |
|------|------|------|
| **feature** | `feature/` | 新功能开发 |
| **fix** | `fix/` | Bug 修复 |
| **refactor** | `refactor/` | 代码重构 |
| **docs** | `docs/` | 文档更新 |
| **perf** | `perf/` | 性能优化 |
| **test** | `test/` | 测试相关 |

---

## 🔄 PR 文档生命周期

### 1. Pre 文档（开发前）

**时机**：开发前编写

**内容**：
- 任务范围
- 背景与问题
- 目标与验收标准
- 实施方案
- 风险评估

**状态**：📋 待评审 → ✅ 已通过 → 🔄 开发中

### 2. Post 文档（开发后）

**时机**：开发完成后编写

**内容**：
- 核心成果总结
- 开发过程
- 测试与验证
- 未完成项与后续计划
- 提交记录

**状态**：📋 待评审 → ✅ 已通过 → 🔄 已合并

### 3. 全流程文档（归档）

**时机**：PR 合并后归档

**内容**：
- Pre 文档（完整版）
- Post 文档（完整版）
- 代码审查报告（如有）
- 测试报告（如有）

---

## 📊 文档模板

### Pre 文档模板

详见 `CLAUDE.md` 中的"文档规范"章节。

### Post 文档模板

详见 `CLAUDE.md` 中的"文档规范"章节。

---

## 🧠 头脑风暴（Brainstorm）

### 用途

记录开发过程中的：
- 发现（Findings）
- 建议（Proposals）
- 决策（Decisions）

### 命名格式

```
{tag}_{YYYY-MM-DD}_{topic}.md
```

### Tag 分类

| Tag | 说明 | 示例 |
|-----|------|------|
| **finding** | 发现的问题 | `transport_2026-01-23_rpc-issue.md` |
| **proposal** | 改进建议 | `metadata_2026-01-18_strong-typed.md` |
| **decision** | 技术决策 | `gossip_2026-01-19_udp-tcp-choice.md` |
| **review** | 代码审查 | `code_2026-01-30_simplifier-report.md` |
| **test** | 测试分析 | `testing_2026-01-29_test-plan.md` |

### 示例

```markdown
# Gossip: UDP vs TCP 分析

> **日期**: 2026-01-19
> **类型**: 决策 (decision)
> **相关模块**: 网络层、Gossip 协议

---

## 背景
分析 Gossip 协议使用 UDP 还是 TCP 的优缺点。

## 分析
| 方面 | UDP | TCP |
|------|-----|-----|
| 性能 | 更低延迟 | 更高延迟 |
| 可靠性 | 需要应用层保证 | 内置可靠性 |
| 复杂度 | 需要重试机制 | 简单 |

## 决策
使用 TCP 作为 Gossip 协议的传输层。

## 原因
1. 简化实现
2. 内置可靠性保证
3. 连接复用提高效率
```

---

## 📋 检查清单

### Pre 文档检查

- [ ] 任务范围清晰
- [ ] 目标可衡量（SMART）
- [ ] 技术方案可行
- [ ] 风险已识别
- [ ] 验收标准明确

### Post 文档检查

- [ ] 所有目标已达成
- [ ] 测试覆盖率 ≥ 80%
- [ ] 性能指标达标
- [ ] 文档完整准确
- [ ] 代码已审查

### 归档检查

- [ ] Pre 文档已完整
- [ ] Post 文档已完整
- [ ] CI 已通过
- [ ] PR 已合并
- [ ] 分支已删除

---

## 🔍 查找文档

### 按类型查找

```bash
# 查找所有功能开发 PR
ls pr_documents/feature/

# 查找所有 Bug 修复 PR
ls pr_documents/fix/
```

### 按日期查找

```bash
# 查找特定日期的 PR
ls pr_documents/*/*2026-01-31*
```

### 按关键词查找

```bash
# 搜索特定关键词
grep -r "btree" pr_documents/
```

---

## 📈 统计信息

### PR 统计

可以通过以下命令统计：

```bash
# 统计 PR 数量
find pr_documents -name "*_全流程.md" | wc -l

# 按类型统计
find pr_documents/feature -name "*.md" | wc -l
find pr_documents/fix -name "*.md" | wc -l
```

### Brainstorm 统计

```bash
# 统计头脑风暴数量
find brainstorm -name "*.md" | wc -l
```

---

## ⚠️ 注意事项

### 文档归档时机

- ✅ PR 合并后立即归档
- ✅ 确保文档完整（Pre + Post）
- ✅ 更新文档状态为"已归档"

### 文档版本控制

- ✅ 所有文档纳入 Git 版本控制
- ✅ 不要删除或修改已归档的文档
- ✅ 如有补充，创建新版本文档

### 敏感信息

- ❌ 不要在文档中记录敏感信息
- ❌ 不要记录 API 密钥、密码等
- ✅ 使用占位符代替真实值

---

## 📚 相关文档

- `CLAUDE.md` - 开发流程规范（包含 12 步 PR 工作流程）
- `02_development/01_编码规范文档.md` - 编码规范
- `03_test/01_测试计划文档.md` - 测试计划

---

**文档版本**: v1.0
**创建日期**: 2026-01-31
**最后更新**: 2026-01-31
**维护者**: LiteKV 开发团队
