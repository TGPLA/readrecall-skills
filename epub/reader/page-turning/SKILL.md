# 翻页 — L4 实现

## 职责
下一页、上一页、跳转页面不响应的排查。

## 关键词
翻页不动、下一页不响应、上一页卡住、next()、prev()

## 常见问题

| 问题 | 原因 | 解决 |
| --- | --- | --- |
| next() 不响应 | 已是最后一页 | 边界判断 `await rendition.next()` 需 try-catch |
| prev() 第一页报错 | 已是第一页 | 边界判断 `await rendition.prev()` 需 try-catch |
| 双击翻页变两页 | 事件触发两次 | 防抖或 flag 拦截 |

## 规范
```typescript
// 正确做法：加边界保护
const canGoNext = currentPage < totalPages;
const canGoPrev = currentPage > 1;
if (canGoNext) await rendition.next();
if (canGoPrev) await rendition.prev();
```
