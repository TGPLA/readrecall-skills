# 列表/卡片/表格 — L4 实现

## 职责
列表、卡片、Grid、Table、Pagination 分页组件。

## 关键词
Card、List、Table、Grid、Pagination、分页、Antd Table、Antd List

## 现有实现
- `AntdPagination` — 分页组件

## 常见问题
| 问题 | L4 |
| --- | --- |
| 分页参数错误 | `card/AntdPagination.md` |
| 筛选条件不更新 | `card/AntdPagination.md` |
| `getCurrentFilters` 不生效 | `card/AntdPagination.md` |

## 规范
- 列表用 Antd List 或自定义 Card 组件
- 分页用 Antd Pagination
- 筛选条件通过 URL params 同步
