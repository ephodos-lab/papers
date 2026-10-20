<p align="center">
  <a href="https://github.com/ephodos-lab">
    <img src="https://raw.githubusercontent.com/ephodos-lab/.github/main/brand/banner.png" alt="Ephodos Lab" width="800">
  </a>
</p>

# Ephodos Lab Papers

Catalogue and publication records for papers from [Ephodos Lab](https://github.com/ephodos-lab).

Each paper is published in its own repository. Complete manuscripts and essential supplements are released there as immutable GitHub Releases. This catalogue records the authors, repository, versions and publication links.

## Papers

No manuscripts have been released yet.

| Paper ID | Title and authors | Repository | First release | Latest release | Publication / status |
| --- | --- | --- | --- | --- | --- |

Entries are added after a paper's first release has been published and verified. Each entry links to a detailed record under the year it was first catalogued. Later arXiv, DOI and journal links are added to the same record.

## Reading and citing

- Follow the paper's repository link for its current manuscript and discussion.
- Use a release in that repository to download and cite a specific version and its required supplements.
- Cite the authors, full title, paper ID, version and release URL. Use the journal or arXiv reference when appropriate, while retaining a version link when discussing an earlier manuscript.
- Report mathematical errors or manuscript questions in the individual paper's repository. Report catalogue errors through this repository's [Issues](https://github.com/ephodos-lab/papers/issues/new/choose).

## Repository layout

```text
2026/
  README.md                    # annual index
  EL-2026-NNN.md               # one metadata record per paper
docs/
  PUBLISHING.md                # separate-repository publishing guide
templates/
  paper-record.md              # copy into the annual catalogue
  paper-README.md              # copy into an individual paper repository
```

The paper record above is a naming pattern, not a published entry. Manuscripts and supplements belong in the individual paper repositories.

For example, a paper with ID `EL-2026-001` may use the repository `ephodos-lab/paper-2026-001-short-topic`, with releases `v1`, `v2`, and so on. Each paper starts its own version sequence.

## Publishing and corrections

See the [publishing guide](docs/PUBLISHING.md) and [contribution guide](CONTRIBUTING.md).

Each paper repository enables release immutability before its first publication. A revision is published there as a new release, then its catalogue record is updated. The first-release link is retained.

This catalogue does not publish manuscript releases. Its records and directory structure can be maintained independently of the paper repositories.

## Authors and reuse

Authors, affiliations and any AI use are stated in each manuscript. Catalogue metadata should agree with the released manuscript.

Reuse terms are stated in each paper repository and, where necessary, separately for its supplements. Listing a paper here does not change those terms.

<details>
<summary><b>中文说明</b></summary>

本仓库是 Ephodos Lab 的论文总索引，只保存论文记录和链接。

- 每篇论文一个独立仓库，完整稿件和必要附件放在该论文仓库中。
- 各论文仓库分别启用不可变 Release，使用自己的 `v1`、`v2` 等版本标签。
- 总索引记录论文编号、作者、独立仓库、首次发布、最新版本，以及 arXiv、DOI、期刊信息。
- 修订稿在论文仓库发布新版本后，同步更新总索引；首次发布链接保留。
- 数学内容的勘误与讨论放在对应论文仓库；总索引的问题在本仓库反馈。

目前尚无已发布论文。添加稿件和发布版本的方法见[发布指南](docs/PUBLISHING.md)。

</details>
