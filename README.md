# optimizedTokenSkill

一个为 Codex 设计的轻量级 skill，用于在不牺牲精准性、执行效率和工程质量的前提下，尽量减少 token 消耗。

## 项目简介

`optimizedTokenSkill` 是一个面向 Codex / AI coding agent 的实用 skill，核心目标是：

- 减少无效的上下文读取
- 降低冗长输出带来的 token 消耗
- 保持任务完成率、正确性和验证质量

它不是一个“少说话”的模板，而是一套约束模型工作方式的规则：

- 小范围读取，按需扩展
- 少复述，少预加载，少重复总结
- 小任务优先直接执行
- 最终回答聚焦结果、验证和风险

## 适用场景

这个 skill 适合下面这些场景：

- Codex 日常开发
- bug 修复
- 小到中等规模功能实现
- 代码审查
- 定向排查仓库问题
- 希望节省 token 成本的 AI 编程工作流

## 关键词

为了便于 GitHub 搜索和理解，这个项目主要覆盖这些关键词：

`Codex` `skill` `token optimization` `prompt engineering` `AI coding` `developer productivity` `context efficiency` `LLM workflow`

## 仓库内容

当前 skill 位于子目录：

- [precision-with-low-token-cost](./precision-with-low-token-cost)

该目录包含：

- [SKILL.md](./precision-with-low-token-cost/SKILL.md)：skill 定义
- [README.md](./precision-with-low-token-cost/README.md)：详细介绍
- [USAGE.md](./precision-with-low-token-cost/USAGE.md)：使用示例

## 快速使用

将 skill 目录复制到你的 Codex skills 路径中，例如：

```bash
cp -R precision-with-low-token-cost ~/.agents/skills/
```

然后在提示词中显式引用：

```text
Use the precision-with-low-token-cost skill.
```

## 这个 Skill 的核心价值

它希望解决的不是“回答太长”这个表面问题，而是 AI 编程助手在实际工作中常见的 token 浪费问题，比如：

- 过早读取大量无关文件
- 反复复述用户需求
- 输出很多低信息密度的进度说明
- 小改动也走很长的解释链路

这个 skill 会让 Codex 更像一个克制、直接、可靠的工程助手。

## 详细文档

更完整的说明请查看：

- [详细 README](./precision-with-low-token-cost/README.md)
- [使用文档](./precision-with-low-token-cost/USAGE.md)
