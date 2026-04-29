# 阅读回响 — L1 任务识别与路由入口

## 职责
收到任何开发需求后，**第一步**判断任务属于哪个领域，立即加载对应 L2 skill。

---

## 快速任务匹配 GT

> 匹配关键词 → 加载对应 L2 → L2 路由到 L3/L4

### 前端开发（React / 组件 / 样式）

| 关键词 | L2 → L3 → L4 |
| --- | --- |
| 组件/按钮/弹窗/抽屉/表单 | frontend/components/ → modal/drawer/form/ |
| Select/分页/Card/Table | frontend/components/ → card/ |
| Tailwind/CSS/深色/响应式 | frontend/components/ → style/ |
| SEO/页面标题/document.title | frontend/components/ → page/ |
| useState/useEffect/useCallback | frontend/hooks/ → debug/ |
| API请求/axios/权限/Token | frontend/hooks/ → useFetch/ |
| Failed to fetch/网络错误 | frontend/hooks/ → debug/ |
| localStorage/持久化 | frontend/state/ → localStorage/ |
| Context/全局状态 | frontend/state/ → context/ |

### EPUB 阅读器

| 关键词 | L2 → L3 → L4 |
| --- | --- |
| 翻页不动/下一页不响应 | epub/reader/ → page-turning/ |
| 进度条/CFI/位置不保存 | epub/reader/ → progress/ |
| 布局/面板/侧边栏 | epub/reader/ → layout/ |
| 目录为空/章节href错误 | epub/parsing/ → toc/ |
| 封面黑屏/封面不显示 | epub/parsing/ → cover/ |
| 书名/作者/元数据为空 | epub/parsing/ → metadata/ |
| 划词/选中文本/弹出菜单 | epub/highlight/ → selection/ |
| 划线颜色/笔记/CFI不稳定 | epub/highlight/ → note/ |

### 测试

| 关键词 | L2 → L3 → L4 |
| --- | --- |
| vitest/单元测试/组件测试 | testing/unit/ → mock/ 或 assertion/ |
| mock/vi.fn()/vi.mock | testing/unit/ → mock/ |
| expect/断言/toBe/toEqual | testing/unit/ → assertion/ |
| 测试失败/AssertionError | testing/unit/ → debug/ |
| playwright/e2e/UI测试 | testing/e2e/ → selector/ |
| 选择器找不到/not found | testing/e2e/ → selector/ |
| flaky/超时/调试 | testing/e2e/ → debug/ |
| CI/GitHub Actions | testing/e2e/ → ci/ |

### 部署运维

| 关键词 | L2 → L3 → L4 |
| --- | --- |
| 构建失败/Vite报错 | deploy/build/ → vite/ |
| ESLint/warning/error | deploy/build/ → lint/ |
| 部署脚本/自动化/scp | deploy/build/ → script/ |
| nginx/反向代理/404/502 | deploy/nginx/ → config/ |
| 端口占用/kill进程 | deploy/nginx/ → port/ |
| SSL/HTTPS/证书 | deploy/ssl/ |
| GitHub Actions/CI/CD | deploy/ci/ → github-actions/ |
| 回滚/版本恢复 | deploy/rollback/ |

### 工具类（按需加载）

| 关键词 | L2 |
| --- | --- |
| 任务拆解/复杂需求/路线图 | 任务拆解/SKILL.md |
| Todo/待办/任务列表 | Todo管理/SKILL.md |
| 浏览器控制台/调试/报错 | 控制台检查/SKILL.md |
| GitHub参考/借鉴项目 | 问题自救/SKILL.md |
| 头脑风暴/发散思考 | 头脑风暴/SKILL.md |
| 失败总结/复盘 | 失败复盘存档/SKILL.md |

---

## L2 领域清单

| L2 | 路径 | 说明 |
| --- | --- | --- |
| 前端开发 | frontend/ | React 组件、Hooks、状态 |
| EPUB 阅读器 | epub/ | 阅读器、解析、划线 |
| 测试 | testing/ | 单元测试、E2E、CI |
| 部署运维 | deploy/ | 构建、nginx、CI/CD、回滚 |

---

## 执行流程

1. **接收需求** — 理解用户想做什么
2. **匹配关键词** — 看需求中包含哪些技术词
3. **加载对应 L2** — 立即加载对应领域的 SKILL.md
4. **L2 引导 L3** — L2 的 GT 表路由到 L3
5. **L3 引导 L4** — L3 的子目录路由到 L4
6. **L4 是最终执行依据**

---

## 注意

- **多领域任务**：如果一个需求涉及多个领域，按顺序加载所有相关 L2
- **不确定时**：优先加载 frontend + epub 两个 L2
- **L4 文件是最终执行依据**，L1/L2/L3 都是导航作用
