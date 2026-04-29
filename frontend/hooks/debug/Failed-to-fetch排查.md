# Failed to fetch 排查指南

## 常见原因

1. CORS 跨域 — 后端未配置允许前端域名
2. 网络请求被拦截 — 浏览器插件/代理
3. 后端服务未启动 — 检查服务器端口
4. URL 错误 — 路径拼写错误
5. HTTPS → HTTP — 混合内容被阻止

## 排查步骤

1. 打开 DevTools → Network，检查请求状态码
2. 查看 Console 有无 CORS 错误
3. 确认后端 API 地址是否可访问
4. 检查请求方法（GET/POST）和 headers
