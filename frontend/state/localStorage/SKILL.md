# localStorage 持久化 — L4 实现

## 职责
数据持久化到本地存储。

## 关键词
localStorage、持久化、useLocalStorageState、存储

## 规范
- 使用 `use-local-storage-state` 包
- Key 命名：`readrecall_{功能}_{id}`
- 只存必要的轻量数据

## 已有实现
- 阅读进度（readrecall_progress_{bookId}）
- 用户设置（readrecall_settings）
- 划线笔记（readrecall_highlights_{bookId}）
