# Chrome DevTools MCP 配置

> **项目**: Chrome DevTools MCP Server by Google
> **仓库**: https://github.com/ChromeDevTools/chrome-devtools-mcp

## 项目概述

Model Context Protocol (MCP) 服务器，让 AI 编码助手（如 Gemini、Claude、Cursor、Copilot）能够控制和检查 Chrome 浏览器。

**核心功能**:
- 性能分析：使用 Chrome DevTools 录制 trace 并提取性能洞察
- 高级调试：分析网络请求、截图、检查控制台
- 可靠自动化：基于 Puppeteer 自动化浏览器操作

## 技术栈

| 技术 | 版本 | 用途 |
|------|------|------|
| Node.js | ^20.19.0 || ^22.12.0 || >=23 | 运行时 |
| TypeScript | ^5.9.2 | 主要语言 |
| Puppeteer | 24.36.1 | 浏览器自动化 |
| chrome-devtools-frontend | 1.0.1576915 | DevTools 集成 |
| Rollup | 4.57.1 | 打包 |
| MCP SDK | 1.25.3 | 协议实现 |

## 项目结构

```
chrome-devtools-mcp/
├── src/                 # TypeScript 源代码
├── build/              # 编译输出
├── tests/              # 测试
├── scripts/            # 构建脚本
├── docs/               # 文档
├── .claude-plugin/     # MCP 插件配置
└── skills/             # 技能定义
```

## 开发规范

### 命令
- `npm run build` - 编译 TypeScript
- `npm run typecheck` - 类型检查
- `npm run format` - 格式化 (ESLint + Prettier)
- `npm test` - 运行测试
- `npm run bundle` - 打包分发

### 代码风格
- ESLint 配置：`eslint.config.mjs`
- Prettier 配置：`.prettierrc.cjs`
- 使用 TypeScript strict mode
- 遵循 Google 开源风格

### 关键文件
- `src/index.ts` - MCP 服务器入口
- `package.json` - 包含 `server.json` 路径
- `server.json` - MCP 服务器元数据

## 开发注意事项

1. **MCP 协议**: 所有工具必须遵循 MCP SDK 规范
2. **浏览器会话**: 确保正确管理 Chrome 实例生命周期
3. **异步处理**: 大量使用 async/await 处理 Puppeteer 操作
4. **错误处理**: 提供清晰的错误消息给 AI 客户端

## 相关文档

- [工具参考](./docs/tool-reference.md)
- [设计原则](./docs/design-principles.md)
- [故障排除](./docs/troubleshooting.md)
- [贡献指南](./CONTRIBUTING.md)

---

## 资源索引

详见 `.claude/index.json`

## 历史记录

详见 `.claude/completed.md`

## 当前任务

详见 `.claude/in-progress.md`
