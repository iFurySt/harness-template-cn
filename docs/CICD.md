# CI/CD 说明

这个模板当前不再内置 GitHub Actions CI/CD 骨架。

## 当前状态

- `.github/workflows/` 下没有默认 workflow。
- 仓库不再提供 `make ci`、`scripts/ci.sh` 或 `scripts/release-package.sh`。
- 具体项目落地后，再按真实技术栈补回测试、构建、扫描、发布和部署流水线。

## 设计原则

CI/CD 应该服务真实项目，而不是在模板阶段保留一套无人维护的占位流程。

当新项目的技术栈确定后，优先补一条最小但真实的验证链路，再逐步加入构建产物、供应链扫描、release 和部署。新增 GitHub Actions 时，仍应固定到 commit SHA，避免使用浮动 tag。

## 推荐接入顺序

1. 先定义项目自己的本地验证命令。
2. 添加最小 PR gate，运行真实测试、lint 或 smoke check。
3. 有可交付产物后，再增加打包、SBOM 和 provenance。
4. 技术栈和环境稳定后，再补具体的部署 job。
5. 把所有流水线入口和制品说明同步写回本文件。

## 后续补回时注意

- 不要恢复只有占位意义的 workflow。
- 不要让 `Makefile` 暴露不存在或没人维护的命令。
- 如果引入 release 自动化，同步更新 `docs/SUPPLY_CHAIN_SECURITY.md` 和 `docs/releases/README.md`。
