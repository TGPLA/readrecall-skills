# EPUB 阅读器 — L2 领域 Skill

## 职责
所有 EPUB 解析、阅读器核心、划线标注相关的开发任务，优先加载此文件做任务路由。

---

## 快速任务匹配 GT

| 关键词示例 | 加载 L3 | L4 路径 |
| --- | --- | --- |
| 翻页不动/下一页不响应 | `epub/reader/` | `reader/page-turning/` |
| 进度条不更新/位置丢失/CFI | `epub/reader/` | `reader/progress/` |
| 布局/面板/侧边栏/响应式 | `epub/reader/` | `reader/layout/` |
| 目录为空/章节href错误/navigation | `epub/parsing/` | `parsing/toc/` |
| 封面黑屏/封面不显示 | `epub/parsing/` | `parsing/cover/` |
| 书名/作者/元数据为空 | `epub/parsing/` | `parsing/metadata/` |
| 划词/选中文本/弹出菜单 | `epub/highlight/` | `highlight/selection/` |
| 划线颜色/笔记/标注/CFI不稳定 | `epub/highlight/` | `highlight/note/` |
| 打开书报错/EPUB解析失败 | `epub/parsing/` | `parsing/metadata/` |
| 初始化失败/rendition报错 | `epub/reader/` | `reader/progress/` |

---

## 核心依赖

- `epub` — EPUB 解析库
- `react-reader` — 阅读器封装组件
- `jszip` — ZIP 格式解压

## 阅读器核心概念

- `rendition` — epub.js 渲染实例，负责翻页/定位
- `book` — epub.js 书籍实例，负责加载和访问目录
- `location` — 当前位置（CFI 格式，不要用页码）
- `navigation` — 书籍目录结构

---

## 本领域 L3 模块清单

| L3 模块 | 路径 | 何时使用 |
| --- | --- | --- |
| 阅读器核心 | `epub/reader/` | 翻页、渲染、rendition、位置同步 |
| EPUB 解析 | `epub/parsing/` | 元数据、封面、章节目录 |
| 划线与标注 | `epub/highlight/` | 高亮、笔记、划线菜单 |
