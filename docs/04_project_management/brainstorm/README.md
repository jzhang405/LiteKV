# 头脑风暴记录

> **目录定位**：记录开发过程中的发现、建议和决策。

---

## 📝 文档用途

### 记录类型

| 类型 | Tag | 说明 |
|------|-----|------|
| **发现** | `finding` | 开发中发现的问题或机会 |
| **建议** | `proposal` | 改进建议或新功能想法 |
| **决策** | `decision` | 技术决策及其原因 |
| **审查** | `review` | 代码审查报告 |
| **测试** | `test` | 测试分析和结果 |

---

## 📂 文件命名格式

```
{tag}_{YYYY-MM-DD}_{topic}.md
```

### 示例

```
btree_2026-01-31_node-structure-proposal.md
storage_2026-01-31_mvcc-implementation-decision.md
code_2026-01-31_refactor-report.md
test_2026-01-31-performance-analysis.md
```

---

## 📄 文档模板

### 发现 (Finding)

```markdown
# {主题}: {简短标题}

> **日期**: YYYY-MM-DD
> **类型**: 发现 (finding)
> **相关模块**: 模块名称

---

## 问题描述
描述发现的问题或机会

## 分析
详细分析问题

## 影响
说明影响范围和严重程度

## 建议
提出改进建议
```

### 建议 (Proposal)

```markdown
# {主题}: {简短标题}

> **日期**: YYYY-MM-DD
> **类型**: 建议 (proposal)
> **相关模块**: 模块名称

---

## 背景说明
为什么需要这个改进

## 当前问题
描述当前存在的问题

## 建议方案
详细的改进方案

## 预期效果
实施后的预期效果

## 实施计划
如何实施这个建议
```

### 决策 (Decision)

```markdown
# {主题}: {简短标题}

> **日期**: YYYY-MM-DD
> **类型**: 决策 (decision)
> **相关模块**: 模块名称

---

## 背景
需要决策的问题背景

## 可选方案
| 方案 | 优点 | 缺点 |
|------|------|------|
| 方案1 | ... | ... |
| 方案2 | ... | ... |

## 决策
选择方案X

## 决策理由
为什么选择这个方案

## 后续行动
如何实施这个决策
```

### 审查 (Review)

```markdown
# {主题}: {简短标题}

> **日期**: YYYY-MM-DD
> **类型**: 审查 (review)
> **相关 PR**: #PR编号

---

## 审查范围
描述审查的代码范围

## 审查结果
### P0（高风险）
- [ ] 问题1

### P1（中风险）
- [ ] 问题2

### P2（低风险）
- [ ] 问题3

## 改进建议
提出具体的改进建议

## 后续计划
如何处理这些问题
```

---

## 🔍 查找文档

### 按类型查找

```bash
# 查找所有决策文档
ls *decision*.md

# 查找所有建议文档
ls *proposal*.md
```

### 按日期查找

```bash
# 查找特定日期的文档
ls *2026-01-31*
```

### 按模块查找

```bash
# 查找特定模块的文档
ls btree_*
ls storage_*
```

---

## 📊 统计信息

### 按类型统计

```bash
# 统计各类文档数量
echo "Finding: $(ls *finding*.md 2>/dev/null | wc -l)"
echo "Proposal: $(ls *proposal*.md 2>/dev/null | wc -l)"
echo "Decision: $(ls *decision*.md 2>/dev/null | wc -l)"
echo "Review: $(ls *review*.md 2>/dev/null | wc -l)"
echo "Test: $(ls *test*.md 2>/dev/null | wc -l)"
```

---

## 📚 相关文档

- `../README.md` - 项目管理目录说明
- `CLAUDE.md` - 开发流程规范

---

**文档版本**: v1.0
**创建日期**: 2026-01-31
**最后更新**: 2026-01-31
**维护者**: LiteKV 开发团队
