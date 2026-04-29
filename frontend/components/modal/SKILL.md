# 弹窗/对话框 — L4 实现

## 职责
所有 Modal、Dialog、Toast、Alert 等弹窗组件。

## 关键词
Dialog、弹窗、Modal、TanChuang、Alert、Toast、消息提示

## 现有实现
- `src/shared/utils/common/` — 通用 Toast、Loading

## 规范
- 使用 Antd `Modal.confirm()` 或自定义 TanChuang 组件
- 弹窗内容通过 `children` 或 `content` prop 传入
- 抽屉用 `Drawer` 组件，命名 `XxxChouTi.tsx`
