# Lint 检查 — L4 实现

## 职责
ESLint 错误/警告排查和修复。

## 关键词
ESLint、lint、warning、error、prettier

## 常用命令

```bash
npm run lint        # 检查
npm run lint:fix   # 自动修复
```

## 常见错误

| 错误 | 解决 |
| --- | --- |
| no-unused-vars | 变量未使用，加 _ 前缀或删掉 |
| react-hooks/exhaustive-deps | useEffect 依赖数组不完整 |
| import/order | prettier 自动修复 |
| no-explicit-any | 项目已关闭此规则，不需要修 |

## 注意
项目禁用了 no-explicit-any 等规则，遇到这些报错不用修。
