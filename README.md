# Fastify Best Practices CN

**用中文描述后端问题，按需找到 Fastify 实现规则。**

基于 [mcollina/skills 的 fastify-best-practices](https://github.com/mcollina/skills/tree/main/skills/fastify) 的小幅中文适配。独立维护、非官方。

## 保留什么

上游入口正文和19份规则原样保留：插件、路由、schema、错误、hooks、鉴权、测试、性能、日志、TypeScript、数据库、部署等。保留封装、schema优先和最小依赖的原则。

## 小幅补充

- 中文需求到相关规则文件的阅读导航，减少盲目加载整套材料。
- 先确认项目版本与结构，再套用对应 API，不擅自升级框架。
- 中文解释改动，代码字段和报错保持原文；区分静态检查与接口行为验证。
- 本地测试的监听范围、数据库与部署动作仍由任务授权决定。

## 安装与调用

```bash
npx skills add batespaige357-tech/fastify-best-practices-cn --skill fastify-best-practices-cn
```

对助手说“用 fastify-best-practices-cn 实现这个接口，沿用项目现有结构”；Codex 可用 `$fastify-best-practices-cn`。也可复制 `skills/fastify-best-practices-cn` 整个目录到助手支持的技能目录，保留 rules 子目录。

这是开发规则包，不自带 Fastify 服务或依赖。具体实现需要目标项目的 Node.js、Fastify 与测试环境，版本以项目为准。不全局安装技能，不自动启动服务，不附示例网页、截图或前后对比。

## 来源与验证

MIT，保留 Matteo Collina 版权和完整许可。[CHANGES.md](CHANGES.md) 记录来源提交与改动。

已检查原正文及19份规则完整保留、UTF-8、相对引用和技能格式。未进行真实助手行为评估或 Fastify 服务运行测试，没有性能提升成绩；未运行前端编译。
