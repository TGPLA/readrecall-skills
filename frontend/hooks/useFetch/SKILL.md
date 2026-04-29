# API 请求 — L4 实现

## 职责
axios/fetch 封装、API 调用、权限校验。

## 关键词
request、api、axios、fetch、请求、响应、权限、Token、会员

## 规范
- 统一使用 axios 封装
- 请求拦截器处理 Token
- 响应拦截器处理错误

## 常见问题
| 问题 | 排查 |
| --- | --- |
| Failed to fetch | hooks/debug/Failed-to-fetch排查.md |
| API 请求失败 | hooks/debug/ |
| Token 过期 | 统一在响应拦截器处理 |
