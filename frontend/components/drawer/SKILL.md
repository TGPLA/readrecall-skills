# 抽屉面板 — L4 实现

## 职责
侧边滑出的抽屉面板，如目录抽屉、笔记抽屉。

## 关键词
Drawer、抽屉、ChouTi、侧边栏、侧滑

## 现有实现
- `MuLuChouTi.tsx` — 目录抽屉
- `BiJiChouTi.tsx` — 笔记抽屉

## 规范
- 命名：`XxxChouTi.tsx`
- 使用 Antd `Drawer` 或自定义
- 通过 `visible`/`open` prop 控制显示
