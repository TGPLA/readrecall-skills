# 进度/位置同步 — L4 实现

## 职责
阅读进度存储、位置同步、进度条更新、CFI 存储。

## 关键词
进度条不更新、位置不保存、CFI、进度、relocated、location.start

## 核心逻辑
- 进度用 `CFI` 格式存储，不用页码
- 在 `rendition.on('relocated')` 里同步进度
- `location.start.cfi` = 当前位置 CFI

## 常见问题

| 问题 | 解决 |
| --- | --- |
| 进度条不更新 | 检查 relocated 事件是否绑定，`location.start.cfi` 是否有值 |
| 重新打开书位置丢失 | localStorage key 拼写错误，或 CFI 格式损坏 |
| 进度跳到开头 | CFI 解析失败，用 try-catch 保护 |

## 存储规范
- Key: `readrecall_progress_{bookId}`
- Value: `{ cfi: string, percentage: number, updatedAt: number }`
