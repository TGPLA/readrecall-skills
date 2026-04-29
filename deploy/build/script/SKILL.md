# 部署脚本 — L4 实现

## 关键词
部署脚本、自动化、shell、bash、scp、rsync

## 部署命令

```bash
# 构建
npm run build

# 上传到服务器（Windows PowerShell）
scp -r dist\* root@114.132.47.245:/www/sites/readrecall/index/

# 或用 rsync（增量同步）
rsync -avz --delete dist/ root@114.132.47.245:/www/sites/readrecall/index/
```

## 服务器路径
- 远程目录：/www/sites/readrecall/index
- 备份目录：/www/sites/readrecall/backup/
