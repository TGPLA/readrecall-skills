# 回滚 — L4 实现

## 关键词
回滚、版本恢复、旧版本、rollback、恢复

## 回滚方法

### 文件覆盖回滚
```bash
# 列出备份
ls /www/sites/readrecall/backup/

# 覆盖回滚
cp -r /www/sites/readrecall/backup/v1.x.x/* /www/sites/readrecall/index/
```

### Git 回滚
```bash
cd /www/sites/readrecall && git checkout v1.x.x && npm run build
```

## 回滚检查清单
- [ ] 确认版本号
- [ ] 验证核心功能（书架、阅读）
- [ ] 确认没有破坏数据
