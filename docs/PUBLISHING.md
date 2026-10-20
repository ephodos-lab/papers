# 论文分仓发布与总索引指南

每篇论文使用一个独立仓库，公开完整稿件及必要附件，并在该论文仓库发布不可变 Release。`ephodos-lab/papers` 只维护论文记录、版本链接和发表信息。

## 论文编号与仓库

首次收录时分配编号，例如 `EL-2026-001`。同一篇论文后续修订、改标题或正式发表时，继续使用该编号。

为论文在 `ephodos-lab` 组织下创建独立公开仓库。建议名称为 `paper-2026-001-short-topic`，其中 `short-topic` 替换为题目的简短英文描述。这里的编号和仓库名只是示例，不代表已有论文或仓库。

论文仓库的推荐结构：

```text
README.md
paper.pdf
supplements/     # 有必要附件时添加
```

将 [`templates/paper-README.md`](../templates/paper-README.md) 复制为该论文仓库的 `README.md`，填入标题、作者、文件说明、版本与许可。

正文 PDF 中写清标题、作者、组织或机构信息、版本，以及适用的 AI 使用说明。附件应有名称与用途说明。论文和附件的许可由相应作者确定并写明。

## 在论文仓库发布版本

下面以 `ephodos-lab/paper-2026-001-short-topic` 为例，实际操作时替换为该论文的真实仓库名。

1. 将完整 PDF、必要附件和论文说明提交到该论文仓库。
2. 在**该论文仓库**的 **Settings → General → Releases** 中启用 **Enable release immutability**。每个新论文仓库都要分别确认，索引仓库的设置不会自动应用到其他仓库。
3. 进入该论文仓库的 **Releases → Draft a new release**，选择已经包含本版稿件文件的提交，创建标签 `v1`。后续修订使用 `v2`、`v3` 等新标签。
4. 发布标题使用 `EL-2026-001 v1 — 论文标题`。说明中列出作者、版本、文件清单、适用许可；修订版另列主要改动。
5. 在草稿中上传这一版的完整 PDF 和全部必要附件，再点击 **Publish release**。为附件使用带论文编号和版本的文件名，例如 `EL-2026-001-v1.pdf`。
6. 确认发布页面显示 **Immutable**，核验发布证明和全部必要附件，并留存原始材料。
7. 核验完成后，在总索引登记该论文和版本。

不同论文分别在各自仓库使用 `v1`、`v2`。这些标签属于不同仓库，不会互相冲突。

将完整 PDF 显式上传为 Release 附件；GitHub 自动生成的源码 ZIP 和 TAR 包不属于 `gh release verify-asset` 支持核验的附件。

## 核验与留存

使用当前受支持版本的 [GitHub CLI](https://cli.github.com/)，在下载文件的目录运行以下命令，将示例仓库名替换为真实仓库名：

```powershell
gh release verify v1 --repo ephodos-lab/paper-2026-001-short-topic
gh release verify-asset v1 EL-2026-001-v1.pdf --repo ephodos-lab/paper-2026-001-short-topic
gh release verify v1 --repo ephodos-lab/paper-2026-001-short-topic --format json
```

对每个必要附件分别运行 `verify-asset`。检查文件校验值、仓库、标签，以及 `verificationResult.verifiedTimestamps`。文件匹配和验签成功后，再将该版本登记为已核验。

由维护者另行保存：

- 这一版原始 PDF 和全部附件；
- GitHub 原始 release attestation 签名证明包，以及相应验证所需的信任根材料；
- 完整验证结果与公开发布页面地址。

签名证明可通过发布页面的 **Release attestation (json)** 下载；信任根可由 `gh attestation trusted-root` 导出。单独保存一张“验证成功”的截图，不能替代原始文件和签名证明。完整材料宜另行备份。

这些记录用于核查具体文件、发布来源与时间。论文内容是否正确、是否存在更早成果，仍需依靠数学论证和文献核查。

## 登记总索引

总索引只保存元数据，不上传稿件或附件：

```text
ephodos-lab/papers
  README.md                  # 全部论文的总目录
  2026/
    README.md                # 年度索引
    EL-2026-001.md            # 单篇论文记录
```

1. 将 [`templates/paper-record.md`](../templates/paper-record.md) 复制为 `2026/EL-2026-001.md`，使用真实年份与编号。
2. 填入标题、作者、独立仓库、首次 GitHub Release、最新版本、摘要和发表状态。如果此前已在其他地方公开，另行记录较早版本及其链接。
3. 发布日期使用 GitHub 的实际 `published_at`，按 UTC 记录。只有实际核验完成后，才填写已核验状态。
4. 更新总仓 `README.md` 与对应年份 `README.md` 的目录表格，论文编号链接到单篇记录。
5. 在论文仓库的 `README.md` 中补上该总索引记录的链接。

只有已经实际发布并核验的论文才加入公开目录。模板中的示例与占位文字不作为论文记录。

## 修订、勘误与维护

- 修改正文或必要附件：在原论文仓库发布 `v2` 等新版本，说明改动并保留 `v1`；同步更新总索引的最新版本与版本历史，保留首次发布链接。
- 论文改标题或正式发表：更新论文仓库及总索引的元数据，继续使用原论文编号。
- 数学内容的勘误与问题：在对应论文仓库处理，注明具体版本和位置。
- 索引信息有误或链接失效：在 `ephodos-lab/papers` 修正。
- 撤回或发现影响结论的错误：在论文仓库及总索引标明状态，说明原因与更正版本。
- 调整目录：正常提交修改并更新相关链接；旧 Release 的附件和标签保持固定。

不可变发布固定那次发布的附件和对应标签。各仓库的默认分支、目录、README 和后续版本可以正常维护。Release 的标题和说明仍可编辑，因此署名、版本和需要固定的说明也应放入所发布的文件中。

## 官方参考

- [GitHub 不可变发布](https://docs.github.com/en/code-security/concepts/supply-chain-security/immutable-releases)
- [启用不可变发布](https://docs.github.com/en/code-security/how-tos/secure-your-supply-chain/establish-provenance-and-integrity/prevent-release-changes)
- [核验发布和附件](https://docs.github.com/en/code-security/how-tos/secure-your-supply-chain/secure-your-dependencies/verify-release-integrity)
- [导出信任根材料](https://cli.github.com/manual/gh_attestation_trusted-root)
