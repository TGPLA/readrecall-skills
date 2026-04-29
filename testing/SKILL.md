# 测试 — L2 领域 Skill

## 职责
所有测试相关的开发任务，优先加载此文件做任务路由。

---

## 快速任务匹配 GT

| 关键词示例 | 加载 L3 | L4 路径 |
| --- | --- | --- |
| mock、spy、vi.fn() | `testing/unit/` | `unit/mock/` |
| expect、断言、toBe、toEqual | `testing/unit/` | `unit/assertion/` |
| 测试失败/不通过/AssertionError | `testing/unit/` | `unit/debug/` |
| 选择器找不到/not found/定位 | `testing/e2e/` | `e2e/selector/` |
| flaky/超时/调试/截图 | `testing/e2e/` | `e2e/debug/` |
| CI/GitHub Actions/自动化 | `testing/e2e/` | `e2e/ci/` |
| 组件测试/Hook测试 | `testing/unit/` | — |
| UI流程测试/登录测试 | `testing/e2e/` | — |

---

## 技术栈

- **单元测试**：Vitest + @testing-library/react
- **E2E 测试**：Playwright
- **测试路径**：`tests/` 目录

---

## 本领域 L3 模块清单

| L3 模块 | 路径 | 何时使用 |
| --- | --- | --- |
| 单元测试 | `testing/unit/` | vitest 单元测试、mock、断言 |
| E2E 测试 | `testing/e2e/` | Playwright 端到端、选择器、CI |
