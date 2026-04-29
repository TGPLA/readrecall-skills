# E2E 测试 — L3 模块 Skill

## 职责
Playwright 端到端测试的编写和修复。

## 快速路由

| 关键词 | 加载 L4 |
| --- | --- |
| 选择器找不到、定位失败 | `e2e/selector/` |
| 测试不稳定/flaky/超时 | `e2e/debug/` |
| CI 集成、GitHub Actions | `e2e/ci/` |

---

## 测试目录
`tests/` — Playwright E2E 测试

## 运行命令

```bash
npm run test:e2e       # 运行所有 E2E 测试
npm run test:e2e:ui     # 打开 Playwright UI 界面
npx playwright test --debug  # 调试模式
```

## Playwright 测试规范

```typescript
import { test, expect } from '@playwright/test';

test('登录失败后显示错误提示', async ({ page }) => {
  await page.goto('/auth');
  await page.fill('[data-testid="username"]', 'wrong');
  await page.fill('[data-testid="password"]', 'wrong');
  await page.click('[data-testid="login-btn"]');
  await expect(page.locator('.toast-error')).toBeVisible();
});
```

## 选择器优先级
1. `data-testid` — 最优先（需要开发时添加）
2. `role` — 如 `getByRole('button', { name: '登录' })`
3. `text` — 如 `getByText('提交')`
4. `CSS selector` — 最后考虑
