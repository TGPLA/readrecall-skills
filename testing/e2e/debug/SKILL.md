# E2E 调试 — L4 实现

## 职责
测试不稳定、flaky、timeout、调试方法。

## 关键词
flaky、超时、timeout、调试、不稳定、重试

## 调试方法

```bash
# 截图
await page.screenshot({ path: 'debug.png' });

# 控制台日志
await page.on('console', msg => console.log(msg.text()));

# 录制视频
# playwright.config.ts:
const config: PlaywrightTestConfig = {
  use: { video: 'retain-on-failure' },
};

# 逐步执行
npx playwright test --debug --timeout=99999999
```

## 等待策略

```typescript
// 不要用固定 sleep，用智能等待
await expect(page.getByText('加载完成')).toBeVisible({ timeout: 10000 });

// 显式等待
await page.waitForLoadState('networkidle');

// API 拦截
await page.route('**/api/book', route => route.fulfill({ status: 200 }));
```

## 常见问题

| 问题 | 解决 |
| --- | --- |
| timeout 过期 | 加长 timeout 或检查网络 |
| flakiness | 用 `page.waitForLoadState('domcontentloaded')` 代替 sleep |
| 元素延迟出现 | 用 `waitForSelector` 代替 click |
| 重复请求 | 在 beforeEach 清理 localStorage / cookies |

## 重试配置（playwright.config.ts）
```typescript
retries: process.env.CI ? 2 : 0,
timeout: 30000,
```
