# 断言 — L4 实现

## 职责
Vitest 常用断言、常见断言写法。

## 关键词
expect、toBe、toEqual、toThrow、toHaveBeenCalledWith

## 常用断言

| 断言 | 用途 |
| --- | --- |
| `expect(x).toBe(y)` | 原始值相等（===） |
| `expect(x).toEqual(y)` | 深度相等（对象/数组） |
| `expect(() => fn()).toThrow()` | 函数抛出错误 |
| `expect(arr).toContain(item)` | 数组包含元素 |
| `expect(obj).toHaveProperty('key')` | 对象有某属性 |
| `expect(fn).toHaveBeenCalled()` | 函数被调用过 |
| `expect(fn).toHaveBeenCalledWith(a, b)` | 函数用指定参数调用 |
| `expect(Promise).resolves.toEqual(val)` | Promise resolves |
| `expect(Promise).rejects.toThrow()` | Promise rejects |

## 异步测试

```typescript
// 方式1：async/await
it('should fetch book', async () => {
  const book = await fetchBook('123');
  expect(book.title).toBe('测试书');
});

// 方式2：resolves/rejects
it('should throw for invalid id', async () => {
  await expect(fetchBook('')).rejects.toThrow('Invalid id');
});
```

## 常见问题

| 问题 | 解决 |
| --- | --- |
| 对象相等失败 | 用 `toEqual` 而不是 `toBe`（深度比较） |
| 浮点数相等 | 用 `toBeCloseTo()` 代替 `toBe` |
| 数组顺序不同 | `toEqual` 会深度比较，考虑 `toContainEqual` |
