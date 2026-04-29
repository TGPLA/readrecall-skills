# 划词交互 — L4 实现

## 职责
选中文本、弹出划线菜单、selection 事件处理。

## 关键词
划词、选中文本、selection、弹出菜单、textSelectionChange

## 划词流程
1. 用户选择文本 → `selectionchange` 或 `mouseup` 事件
2. 获取 `window.getSelection()` 的选中内容
3. 计算 CFI range（通过 rendition）
4. 显示浮动菜单（颜色选择 + 笔记按钮）

## 选中内容结构
```typescript
{
  anchorCfi: string;   // 选区起点 CFI
  focusCfi: string;    // 选区终点 CFI
  text: string;        // 选中的纯文本
}
```

## 常见问题
| 问题 | 解决 |
| --- | --- |
| 选中文本没反应 | 检查 selection 事件是否绑定到 iframe 内部 |
| CFI 为空 | rendition 未初始化完成，等待 displayed 事件 |
| 菜单位置偏移 | 用 `getRangeClientRects()` 计算绝对位置 |
