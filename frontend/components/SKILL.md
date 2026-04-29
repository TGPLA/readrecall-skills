# 前端组件 — L3 模块 Skill

## 职责
所有 UI 组件的创建、修改、样式相关任务。

---

## 组件目录

- `src/features/books/components/` — 书籍相关组件
- `src/features/user/components/` — 用户相关组件
- `src/shared/utils/common/` — 通用 UI 组件（Toast、Loading 等）

---

## 组件类型参考

| 类型 | 说明 | 命名示例 |
| --- | --- | --- |
| 容器型 | 持有状态，管理子组件 | `EPUBReader.tsx` |
| 展示型 | 纯接收 props，渲染 UI | `BookCard.tsx` |
| 弹窗/抽屉型 | 弹窗 `XxxTanChuang` · 抽屉 `XxxChouTi` | `MuLuChouTi.tsx`、`BiJiChouTi.tsx` |
| 表单型 | 用户输入、提交 | `EPUBDaoRuTanChuang.tsx` |

---

## L4 子模块路由

| 功能 | L4 路径 | 关键词 |
| --- | --- | --- |
| 弹窗/对话框 | `components/modal/` | Dialog、Modal、弹窗 |
| 抽屉面板 | `components/drawer/` | Drawer、抽屉、ChouTi |
| 表单 | `components/form/` | Form、表单、DatePicker、Calendar |
| 列表/卡片 | `components/card/` | Card、List、Table、Grid、Pagination |
| 按钮/选择器 | `components/button/` | Button、Select、Antd |
| 页面级组件 | `components/page/` | SEO、页面标题、document.title |
| 样式/布局 | `components/style/` | Tailwind、CSS、深色、响应式、间距 |

---

## 新建组件流程

1. 确定组件类型（容器/展示/弹窗/表单）
2. 确定放哪个目录
3. 按命名规范命名（PascalCase.tsx）
4. 优先使用 Tailwind 样式
5. 导出类型定义清晰

---

## 样式规范

- 使用 Tailwind CSS
- 深色模式：`dark:` 前缀
- 响应式：`md:`、`lg:` 断点
- 间距：Tailwind spacing scale
