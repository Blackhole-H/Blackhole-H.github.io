# 待补充资料清单

本文件列出网站上**因为缺少可靠资料而被隐藏或降级处理**的内容。
所有已上线内容都来自你提供的 `profile.md`、三篇论文 PDF，或已核验的 arXiv 页面。
下面每一项都写明：缺什么 → 现在网站怎么处理 → 补上后怎么改。

---

## A. 论文的发表状态（最重要）

三篇论文的**题目、作者、年份、arXiv 编号、DOI** 都已逐项对照 arXiv 官方页面核验过：

| 论文 | arXiv | 核验结果 |
| --- | --- | --- |
| SpikeSTAG: A Dendritic Compartmental Spiking Graph Network for Multivariate Time-Series Forecasting | 2508.02069 | Accepted at NeurIPS 2026 |
| QuantaSpike: Short-Window Spike-Driven Quantization for Large Language Models | 2609.34259 | 2026-09-28 提交 |
| SpikeLite: Lightweight Spiking Neural Networks for Time-Series Forecasting | 2609.35097 | 2026-09-28 提交 |

**但 arXiv 页面上没有任何会议/期刊收录信息**，因此网站目前统一按
`arXiv preprint` 展示（左侧 `arXiv` 徽章 + 年份 + arXiv 链接），
**没有标注任何 Accepted / Published 状态，也没有写投稿中的会议名**。

待你确认的信息（来自你之前提供的「内容核验记录」，但本次 `profile.md` 的
Venue / Status 字段留空，且这些信息无法从公开页面核实，所以暂未上线）：

- [ ] SpikeSTAG 是否已正式被 **NeurIPS 2026** 接收？
- [ ] QuantaSpike / SpikeLite 是否处于 **ICLR 2027 投稿中**？

> 提醒：把「投稿中」连同会议名写在公开主页上，可能被认为违反双盲评审的匿名要求。
> 如果确实想展示，建议只用 `Under review` 而不写会议名，或等录用后再写。

确认后怎么改 —— 编辑 `_bibliography/papers.bib` 对应条目：

```bibtex
@article{hu2026spikelite,
  abbr   = {ICLR},          % 左侧徽章文字，同时在 _data/venues.yml 里加同名条目可变成链接
  ...
}
```

已录用则再加会议字段，例如：

```bibtex
  booktitle = {International Conference on Learning Representations (ICLR)},
  year      = {2027},
```

---

## B. 论文相关链接

| 资料 | 现状 | 补上后 |
| --- | --- | --- |
| 论文 PDF | 未提供 → 不显示 PDF 按钮 | 放到 `assets/pdf/`，bib 里加 `pdf = {xxx.pdf}` |
| 代码仓库 | 未提供 → 不显示 Code 按钮 | bib 里加 `code = {https://github.com/...}` |
| 项目主页 | 未提供 → 不显示 Project 按钮 | bib 里加 `website = {https://...}` |
| 真实方法图 | ✅ 已上线（你上传的 3 张 PDF 框架图已渲染为 PNG 替换占位卡片） | 如需换图，替换 `assets/img/publication_preview/` 下同名 PNG |

> ~~三条占位缩略图~~ 已于 2026-10-10 全部替换为真实论文方法图
> （来源：仓库 `assets/img/publication_preview/*.pdf`，160 dpi 渲染）。

---

## C. 个人信息

| 字段 | 现状 | 需要补充 |
| --- | --- | --- |
| 姓名 / 职位 / 学院 / 学校 | ✅ 已上线（Bang Hu, PhD Student, 复旦大学计算机科学与人工智能学院） | — |
| 学术邮箱 | ✅ 已上线 `hub24@m.fudan.edu.cn` | 如需换成 `blackholeban@gmail.com` 或同时显示，改 `_data/socials.yml` |
| GitHub | ✅ 已上线 `Blackhole-H` | — |
| ORCID | ✅ 已上线 `0009-0005-4274-7588` | — |
| **Google Scholar** | ❌ 未提供 ID → 不显示 Scholar 按钮 | 把 Scholar 主页 URL 里 `user=XXXXXXXXXXX` 的值填进 `_data/socials.yml` 的 `scholar_userid` |
| **头像照片** | ✅ 已上线（你上传的真实照片，1278×1706） | 如需更换，替换 `assets/img/prof_pic.jpg` |
| 办公室地址 / 通讯地址 | ❌ 未提供 → 首页头像下不显示 | `_pages/about.md` 的 `profile.more_info` |
| LinkedIn / X 等 | ❌ 未提供 → 不显示 | `_data/socials.yml` |

---

## D. CV

`profile.md` 里 Education、Selected Honors、Academic Service 均为空，也没有 CV PDF。

- 网站**没有** CV 导航项，也没有 CV 下载按钮（避免出现打不开的死链）。
- 补上 PDF 后按 `MAINTENANCE.md` 第 5 节操作：放文件 → 取消 `_data/socials.yml` 里
  `cv_pdf` 的注释 → （可选）新建 `_pages/cv.md`。
- 如果有结构化的教育经历、获奖、学术服务，也可以做成结构化 CV 页面。

---

## E. News

`profile.md` 中 News 为空 → 首页 `announcements.enabled: false`，`_news/` 目录为空。
有真实事件（论文接收、新 preprint、学术报告）后，在 `_news/` 新建
`YYYY-MM-DD-xxx.md` 并把 `_pages/about.md` 的 `announcements.enabled` 改成 `true`。

---

## F. 展示顺序

`profile.md` 的 `Preferred Publication Order` 留空。
目前 `/publications/` 与首页都按**年份倒序**（2026 → 2025）排列：

1. QuantaSpike (2026)
2. SpikeLite (2026)
3. SpikeSTAG (2025)

如需改成你心里的重要度顺序（例如 SpikeSTAG → QuantaSpike → SpikeLite），
告诉我即可，改法是给每条 bib 加一个排序键并在 `_config.yml` 的 `scholar` 段调整
`sort_by` / `group_by`。

---

## G. 未填的 profile 字段

- [ ] Education（教育经历）
- [ ] Selected Honors（获奖）
- [ ] Academic Service（审稿 / 服务工作）
- [ ] Information Not Intended for Public Display（如需排除某些信息，请明确列出）
