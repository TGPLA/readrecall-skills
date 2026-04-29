# EPUB 阅读器核心 — L3 模块 Skill

## 职责
翻页、渲染、位置同步、rendition 管理相关的开发。

## 快速路由

| 关键词 | 加载 L4 |
| --- | --- |
| 翻页不动/不响应 | `reader/page-turning/` |
| 进度条/位置不更新 | `reader/progress/` |
| 布局/面板/侧边栏 | `reader/layout/` |
| 初始化失败/报错 | `reader/progress/` |

---

## 核心概念

| 概念 | 说明 |
| --- | --- |
| `rendition` | epub.js 渲染实例，负责翻页/定位，通过 `renditionRef` 持有 |
| `book` | epub.js 书籍实例，负责加载和访问目录，通过 `bookRef` 持有 |
| `CFI` | Canonical Fragment Identifier，EPUB 内部位置格式，**不要用页码** |

---

## 核心文件

- `EPUBReader.tsx` — 阅读器主组件
- `EPUBYueDuQuYu.tsx` — 阅读区域
- `useEPUBReaderShiJian.ts` — 阅读器核心 Hook
- `useEPUBReader.ts` — rendition 初始化

---

## rendition 常用方法

| 方法 | 用途 |
| --- | --- |
| `rendition.next()` | 下一页 |
| `rendition.prev()` | 上一页 |
| `rendition.display(cfi)` | 跳转到指定位置 |
| `rendition.annotations.add()` | 添加标注 |
| `rendition.getContents()` | 获取 iframe 内容 |
| `rendition.on('relocated')` | 位置变化事件 |
| `rendition.on('displayed')` | 页面渲染完成事件 |
