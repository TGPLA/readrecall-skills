# Vite 构建 — L4 实现

## 职责
Vite 构建配置、构建失败排查。

## 关键词
构建失败、build报错、Vite、dist、preview、预览

## 常用命令

```bash
npm run build      # 生产构建
npm run preview    # 预览构建结果
npm run dev        # 开发模式
```

## 常见问题

| 问题 | 原因 | 解决 |
| --- | --- | --- |
| Module not found | 路径别名未配置/大小写错误 | 检查 vite.config.ts alias |
| Export not found | 导出方式不对 | 检查 tsconfig 和导出语法 |
| 构建产物空白 | 路径 base 配置错误 | 检查 vite.config base |
| Chunk 过大 | 代码分割不当 | 检查 dynamic import |
