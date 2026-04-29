# 元数据解析 — L4 实现

## 职责
书名、作者、出版社、语言等元数据的提取。

## 关键词
元数据、metadata、书名、作者、解析

## 解析流程
1. `jszip` 解压 EPUB 文件
2. 读取 `META-INF/container.xml` 获取 OPF 路径
3. 解析 OPF 的 `<metadata>` 标签

## OPF metadata 结构
```xml
<metadata xmlns:dc="http://purl.org/dc/elements/1.1/">
  <dc:title>书名</dc:title>
  <dc:creator>作者</dc:creator>
  <dc:language>zh-CN</dc:language>
</metadata>
```

## 常见问题
| 问题 | 原因 |
| --- | --- |
| 书名为空 | OPF 命名空间不匹配 |
| 作者为空 | 多个 creator 标签只取第一个 |
