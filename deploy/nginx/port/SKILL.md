# 端口管理 — L4 实现

## 关键词
端口占用、kill、进程、port、Address already in use

## 排查端口占用

```bash
# 查看端口占用
lsof -i :3000
netstat -tlnp | grep 3000

# kill 进程
kill -9 <PID>
```

## 服务器端口
- 阅读回响前端：80/443
- 后端 API：需在 nginx 配置 upstream
