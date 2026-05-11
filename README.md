# harness-template-cn

English version: [`harness-template`](https://github.com/iFurySt/harness-template)

## 简介

一个面向 Agent 协作开发的基础仓库模板，可以用来启动任何你想做的产品或服务。

## 快速开始

可以在这个仓库右上角直接使用 GitHub 的模板流程：

1. 选择 **Use this template**。
2. 选择 [**Create a new repository**](https://github.com/new?template_name=harness-template-cn&template_owner=iFurySt)。

也可以在新仓库或已有仓库里用 [`harness-cli`](https://github.com/iFurySt/harness-cli) 初始化。先通过 npm 安装：

```sh
npm install -g @ifuryst/harness-cli
```

然后运行：

```sh
harness-cli init --language zh
```

`harness-cli` 需要 Node.js 18+，并且本机 `PATH` 中需要有 Go。

## 你会得到什么

- 通过 `AGENTS.md` 和 `CLAUDE.md` 提供的 Agent 入口。
- 覆盖架构、产品判断、前端、可靠性、安全、CI/CD 和供应链安全的仓库内文档骨架。
- 位于 `docs/` 下的 execution plan、change history、release note 和 reference docs 骨架。
- 默认 CI、release 和供应链安全 workflow，并且 GitHub Actions 已固定到 commit SHA。
- 用于仓库检查、history、plan 和模板初始化的轻量脚本与 `make` 命令。

## 前 10 分钟建议

1. 先替换 `CODEOWNERS`、`docs/ARCHITECTURE.md`、`docs/product-specs/` 等模板占位内容。
2. 运行 `make ci`，并把它作为 Agent 发 PR 前默认要跑的基线命令。
3. 先补第一个真实产品流程和验收标准，再开始扩展实现。
4. 更新 `docs/QUALITY_SCORE.md`，把新项目最薄弱的地方写清楚，方便后续任务接上。

## 许可证

[MIT](LICENSE)

## 备注

这套方法主要来自我们自己的持续实践和整理，同时也吸收了 OpenAI 在 [harness engineering 文章](https://openai.com/index/harness-engineering/) 中的一部分思路，最后汇总成了这个模板。
