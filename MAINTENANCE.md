# 网站维护说明（中文）

本网站基于 [al-folio](https://github.com/alshedivat/al-folio) v1.x。
al-folio v1.x 是一个「Jekyll 启动模板」：布局、样式、脚本都由 gem 提供，**不在本仓库里**。
日常维护只需要改内容和配置，不需要碰主题文件。

访问地址：`https://blackhole-h.github.io/`
仓库：`Blackhole-H.github.io`

---

## 1. 更新个人信息

| 想改什么 | 改哪个文件 |
| --- | --- |
| 姓名、职位、学校、邮箱、关键词、SEO 描述 | `_config.yml` 顶部 `Site settings` 段（`first_name` / `last_name` / `description` / `keywords`） |
| 首页姓名下方那一行（职位 + 方向） | `_pages/about.md` 的 `subtitle:` |
| 首页正文自我介绍 | `_pages/about.md` 正文（front matter 之后的第一段） |
| GitHub / ORCID / Google Scholar / CV 链接 | `_data/socials.yml` |
| 头像 | 替换 `assets/img/prof_pic.jpg`（建议 1:1 或 4:5，短边 ≥ 600px） |
| 页脚文字 | `_config.yml` 的 `footer_text:` |

`_data/socials.yml` 里**没有填**的字段不会渲染出按钮。不要为了「看起来完整」填占位链接。

---

## 2. 添加新论文

只需要两步：

1. 在 `_bibliography/papers.bib` 末尾加一条 BibTeX：

```bibtex
@inproceedings{hu2027yourpaper,
  abbr          = {NeurIPS},
  bibtex_show   = {true},
  selected      = {true},          % 想在首页展示就加这行
  title         = {Your Paper Title},
  author        = {Hu, Bang and Someone, Else},
  booktitle     = {NeurIPS},
  year          = {2027},
  arxiv         = {2701.01234},    % 只填编号，链接自动生成
  html          = {https://...},   % 论文主页 / arXiv 页
  pdf           = {your_paper.pdf},% 文件放 assets/pdf/ 下
  code          = {https://github.com/...},
  abstract      = {论文摘要，点 Abs 按钮时展开},
  preview       = {your_preview.svg} % 缩略图放 assets/img/publication_preview/
}
```

2. 把缩略图放进 `assets/img/publication_preview/`（见下节）。

排序：默认按年份倒序。**同一个键只加一次**，`selected = {true}` 的条目会同时出现在首页
`Selected Publications` 和 `/publications/` 页面。

常用字段（`_config.yml` 的 `filtered_bibtex_keywords` 里已列出全部）：

| 字段 | 作用 |
| --- | --- |
| `abbr` | 左侧的小徽章文字，配合 `_data/venues.yml` 可变成链接 |
| `arxiv` | arXiv 编号，自动生成 arXiv 按钮 |
| `pdf` / `code` / `website` / `slides` / `poster` / `video` / `blog` | 对应的按钮 |
| `abstract` | Abs 按钮 |
| `bibtex_show` | Bib 按钮（展开 BibTeX） |
| `preview` | 左侧缩略图 |
| `selected` | 是否进首页精选 |

**只有真实存在的资源才填对应字段**，没有就整行删掉。

作者高亮由 `_config.yml` 的 `scholar.last_name` / `scholar.first_name` 控制，目前是
`Hu` / `[Bang, B.]`，一般不用改。合作者主页链接写在 `_data/coauthors.yml`。

---

## 3. 替换论文缩略图

目前三张缩略图（`spikestag.svg` / `quantaspike.svg` / `spikelite.svg`）是**排版占位卡片**，
不是论文真实插图 —— 避免未经授权使用他人图片。

换成真实方法图：

1. 导出图片（建议 16:9，宽 ≥ 640px，SVG 或 PNG）。
2. 放到 `assets/img/publication_preview/`。
3. 把 `papers.bib` 里对应条目的 `preview = {...}` 改成新文件名。

图片文件名改了不用动任何 HTML —— 缩略图完全由 bib 条目驱动。

---

## 4. 更新研究兴趣 / 当前研究

- 首页的两栏 `Research Interests`：`_pages/about.md` 里 `<div class="research-grid">` 那段。
- 首页末尾 `Current Research`：`_pages/about.md` 最后一个二级标题。
- 独立 Research 页：`_pages/research.md`。

`_includes/site-extras.html` 是**全站唯一的自定义样式文件**（一个 `<style>` 块），目前被
`about.md`、`publications.md`、`research.md`、`404.md` 四个页面 include，包含两部分内容：

1. Footer 配色覆盖 —— al-folio 浅色主题默认的 footer 是近黑色（`#1c1c1d`），
   与本站的浅色学术风不符，这里已覆盖为浅色（`#faf9f7`），暗色模式覆盖为深色；
2. About / Research 两页共用的研究卡片样式。

要改卡片配色、圆角、字号或 footer 颜色，只改这个文件即可，所有页面同步生效。
**注意**：以后新增页面时，请在页面开头加一行 `{% include site-extras.html %}`，
否则该页的 footer 会退回 al-folio 默认的黑色样式。

---

## 5. 更新 CV

CV 目前**未提供**，因此导航栏没有 CV 入口，`_data/socials.yml` 里的 `cv_pdf` 也是注释状态。

补上之后：

1. 把 PDF 放到 `assets/pdf/`（例如 `Bang_Hu_CV.pdf`）。
2. 在 `_data/socials.yml` 里取消注释并填写：
   ```yaml
   cv_pdf: /assets/pdf/Bang_Hu_CV.pdf
   ```
   这样首页底部的 CV 按钮就出现了。
3. 如果想要一个独立的 `/cv/` 页面，新建 `_pages/cv.md`：

```markdown
---
layout: page
permalink: /cv/
title: CV
description: Curriculum vitae of Bang Hu.
nav: true
nav_order: 4
---

[Download PDF](/assets/pdf/Bang_Hu_CV.pdf)
```

以后换版本只要覆盖同名 PDF 文件即可，不用改页面。

---

## 6. 本地预览

需要 Ruby（本项目用 Ruby 3.4 验证过）+ Bundler。

```bash
bundle install
bundle exec jekyll serve     # http://localhost:4000/
```

注意：`baseurl` 必须保持为空（这是 `username.github.io` 类型的站点）。
改了 `_config.yml`、`_pages/`、`_bibliography/` 之外的文件基本都会触发自动重建；
改了 `_config.yml` 需要重启 `jekyll serve`。

Windows 上如果 `bundle install` 报 native extension 编译错误，是因为缺少 MSYS2 工具链，
运行 `ridk install` 装上即可。

---

## 7. 发布到 GitHub Pages

推送到 `main` 分支即可，`.github/workflows/deploy.yml` 会自动构建并部署到 `gh-pages` 分支。

```bash
git add -A
git commit -m "..."
git push origin main
```

首次部署前只需做一次仓库设置：

1. **Settings → Actions → General → Workflow permissions**：选 **Read and write permissions**，保存。
2. **Settings → Pages → Build and deployment**：Source 选 **Deploy from a branch**，分支选 **gh-pages**（不是 `main`）。

之后在 **Actions** 标签页看 "Deploy site" 工作流变绿，约 4 分钟后
`https://blackhole-h.github.io/` 即更新。

---

## 8. 其他

- **News**：有真实事件（论文接收、新的 preprint、学术报告）后，在 `_news/` 下新建
  `YYYY-MM-DD-xxx.md`，并把 `_pages/about.md` 的 `announcements.enabled` 改成 `true`。
  没有真实事件就保持关闭。
- **不要**在 `_config.yml` 里改 `baseurl`，也不要往仓库里加 `_layouts/` `_includes/`（除已有的
  `site-extras.html`）`_sass/` 之外的主题副本 —— v1.x 的运行时在 gem 里，本地副本会造成升级漂移。
- 升级 al-folio：`bundle update`，然后 `bundle exec al-folio upgrade audit`。
