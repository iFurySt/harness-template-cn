# 供应链安全

这份文档记录模板当前的供应链安全状态，以及项目落地后应接入的能力。

## 当前状态

当前模板不再内置 GitHub Actions 供应链扫描或 release provenance 流水线。

保留的默认约束是：

- 不提交密钥、令牌或本地私有配置。
- 具体项目落地后，必须提交可审计的依赖清单和 lockfile。
- 后续新增 GitHub Actions 时，应固定到不可变的 commit SHA，而不是漂移的版本标签。

## 后续可接入的工具

- `actions/dependency-review-action`：审查 PR 依赖变更。
- `google/osv-scanner-action`：扫描已知开源漏洞。
- `anchore/sbom-action`：生成 SPDX 格式的 SBOM。
- `actions/attest-build-provenance`：为 release artifact 生成签名 provenance。

## 限制和前提

- Dependency Review 在 public repo 可以直接使用；private repo 通常需要 GitHub Advanced Security 或对应的代码安全能力。
- 当前没有自动化依赖审计、SBOM 或 provenance 产出。
- 供应链能力需要在项目技术栈确定后重新接入。
- OpenSSF Scorecard 默认不启用，因为新模板仓库还没有真实分支保护、release 历史和 SAST 姿态可以评分；等仓库规则配置完成后再按需加回。

## 项目落地后建议继续做的事

- 锁定并提交项目真实依赖的 lockfile。
- 让构建过程尽量可重复、可验证。
- 如果条件允许，在部署链路里增加对 provenance 的校验。
- 把 attestation 校验继续下沉到部署平台或准入层。
