# 前端开发 — L2 领域 Skill

## 职责
所有 React 组件、样式、交互、页面、性能相关的开发任务，优先加载此文件做任务路由。

---

## 快速任务匹配 GT

> 匹配到关键词后，直接加载对应 L3

| 关键词示例 | 加载 L3 | L4 路径 |
| --- | --- | --- |
| **组件** Select、Dialog、Button、Form、Calendar、DatePicker、Antd、分页、Pagination、Card、Grid、Table | `frontend/components/` | `components/modal/` · `components/drawer/` · `components/form/` · `components/card/` |
| **样式** Tailwind、CSS、深色模式、响应式、间距、布局、dark | `frontend/components/` | 样式相关子路由 |
| **请求/API** request、axios、fetch、请求、响应、权限、Token、会员 | `frontend/hooks/` | `hooks/useFetch/` · `hooks/useAuth/` |
| **页面** 列表、详情页、编辑页、SEO、页面标题、路由、URL 参数 | `frontend/components/` | `components/page/` |
| **调试/报错** 空白、不显示、内存、性能、卡顿、Failed to fetch、网络错误、API 失败、重复请求 | `frontend/hooks/` | `hooks/debug/` |
| **Hooks** UseEffect、UseCallback、UseMemo、Cannot access、before initialization、闭包问题 | `frontend/hooks/` | `hooks/debug/` |
| **状态** Zustand、get()、状态不更新、状态读取、localStorage、持久化 | `frontend/state/` | `state/localStorage/` · `state/context/` |
| **EPUB/阅读器** 翻页、渲染、标注、划词、目录、进度、CFI | `frontend/hooks/` | 已有 `useEPUBReaderShiJian` 等 Hook |

---

## 技术栈

- **框架**：React 19 + TypeScript
- **样式**：Tailwind CSS
- **构建**：Vite
- **状态**：useState / useLocalStorageState / useContext / useReducer
- **图标**：lucide-react
- **UI 库**：Antd（部分）

---

## 本领域 L3 模块清单

| L3 模块 | 路径 | 何时使用 |
| --- | --- | --- |
| 组件开发 | `frontend/components/` | 新建/修改 UI 组件时 |
| Hook 开发 | `frontend/hooks/` | 自定义逻辑/数据请求时 |
| 状态管理 | `frontend/state/` | 状态持久化/跨组件共享时 |

---

## 组件命名规范

- 组件文件：`PascalCase.tsx`（如 `BookShelf.tsx`）
- Hook 文件：`usePascalCase.ts`（如 `useEPUBReaderShiJian.ts`）
- 工具函数：`camelCase.ts`（如 `showToast.ts`）
- 弹窗：`XxxTanChuang.tsx`、抽屉：`XxxChouTi.tsx`

---

## 常见任务 → L3 映射

| 任务 | 加载 L3 |
| --- | --- |
| 改书架页面样式 | `frontend/components/` |
| 加一个弹窗/抽屉 | `frontend/components/` |
| 处理用户输入/表单提交 | `frontend/components/` |
| 发送 API 请求/权限校验 | `frontend/hooks/` |
| 存数据到 localStorage | `frontend/state/` |
| 新页面/路由/SEO | `frontend/components/` |
| 报错排查/空白页/性能 | `frontend/hooks/` |
| Hook 内部状态不更新 | `frontend/hooks/` |
| Context 全局状态 | `frontend/state/` |
