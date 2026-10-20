<p align="center">
  <a href="https://github.com/ephodos-lab">
    <img src="https://raw.githubusercontent.com/ephodos-lab/.github/main/brand/banner.png" alt="Ephodos Lab" width="800">
  </a>
</p>

# Ephodos Lab Papers

Research manuscripts and essential supplementary materials from [Ephodos Lab](https://github.com/ephodos-lab).

Each paper has its own directory, identifier and version history. Published versions are available as immutable [GitHub Releases](https://github.com/ephodos-lab/papers/releases).

## Papers

No manuscripts have been released yet.

| Paper ID | Title and authors | First release | Latest release | Publication |
| --- | --- | --- | --- | --- |

Entries are added when the first version of a paper is released. Later arXiv, DOI and journal links are added to the same entry.

## Reading and citing

- Use a paper's release page to download a specific version and its required supplements.
- The default branch contains the current working files; they may change between releases.
- Cite the authors, full title, paper ID, version and release URL. Use the journal or arXiv reference when appropriate, while retaining a version link when discussing an earlier manuscript.
- Report an error or ask a question through [Issues](https://github.com/ephodos-lab/papers/issues/new/choose), identifying the paper and version.

## Repository layout

```text
2026/
  EL-2026-NNN-short-topic/
    README.md
    paper.pdf
    supplements/               # when required by the paper
docs/
  PUBLISHING.md                # publication and verification guide
templates/
  paper-README.md              # copy into a new paper directory
```

The example directory above is a naming pattern, not a published paper. Source files may be included when they form part of the release.

Release tags include the paper ID: `EL-2026-NNN-v1`, `EL-2026-NNN-v2`, and so on. A new paper starts its own sequence.

## Publishing and corrections

See the [publishing guide](docs/PUBLISHING.md) and [contribution guide](CONTRIBUTING.md).

Repository directories and working files can be reorganized after publication. An immutable release keeps that version's attached files and its tag fixed; a correction is published as a new version.

## Authors and reuse

Authors, affiliations and any AI use are stated in each manuscript. Hosting a paper under this organization does not replace the paper's authorship statement.

Reuse terms are stated for each paper and, where necessary, separately for its supplements. This repository does not apply one blanket software license to all manuscripts.

<details>
<summary><b>中文说明</b></summary>

本仓库集中公开 Ephodos Lab 的论文稿件及必要附件。

- 每篇论文一个目录，使用独立编号；目录中的文件可以继续修改和整理。
- 正式版本以不可变 Release 发布。下载、引用或讨论某个版本时，请链接到对应的 Release。
- 修订稿发布为同一论文的下一版本，并保留先前发布的文件。
- 首次公开版本与后续 arXiv、DOI、期刊信息分别记录。

目前尚无已发布论文。添加稿件和发布版本的方法见[发布指南](docs/PUBLISHING.md)。

</details>
