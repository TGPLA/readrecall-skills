# 阅读器布局 — L4 实现

## 职责
阅读区域、面板开关、侧边栏、响应式布局。

## 关键词
布局、面板、侧边栏、响应式、黑暗模式、字体大小

## 核心组件
- `EPUBYueDuQuYu.tsx` — 阅读区域容器
- `MuLuChouTi.tsx` — 目录抽屉
- `BiJiChouTi.tsx` — 笔记抽屉

## 布局状态
- 面板显隐通过 `useYueDuQiBuJu` Hook 管理
- 抽屉通过 Antd Drawer 控制

## 响应式
- 移动端隐藏侧边栏
- 平板横屏显示双页
