# 封面提取 — L4 实现

## 关键词
封面不显示、封面提取、FengMian、cover

## 封面来源优先级
1. OPF `<meta name="cover">` 指向的图片
2. manifest 中 id 含 "cover" 的 item
3. 目录第一张图片

## 提取逻辑
```typescript
// 1. 找 cover meta
const coverMeta = manifest.find(item => 
  item.properties?.includes('cover-image')
);
// 2. 从 jszip 读取图片 blob
const coverBlob = await zip.file(coverItem.href).async('blob');
// 3. 转成 URL
const coverUrl = URL.createObjectURL(coverBlob);
```

## 常见问题
| 问题 | 原因 |
| --- | --- |
| 封面黑屏 | 图片路径错误或跨域 |
| 封面拉伸 | 图片比例和容器不匹配 |
