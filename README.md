# 阅读回响 Skills 库 — Trae 使用指南

---

## 这是什么

一套 **4 层结构的任务路由系统**。

当你收到开发需求时，按照「关键词匹配 → 加载对应文件 → 执行」的方式工作。每个文件只告诉你「遇到什么问题去哪里找」，不重复写项目规范。

---

## 4 层结构速览

```
L1 (你首先看这里)
  SKILL.md
  作用：关键词匹配 → 路由到对应 L2

L2 (按需加载)
  frontend/    epub/    testing/    deploy/
  作用：领域划分 → 路由到对应 L3

L3 (按需加载)
  components/  hooks/  reader/  parsing/
  作用：模块划分 → 路由到对应 L4

L4 (最终执行依据)
  modal/SKILL.md    page-turning/SKILL.md
  作用：具体问题的排查方法、代码规范、常见错误处理
```

---

## 日常用法（3 步）

### 第 1 步：收到需求后，先读 L1

打开 `SKILL.md`，根据需求中的**关键词**匹配到对应 L2 路径。

示例：用户说「弹窗点不出来」
→ 关键词匹配：`弹窗` → `frontend/components/`
→ 加载 `frontend/components/SKILL.md`

### 第 2 步：L2 的 GT 表路由到 L3/L4

每个 L2 SKILL.md 都有「快速路由表」，告诉你具体加载哪个 L3/L4。

示例：看到 L2 表里写「弹窗/对话框 → modal/」
→ 加载 `frontend/components/modal/SKILL.md`

### 第 3 步：按 L4 内容执行

L4 文件里包含：
- 这个问题的常见原因
- 排查步骤
- 代码规范
- 已有实现的路径

---

## L2 领域速查

| 需求类型 | 加载 |
| --- | --- |
| React 组件、Hook、样式、API 请求 | `frontend/` |
| EPUB 阅读器、翻页、目录、划线、笔记 | `epub/` |
| 单元测试、E2E、CI、mock | `testing/` |
| 构建、nginx、部署、回滚、SSL | `deploy/` |
| 复杂任务拆解、发散思考、复盘 | 工具类 SKILL.md（直接加载） |

---

## 如何可持续化完善

### 原则：遇到就记，不要等

在开发过程中，发现新问题或新模式时，立即沉淀到对应 L4，不要碎片化积累。

---

### 场景 1：排查了一个 bug，总结了方法

**操作**：把排查方法和根因写成 L4 文档。

**示例**：排查了「rendition.next() 在最后一页报错」问题
→ 写入 `epub/reader/page-turning/SKILL.md`
→ 如果已有文件，就在对应章节补充

---

### 场景 2：发现某个模块有新的实现方式

**操作**：更新对应 L3/L4 的规范说明。

**示例**：开始在阅读器用 `useReducer` 管理翻页状态
→ 在 `epub/reader/progress/SKILL.md` 补充状态管理方案

---

### 场景 3：某个关键词路由不准

**操作**：更新 L2 的 GT 表，补充更准确的关键词。

**示例**：之前路由到 `frontend/hooks/debug/` 的词，实际应该去 `frontend/components/`
→ 修改 `frontend/SKILL.md` 的 GT 表

---

### 场景 4：新增了一个领域或模块

**操作**：新建 L3 目录 + L3 SKILL.md + 至少一个 L4。

**示例**：新增「微信登录」功能
→ 新建 `frontend/auth/SKILL.md`（L3）
→ 新建 `frontend/auth/wechat/SKILL.md`（L4）
→ 更新 `frontend/SKILL.md` 的 L3 清单和 GT 表

---

### 场景 5：工具类 skill 有改进

**操作**：直接更新对应 SKILL.md 的内容。

**示例**：`任务拆解` 的流程需要优化
→ 更新 `任务拆解/SKILL.md`
→ 在 commit 信息里注明「更新了 xxx」

---

## 更新后推送到 GitHub

```
cd ~/.hermes/skills/  或  cd 项目 .trae/skills/
git add -A
git commit -m "feat: 更新/新增 xxx（描述改了什么）"
git push origin main
```

**注意**：
- 只推送 skill 文件，不要推送统计文件、临时文件
- commit 信息格式：`feat:` 新功能 / `fix:` 修复 / `docs:` 文档 / `refactor:` 重构

---

## 文件命名规范

- 目录名：英文（模块名）/ kebab-case
- 文件名：`SKILL.md`（每个目录的入口）
- 说明性文档：中文命名（如 `Failed-to-fetch排查.md`）

---

## 禁止行为

- ❌ 不确定时瞎猜 → 先加载对应 L2 看 GT 表
- ❌ 重复造轮子 → 先看 L4 里的「已有实现」章节
- ❌ 跳过 L4 直接写代码 → L4 是执行依据
- ❌ 推送不相关文件 → 只推 skill 相关内容

---

## 相关文件

- 项目规范：`./rules/`（代码规范、Git 规范等）
- Agent 提示词：`.trae/agent_prompt.md`
- Skills 库（独立仓库）：https://github.com/TGPLA/readrecall-skills
