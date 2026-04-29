# SSL 证书 — L4 实现

## 职责
HTTPS 配置、证书续期、Let's Encrypt。

## 关键词
SSL、HTTPS、证书、Let's Encrypt、https、certificate

## 证书路径
- Let's Encrypt：/etc/letsencrypt/live/linyubo.top/
- certbot：/etc/nginx/sites-enabled/

## 续期命令

```bash
certbot renew --dry-run    # 测试续期
certbot renew              # 实际续期
```

## 自动续期
certbot 有 cronjob，会自动续期。
