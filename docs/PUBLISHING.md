# 论文发布指南

本仓库用于公开论文稿件及其必要附件。每篇论文独立编号、独立发布版本，所有论文共用一个仓库。

## 目录与编号

首次收录时分配编号，例如 `EL-2026-001`。同一篇论文后续修订、改标题或正式发表时，继续使用该编号。

推荐目录：

```text
2026/EL-2026-001-short-topic/
  README.md
  paper.pdf
  supplements/     # 有必要附件时添加
```

将 [`templates/paper-README.md`](../templates/paper-README.md) 复制为论文目录内的 `README.md`，填入标题、作者、版本与文件说明。该模板是维护用文件，不代表已经发布论文。

正文 PDF 中写清标题、作者、组织或机构信息、版本，以及适用的 AI 使用说明。附件应有名称与用途说明。论文和附件的许可由相应作者确定并写明。

## 发布一个版本

以下命令中的 `EL-2026-001` 仅作示例；发布时使用实际论文编号。

1. 将这一版的完整 PDF、必要附件和论文说明提交到仓库。
2. 在 **Settings → General → Releases** 中确认 **Enable release immutability** 已启用。该设置仅对之后发布的版本生效。
3. 进入 **Releases → Draft a new release**，选择已经包含全部稿件文件的提交，创建唯一标签，例如 `EL-2026-001-v1`。
4. 发布标题使用 `EL-2026-001 v1 — 论文标题`。说明中列出作者、版本、文件清单、适用许可；修订版另列主要改动。
5. 在草稿中上传这一篇论文的完整 PDF 和全部必要附件，再点击 **Publish release**。为附件使用带编号和版本的文件名，例如 `EL-2026-001-v1.pdf`。
6. 确认发布页面出现 **Immutable**，核验附件和发布证明，并保存原始材料。
7. 更新仓库首页目录及论文目录中的链接。首次发布链接保留不变，最新版本链接随修订更新。

将完整 PDF 显式上传为 Release 附件；GitHub 自动生成的源码 ZIP 和 TAR 包不属于 `gh release verify-asset` 支持核验的附件。

同一总仓中，另一篇论文使用 `EL-2026-002-v1`。所有论文各自使用 `v1`、`v2` 等版本序号。

## 核验与留存

使用当前受支持版本的 [GitHub CLI](https://cli.github.com/)，在下载文件的目录运行：

```powershell
gh release verify EL-2026-001-v1 --repo ephodos-lab/papers
gh release verify-asset EL-2026-001-v1 EL-2026-001-v1.pdf --repo ephodos-lab/papers
```

对每个必要附件分别运行 `verify-asset`。查看完整验证结果：

```powershell
gh release verify EL-2026-001-v1 --repo ephodos-lab/papers --format json
```

检查验证结果中的文件校验值、仓库与标签，以及 `verificationResult.verifiedTimestamps`。文件实际匹配和验签成功后，再将该版本登记为已核验。

由维护者另行保存：

- 这一版原始 PDF 和全部附件；
- GitHub 原始 release attestation 签名证明包，以及相应验证所需的信任根材料；
- 完整验证结果与公开发布页面地址。

签名证明可通过发布页面的 **Release attestation (json)** 下载；信任根可由 `gh attestation trusted-root` 导出。单独保存一张“验证成功”的截图，不能替代原始文件和签名证明。完整材料宜另行备份。

这些记录用于核查具体文件、发布来源与时间。论文内容是否正确、是否存在更早成果，仍需依靠数学论证和文献核查。

## 修订、勘误与目录调整

- 修改正文或必要附件：发布 `EL-2026-001-v2`，说明改动，保留 `v1`。
- 修改论文题名：更新当前稿与目录，继续使用原论文编号。
- 移动目录或整理仓库结构：正常提交修改，同时更新首页和当前稿的相对链接。
- 已发布版本的引用：保留指向该 Release 或其附件的链接；目录调整不需要重发同一版本。
- 撤回或发现影响结论的错误：在论文说明和总目录中标明状态，公开说明原因与更正版本。

不可变发布固定那次发布的附件和对应标签。默认分支、目录结构、README 和后续版本可以正常维护。Release 的标题和说明仍可编辑，因此正文中的署名和版本信息、需要固定的附件说明也应放入所发布的文件中。

## 官方参考

- [GitHub 不可变发布](https://docs.github.com/en/code-security/concepts/supply-chain-security/immutable-releases)
- [启用不可变发布](https://docs.github.com/en/code-security/how-tos/secure-your-supply-chain/establish-provenance-and-integrity/prevent-release-changes)
- [核验发布和附件](https://docs.github.com/en/code-security/how-tos/secure-your-supply-chain/secure-your-dependencies/verify-release-integrity)
- [导出信任根材料](https://cli.github.com/manual/gh_attestation_trusted-root)
