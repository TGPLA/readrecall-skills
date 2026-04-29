# 笔记 — L4 实现

## 职责
划线笔记的创建、编辑、删除、存储。

## 关键词
笔记、note、标注、划线笔记、bi ji

## 笔记数据结构
```typescript
interface HuaXian {
  id: string;
  cfiRange: string;    // CFI 位置（不稳定）
  accurateCfiRange: string;  // 精确 CFI
  text: string;        // 原文
  note?: string;       // 用户笔记
  color: 'huang'|'lv'|'lan'|'hong';
  createdAt: number;
  bookId: string;
}
```

## 存储
- Key: `readrecall_highlights_{bookId}`
- 每次保存全量覆盖（简单可靠）

## CFI 不稳定问题
- 同一位置每次解析 CFI 可能不同
- 保存时用 `accurateCfiRange`
- 加载时做模糊匹配（允许小范围误差）
