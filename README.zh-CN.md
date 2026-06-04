# Frontend Skills Compare

[![Author](https://img.shields.io/badge/Author-Guochen%20Wang-blue)](https://github.com/u7663394)
[![GitHub](https://img.shields.io/badge/GitHub-u7663394%20(Guochen%20Wang)-black?logo=github)](https://github.com/u7663394)
[![Email](https://img.shields.io/badge/Email-guochenwang710%40gmail.com-red)](mailto:guochenwang710@gmail.com)

<p align="right">
  语言：<a href="./README.md">English</a> | 简体中文
</p>

本仓库用于在同一产品需求下，对比多个面向前端开发的 skill 的生成效果。每个实现都是一个 Vue 3 + TypeScript 个人介绍主页，内容灵感来自 [u7663394 的 GitHub 主页](https://github.com/u7663394)。

## 统一提示词

> Create a Vue 3 + TypeScript personal introduction homepage. Use the content inspiration from this GitHub profile: https://github.com/u7663394.

## 对比的 Skill

| Skill | 来源 | 输出目录 |
| --- | --- | --- |
| Design Taste Frontend | [Leonxlnx/taste-skill](https://github.com/Leonxlnx/taste-skill) | `Design-Taste-Frontend/` |
| Frontend Skill | [openai/skills](https://github.com/openai/skills)，由 OpenAI Codex 提供 | `Frontend-Skill/` |
| Impeccable | [pbakaus/impeccable](https://github.com/pbakaus/impeccable) | `Impeccable/` |
| Web Design Engineer | [ConardLi/garden-skills](https://github.com/ConardLi/garden-skills/tree/main/skills/web-design-engineer) | `Web-Design-Engineer/` |

## 运行方式

每个示例都是独立的 Vite 项目。进入想查看的目录，按需安装依赖，然后启动开发服务器：

```bash
cd Design-Taste-Frontend
npm install
npm run dev
```

其他输出目录也使用同样的运行方式。

## 评估说明

前端设计审美非常主观，而且即使使用相同提示词，agent 每次生成的结果也可能存在明显随机性。下面的结论只代表我在这次对比中的个人感受，并不表示这些 skill 本身的客观优劣。

- 测试 agent：Codex, GPT 5.5 High
- 个人感受：Web Design Engineer ≈ Design Taste Frontend > Impeccable > Frontend Skill
