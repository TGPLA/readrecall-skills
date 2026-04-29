# 页面级组件 — L4 实现

## 职责
SEO、页面标题、路由级组件、页面布局。

## 关键词
SEO、页面标题、document.title、详情页、列表页、路由、URL 参数

## 常见任务

| 任务 | 方法 |
| --- | --- |
| 动态修改页签标题 | `document.title = 'xxx'` |
| 详情页标题不更新 | 路由参数变化时手动更新 title |
| 列表页 → 详情页跳转 | `useNavigate` + params |

## 规范
- 页面标题统一在 `useEffect` 中设置
- 详情页用 `useParams()` 获取路由参数
