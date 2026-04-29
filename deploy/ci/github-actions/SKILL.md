# GitHub Actions — L4 实现

## 关键词
GitHub Actions、CI/CD、pipeline、workflow、.github/workflows

## workflow 存放位置
.github/workflows/

## workflow 示例

```yaml
name: Build and Deploy
on: [push]
jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - uses: actions/setup-node@v4
        with:
          node-version: '20'
          cache: 'npm'
      - run: npm ci
      - run: npm run build
      - run: npm run lint
```

## 部署到腾讯云
```yaml
- name: Deploy to Server
  run: scp -r dist/* root@114.132.47.245:/www/sites/readrecall/index/
  env:
    SSH_KEY: ${{ secrets.SERVER_SSH_KEY }}
```
