# 选择器 — L4 实现

## 职责
Playwright 选择器写法、最佳实践、常见错误。

## 关键词
选择器、selector、locator、找不到元素、not found

## 选择器优先级（从高到低）

1. **data-testid** — 开发者显式添加，测试最稳定
   ```typescript
   await page.getByTestId('login-btn').click();
   ```

2. **role + name** — 语义化，接近无障碍
   ```typescript
   await page.getByRole('button', { name: '登录' }).click();
   await page.getByRole('textbox', { name: '用户名' }).fill('xxx');
   ```

3. **text** — 按文本内容定位
   ```typescript
   await page.getByText('提交').click();
   await page.getByLabel('记住我').check();
   ```

4. **CSS / XPath** — 最后手段
   ```typescript
   await page.locator('.ant-btn-primary').click();
   await page.locator('input[type="text"]').first().fill('xxx');
   ```

## 常用选择器 API

```typescript
page.locator(selector)        // 创建定位器
.locator().first()            // 第一个
.locator().last()             // 最后一个
.locator().nth(n)             // 第 n 个
.locator().filter({...})      // 过滤
.locator().getByText('xxx')   // 嵌套查找
```

## 常见问题

| 问题 | 解决 |
| --- | --- |
| 元素被遮挡 | 用 `force: true` 或先滚动 |
| 元素不可见 | 等待 `toBeVisible()` |
| 多个匹配 | 加 `.first()` 或用 filter 精确匹配 |
