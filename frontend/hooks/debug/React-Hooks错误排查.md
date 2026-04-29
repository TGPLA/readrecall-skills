# React Hooks 错误排查指南

## 常见错误

### Cannot access 'Xxx' before initialization
- 原因：变量在定义前被引用（Temporal Dead Zone）
- 解决：检查变量声明顺序，确保在函数顶部

### Hooks called conditionally
- 原因：在 if/try-catch/循环中调用 Hook
- 解决：Hook 必须在组件顶部无条件调用

### Stale closure（闭包陷阱）
- 原因：useEffect/useCallback 捕获了旧的 state/props
- 解决：使用 useRef 存储最新值，或在依赖数组中正确填写

## useEffect 依赖问题
- 依赖数组为空 → 只执行一次
- 依赖数组漏填 → 使用旧值
- 依赖数组过多 → 循环触发
