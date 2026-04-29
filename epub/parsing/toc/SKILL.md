# 目录解析 — L4 实现

## 关键词
目录为空、不显示目录、navigation、toc、章节目录

## 目录来源
- `book.loaded.navigation` — EPUB 官方目录
- `book.spine` — 阅读顺序脊（备用）

## 目录结构
```typescript
interface TocItem {
  id: string;
  href: string;
  title: string;
  subitems?: TocItem[];  // 嵌套子章节
}
```

## 常见问题

| 问题 | 原因 | 解决 |
| --- | --- | --- |
| 目录为空 | navigation 未加载完成 | 等待 `book.loaded.navigation` |
| 章节 href 404 | href 是相对路径需要拼接 baseUrl | 用 `new URL(href, baseUrl).href` |
| 目录顺序乱 | spine 和 toc 不一致 | 以 spine 顺序为准重排 |
