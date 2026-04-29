# Context 全局状态 — L4 实现

## 职责
跨组件共享状态，不需要持久化的全局数据。

## 关键词
Context、跨组件、全局状态、useContext、Provider

## 规范
- 按业务域划分 Context，不要一个大Context
- 必要时用 useReducer 处理复杂状态
- 避免过度使用 Context（性能开销大）
