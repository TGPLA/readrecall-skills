# Mock — L4 实现

## 职责
vi.fn()、vi.mock()、vi.spyOn() 的正确使用。

## 关键词
mock、spy、vi.fn、vi.mock、stub、模拟函数

## Mock 函数

```typescript
// 基本 mock
const mockFn = vi.fn(() => 'mocked');
mockFn('hello');  // 'mocked'

// 预设返回值序列
mockFn.mockReturnValueOnce('first')
      .mockReturnValueOnce('second')
      .mockReturnValue('default');

// 模拟实现
mockFn.mockImplementation((arg: string) => \`processed: \${arg}\`);
```

## Mock 模块

```typescript
// mock 整个模块
vi.mock('@/shared/services/api', () => ({
  fetchBook: vi.fn().mockResolvedValue({ title: '测试书' }),
}));

// mock 部分
vi.mock('@/utils/helper', async (importOriginal) => {
  const actual = await importOriginal();
  return { ...actual, getUser: vi.fn() };
});
```

## Mock 第三方库

```typescript
// mock Antd
vi.mock('antd', async () => {
  const actual = await vi.importActual('antd');
  return { ...actual, message: { success: vi.fn(), error: vi.fn() } };
});
```

## 常见问题

| 问题 | 解决 |
| --- | --- |
| mock 不生效 | 检查是否在 vi.mock() 之后引用模块 |
| mock 被调用次数 | `expect(mockFn).toHaveBeenCalledTimes(1)` |
| 清除 mock | `mockFn.mockClear()` 或 `mockFn.mockReset()` |
