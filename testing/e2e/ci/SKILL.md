# CI 集成 — L4 实现

## 职责
GitHub Actions 集成 Playwright、CI 环境配置。

## 关键词
CI、GitHub Actions、CI 环境、自动化测试、pipeline

## GitHub Actions 配置

```yaml
# .github/workflows/e2e.yml
name: E2E Tests

on: [push, pull_request]

jobs:
  e2e:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      
      - name: Setup Node
        uses: actions/setup-node@v4
        with:
          node-version: '20'
          cache: 'npm'
      
      - name: Install dependencies
        run: npm ci
      
      - name: Install Playwright
        run: npx playwright install --with-deps chromium
      
      - name: Run E2E tests
        run: npm run test:e2e
        env:
          CI: true
```

## CI 环境注意点

| 问题 | 解决 |
| --- | --- |
| 浏览器不存在 | `npx playwright install --with-deps chromium` |
| 截图/视频上传 | CI 通常无头模式，截图需上传到 artifact |
| 端口冲突 | 用 `0` 端口或 `--port` 指定 |
| 测试超时 | CI 网络慢，适当增大 timeout |

## Artifact 上传（失败时保存截图）
```yaml
- uses: actions/upload-artifact@v4
  if: failure()
  with:
    name: playwright-report
    path: playwright-report/
```
