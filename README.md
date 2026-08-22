# codex-schema

> openai/codex 全部线协议的 TypeScript 类型 + zod 校验器——其余所有仓库的类型地基。

## 吸收来源
- protocol (23,577 行)
- app-server-protocol (30,267)
- exec-server-protocol (1,818)
- code-mode-protocol (4,147)
- history (1,129)
- ext/extension-api (2,346)
- 参考: sdk/typescript 官方 TS 生成物

## 功能边界
**做**：全部线协议 TS 类型；会话 JSONL 格式规格；SSE 流式事件全集（含 RateLimits/ETag 保真，判⑨）。

**不做**：不含任何运行时行为，纯类型与校验。

## API 草图
```
parseRolloutLine(json): Event
AppServerMethod = { thread/start, ... }
```

## 验收标准
解析 100 个真实 codex 会话文件零报错。

## 上游同步
基于 openai/codex@970b7f2ff4f6（Apache-2.0）。季度 diff 由 dsh-codex-ledger CI 触发，见 ledger/coverage.yaml 对应行。
