# 部署运维 — L2 领域 Skill

## 职责
构建、部署、环境配置相关的任务，优先加载此文件做任务路由。

---

## 快速任务匹配 GT

| 关键词示例 | 加载 L3 | L4 路径 |
| --- | --- | --- |
| 构建失败/build报错/dist | deploy/build/ | build/vite/ |
| ESLint/warning/error | deploy/build/ | build/lint/ |
| nginx配置/反向代理/404 | deploy/nginx/ | nginx/config/ |
| SSL证书/HTTPS/证书过期 | deploy/ssl/ | ssl/ |
| GitHub Actions/CI/CD/pipeline | deploy/ci/ | ci/github-actions/ |
| 回滚/版本恢复/旧版本 | deploy/rollback/ | rollback/ |
| 部署脚本/自动化部署 | deploy/build/ | build/script/ |
| 端口占用/进程 kill | deploy/nginx/ | nginx/port/ |

---

## 服务器信息

- IP: 114.132.47.245
- 用户: root
- 网站目录: /www/sites/readrecall/index
- 域名: linyubo.top

---

## 本领域 L3 模块清单

| L3 模块 | 路径 | 何时使用 |
| --- | --- | --- |
| 构建 | deploy/build/ | build / lint / 脚本 |
| Nginx | deploy/nginx/ | 配置 / 端口 / 反向代理 |
| SSL | deploy/ssl/ | 证书配置 / 续期 |
| CI/CD | deploy/ci/ | GitHub Actions / 流水线 |
| 回滚 | deploy/rollback/ | 版本恢复 |
