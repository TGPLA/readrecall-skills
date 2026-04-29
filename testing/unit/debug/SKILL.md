# 测试不通过排查 — L4 实现

## 职责
单元测试失败的原因分析和修复。

## 关键词
测试失败、测试不通过、failing test、Assertion、Error

## 排查顺序

1. 看错误信息 — 是 AssertionError 还是代码报错
2. 看实际值 vs 期望值 — AssertionError 会显示差异
3. 检查测试依赖 — mock 是否生效
4. 检查异步 — 是否缺少 async/await

## 常见错误类型

| 错误 | 原因 | 解决 |
| --- | --- | --- |
| `TypeError: Cannot read property 'xxx' of undefined` | 缺少 mock 或 setup | 在 beforeEach 中初始化 |
| `Expected: 5, Received: undefined` | 返回值没 mock | 检查 mock 返回值 |
| `act()` warning | 状态更新未等待 | 用 `await act(async () => {...})` |
| `vi.fn()` called but not expected | mock 未清除 | `afterEach(() => vi.clearAllMocks())` |

## 规范
```typescript
beforeEach(() => {
  vi.clearAllMocks();   // 清除上次调用记录
  vi.restoreAllMocks();  // 恢复原生方法
});

afterEach(() => {
  // 清理
});
```
