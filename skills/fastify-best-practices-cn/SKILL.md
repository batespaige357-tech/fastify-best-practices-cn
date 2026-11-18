---
name: fastify-best-practices-cn
description: "中文适配：Fastify 后端、接口、插件与测试。Guides development of Fastify Node.js backend servers and REST APIs using TypeScript or JavaScript. Use when building, configuring, or debugging a Fastify application — including defining routes, implementing plugins, setting up JSON Schema validation, handling errors, optimising performance, managing authentication, configuring CORS and security headers, integrating databases, working with WebSockets, and deploying to production. Covers the full Fastify request lifecycle (hooks, serialization, logging with Pino) and TypeScript integration via strip types. Trigger terms: Fastify, Node.js server, REST API, API routes, backend framework, fastify.config, server.ts, app.ts."
metadata:
  tags: fastify, nodejs, typescript, backend, api, server, http
---

## When to use

Use this skill when you need to:
- Develop backend applications using Fastify
- Implement Fastify plugins and route handlers
- Get guidance on Fastify architecture and patterns
- Use TypeScript with Fastify (strip types)
- Implement testing with Fastify's inject method
- Configure validation, serialization, and error handling

## Quick Start

A minimal, runnable Fastify server to get started immediately:

```ts
import Fastify from 'fastify'

const app = Fastify({ logger: true })

app.get('/health', async (request, reply) => {
  return { status: 'ok' }
})

const start = async () => {
  await app.listen({ port: 3000, host: '0.0.0.0' })
}
start()
```

## Recommended Reading Order for Common Scenarios

- **New to Fastify?** Start with `plugins.md` → `routes.md` → `schemas.md`
- **Adding authentication:** `plugins.md` → `hooks.md` → `authentication.md`
- **Improving performance:** `schemas.md` → `serialization.md` → `performance.md`
- **Setting up testing:** `routes.md` → `testing.md`
- **Going to production:** `logging.md` → `configuration.md` → `deployment.md`

## How to use

Read individual rule files for detailed explanations and code examples:

- [rules/plugins.md](rules/plugins.md) - Plugin development and encapsulation
- [rules/routes.md](rules/routes.md) - Route organization and handlers
- [rules/schemas.md](rules/schemas.md) - JSON Schema validation
- [rules/error-handling.md](rules/error-handling.md) - Error handling patterns
- [rules/hooks.md](rules/hooks.md) - Hooks and request lifecycle
- [rules/authentication.md](rules/authentication.md) - Authentication and authorization
- [rules/testing.md](rules/testing.md) - Testing with inject()
- [rules/performance.md](rules/performance.md) - Performance optimization
- [rules/logging.md](rules/logging.md) - Logging with Pino
- [rules/typescript.md](rules/typescript.md) - TypeScript integration
- [rules/decorators.md](rules/decorators.md) - Decorators and extensions
- [rules/content-type.md](rules/content-type.md) - Content type parsing
- [rules/serialization.md](rules/serialization.md) - Response serialization
- [rules/cors-security.md](rules/cors-security.md) - CORS and security headers
- [rules/websockets.md](rules/websockets.md) - WebSocket support
- [rules/database.md](rules/database.md) - Database integration patterns
- [rules/configuration.md](rules/configuration.md) - Application configuration
- [rules/deployment.md](rules/deployment.md) - Production deployment
- [rules/http-proxy.md](rules/http-proxy.md) - HTTP proxying and reply.from()

## Core Principles

- **Encapsulation**: Fastify's plugin system provides automatic encapsulation
- **Schema-first**: Define schemas for validation and serialization
- **Performance**: Fastify is optimized for speed; use its features correctly
- **Async/await**: All handlers and hooks support async functions
- **Minimal dependencies**: Prefer Fastify's built-in features and official plugins


## 中文任务导航 — fastify-best-practices-cn 新增

上游核心原则和详细规则保留。

### 从中文问题选择规则

先看当前代码、依赖清单与现有运行方式，确认 Fastify、Node.js、TypeScript 版本；不要因为参考采用某个 API，就擅自升级项目或更换模块系统。涉及版本差异时查对应版本的官方文档。

| 用户描述 | 先读 | 再按需要读 |
|---|---|---|
| 加一个接口／拆路由 | [routes](rules/routes.md) | [schemas](rules/schemas.md)、[error-handling](rules/error-handling.md) |
| 插件注册后用不了 | [plugins](rules/plugins.md) | [decorators](rules/decorators.md)、[hooks](rules/hooks.md) |
| 请求校验或返回字段不对 | [schemas](rules/schemas.md) | [serialization](rules/serialization.md)、[content-type](rules/content-type.md) |
| 登录鉴权或跨域问题 | [authentication](rules/authentication.md) | [hooks](rules/hooks.md)、[cors-security](rules/cors-security.md) |
| 给接口写测试 | [testing](rules/testing.md) | [routes](rules/routes.md) |
| 数据库连接／服务退出问题 | [database](rules/database.md) | [configuration](rules/configuration.md)、[deployment](rules/deployment.md) |

按需读相关文件，不为了简单改动加载或执行所有规则。上游无路径的阅读顺序名称都指此技能的 `rules/` 子目录。

### 修改与验证

用中文说明具体改动和原因，保留 API、schema 字段、插件名与原始报错。优先沿用项目结构，限定修改范围，不把局部接口需求扩大成重构整套服务。

验证围绕可观察的请求和响应，使用项目已配置的测试运行方式；参考中的命令不是自动安装依赖或执行所有构建的授权。没运行的测试写明未运行，语法或格式通过不能声称接口行为通过。用户未要求前端编译时，不主动运行前端 build。

本地验证只开放需要的访问范围；上游快速启动代码中的监听地址须结合实际环境和用户意图决定，不为测试擅自暴露外网。鉴权、数据库和部署操作仍依实际授权，不记录敏感凭据。
