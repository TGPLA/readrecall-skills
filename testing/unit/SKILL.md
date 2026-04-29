# 单元测试 — L3 模块 Skill

## 职责
Vitest 单元测试的编写和修复。

## 快速路由

| 关键词 | 加载 L4 |
| --- | --- |
| mock、spy、vi.fn() | `unit/mock/` |
| expect、断言、toBe | `unit/assertion/` |
| 测试不通过/失败/报错 | `unit/debug/` |

---

## 测试目录

| 路径 | 内容 |
| --- | --- |
| `src/shared/services/*.test.ts` | Service 单元测试 |
| `src/shared/services/*.integration.test.ts` | 集成测试 |
| `tests/` | Playwright E2E |

## 运行命令

```bash
npm run test          # watch 模式
npm run test:run      # 单次运行
```

## 测试规范

```typescript
import { describe, it, expect } from 'vitest';

describe('authService', () => {
  it('should return error for invalid credentials', async () => {
    const result = await authService.login('wrong', 'wrong');
    expect(result.error).toBeTruthy();
  });
});
```

## 注意事项
- 测试文件名：`xxx.test.ts`
- 一个 test 文件对应一个 source 文件
- 集成测试后缀：`xxx.integration.test.ts`
