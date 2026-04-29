# Nginx 配置 — L4 实现

## 职责
nginx.conf 配置、反向代理、域名绑定。

## 关键词
nginx、反向代理、404、502、proxy_pass

## nginx 配置位置
- 主配置：/etc/nginx/nginx.conf
- 网站配置：/etc/nginx/sites-available/default
- 启用链接：/etc/nginx/sites-enabled/

## 常用命令

```bash
nginx -t          # 测试配置语法
nginx -s reload   # 重载配置
nginx -s restart  # 重启
```

## 常见问题

| 问题 | 解决 |
| --- | --- |
| 404 | 检查 root 路径、try_files 配置 |
| 502 | upstream 后端未启动或端口错误 |
| 反向代理到 Node | proxy_pass http://localhost:3000 |
