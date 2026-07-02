# 个人主页手动修改指南

本指南适用于仓库 `ZhewenZhang2333/zhewenzhang2333.github.io`。

正式主页：<https://zhewenzhang2333.github.io/>

## 1. 修改前先记住

- 内容源文件位于 `master` 分支。
- `gh-pages` 分支由 GitHub Actions 自动生成，**不要直接编辑或提交到该分支**。
- 英文首页位于 `/`，中文首页位于 `/zh/`；两者是独立文件，个人状态、学校、研究方向等信息变化时应同步更新。
- 文本文件统一保存为 UTF-8；YAML 缩进使用空格，不要使用 Tab。
- 小范围文字修改可以直接提交到 `master`；涉及多个文件时，建议新建分支并通过 Pull Request 合并。
- 不要在公开仓库中提交身份证号、手机号、家庭地址、证件扫描件、私人推荐信或未获授权的内部材料。

## 2. 常用信息对应的文件

| 要修改的内容                     | 文件                             | 主要位置                                                     |
| -------------------------------- | -------------------------------- | ------------------------------------------------------------ |
| 站点名称、简介、关键词、页脚     | `_config.yml`                    | 文件开头的 `title`、`description`、`keywords`、`footer_text` |
| 中文首页简介                     | `_pages/about.md`                | Front Matter 和 `---` 后面的正文                             |
| 英文首页简介                     | `_pages/about-en.md`             | Front Matter 和 `---` 后面的正文                             |
| 博士身份、教育、工作、项目、技能 | `_data/cv.yml`                   | `cv.sections` 下的各部分                                     |
| 公开联系方式和社交账号           | `_data/socials.yml`              | `email`、`github_username` 等字段                            |
| 头像                             | `assets/img/prof_pic.png`        | 替换同名文件即可                                             |
| 项目列表和项目详情               | `_projects/*.md`                 | 每个项目一个 Markdown 文件；项目页根据 Front Matter 自动汇总 |
| 首页“动态”                       | `_news/*.md`                     | 每条动态一个 Markdown 文件                                   |
| 动态页面入口                     | `_pages/news.md`                 | 页面标题、导航顺序和动态列表                                 |
| 论文页面入口                     | `_pages/publications.md`         | 当前为暂无论文说明，未来启用 BibTeX 展示                     |
| 教学页面                         | `_pages/teaching.md`             | 教学、竞赛指导与教育科研经历                                 |
| GitHub 仓库展示                  | `_data/repositories.yml`         | `github_repos` 列表                                          |
| 公开版 PDF 简历                  | `assets/pdf/Zhewen_Zhang_CV.pdf` | 覆盖同名文件即可更新首页下载内容                             |
| 项目页面入口和导航顺序           | `_pages/projects.md`             | `title`、`nav_order`、`description`                          |
| 未来论文数据                     | `_bibliography/papers.bib`       | BibTeX 条目；当前论文页面尚未启用 BibTeX 列表                |

通常只需要修改上表中的文件。不要为了改文字去修改 `Gemfile`、主题文件或 `.github/workflows/deploy.yml`。

## 3. 使用 GitHub 网页直接修改

适合修改一两处文字，不需要安装开发环境。

1. 打开仓库：<https://github.com/ZhewenZhang2333/zhewenzhang2333.github.io>。
2. 确认左上角分支为 `master`，不要选择 `gh-pages`。
3. 打开要修改的文件，点击右上角铅笔图标 **Edit this file**。
4. 修改后点击 **Commit changes...**。
5. 只改一个字段时可提交到 `master`；同时修改多个页面时选择创建新分支和 Pull Request。
6. 提交后打开仓库的 **Actions** 页面，等待 `Deploy site` 显示绿色成功标记。
7. 通常等待 1—3 分钟后刷新正式主页；浏览器缓存未更新时使用 `Ctrl+F5`。

推荐提交说明：

```text
content: update profile information
```

## 4. 使用本地 Git 修改

首次下载：

```powershell
git clone https://github.com/ZhewenZhang2333/zhewenzhang2333.github.io.git
cd zhewenzhang2333.github.io
npm ci
```

每次开始修改前：

```powershell
git checkout master
git pull --ff-only origin master
git checkout -b content/update-profile
```

修改后检查：

```powershell
npm run lint:prettier
npm run lint:style-contract
git status
git diff
```

如果本机已经安装 Ruby 和 Bundler，还可以执行完整构建：

```powershell
bundle install
bundle exec jekyll build
```

提交并推送：

```powershell
git add _config.yml _pages/about.md _pages/about-en.md _data/cv.yml
git commit -m "content: update profile information"
git push -u origin content/update-profile
```

随后在 GitHub 上创建 Pull Request，检查 `Deploy site` 成功后合并到 `master`。

## 5. 常见修改方法

### 5.1 修改中文和英文首页

中文首页：`_pages/about.md`，公开地址为 `/zh/`

英文首页：`_pages/about-en.md`，公开地址为 `/`

个人简介正文的具体修改位置：

- 中文：打开 `_pages/about.md`，修改 `## 个人简介` 与 `## 教育经历` 之间的文字。
- 英文：打开 `_pages/about-en.md`，修改 `## Professional Summary` 与 `## Education` 之间的文字。
- 首页头像旁的身份、学校和地点：修改对应文件 Front Matter 中的 `subtitle` 与 `profile.more_info`。
- 修改姓名、网站简介和全站默认语言：修改 `_config.yml` 开头的 `title`、`first_name`、`last_name`、`description` 和 `lang`。

文件开头两个 `---` 之间是 Front Matter，例如：

```yaml
---
layout: about
title: Home
permalink: /
subtitle: Joint Ph.D. Student · Harbin Institute of Technology, Shenzhen × Great Bay University
nav: true
nav_order: 1
---
```

- `title`：导航栏显示的名称。
- `subtitle`：头像旁边的简短身份说明。
- `nav`：是否显示在导航栏。
- `nav_order`：导航栏顺序，数字越小越靠前。
- `profile.more_info`：头像下方的学校、身份和地点。
- `announcements.enabled`：是否显示动态。
- `announcements.limit`：最多显示几条动态。

博士研究方向确定后，至少同步修改：

1. `_pages/about.md`
2. `_pages/about-en.md`
3. `_data/cv.yml` 中的 `summary` 和博士教育经历
4. `_config.yml` 中的 `description` 与 `keywords`

### 5.2 修改简历

网站已取消在线简历页面。中英文首页的下载按钮都指向：

```text
assets/pdf/Zhewen_Zhang_CV.pdf
```

更新公开简历时，直接用新版 PDF 覆盖这个同名文件即可；不要改变文件名，否则还需要同步修改两个首页中的下载链接。

`_data/cv.yml` 继续保留结构化履历数据，但不会自动生成 PDF。修改经历时应同时更新 PDF 和 `_data/cv.yml`。结构化数据目前包含：

- `教育经历`
- `工作与研究经历`
- `代表项目`
- `证书与奖项`
- `专业技能`
- `语言能力`

添加一条经历时，复制同一部分中的现有条目并修改。例如：

```yaml
- company: 机构名称
  position: 职位名称
  location: 城市，国家
  start_date: 2026-09
  end_date: present
  summary: 一句话说明主要职责。
  highlights:
    - 使用“行动 + 方法 + 结果”的方式描述成果。
    - 只保留可以公开且能够解释的数据。
```

注意：

- 日期建议统一使用 `YYYY-MM`；仍在进行的经历使用 `present`。
- 含有冒号、`#` 或特殊符号的长文本建议使用引号包裹。
- 同一级字段保持相同缩进。
- 删除经历时应删除整个条目，从开头的 `-` 删除到下一条同级内容之前。
- 修改公开邮箱时，同时更新 `_data/socials.yml` 和 `_data/cv.yml`。

### 5.3 替换头像

最简单的方法是将新图片命名为：

```text
assets/img/prof_pic.png
```

然后覆盖原文件。建议：

- 使用正方形或接近正方形的正式照片。
- 推荐尺寸为 800×800 至 1600×1600。
- 文件尽量小于 1 MB。
- 不要改变文件名，这样无需修改首页配置。

如果使用其他文件名，需要同步修改 `_pages/about.md` 和 `_pages/about-en.md` 中的 `profile.image`。

### 5.4 修改邮箱和社交账号

文件：`_data/socials.yml`

```yaml
email: your-name@university.edu
github_username: ZhewenZhang2333
linkedin_username: your-linkedin-id
orcid_id: 0000-0000-0000-0000
scholar_userid: your-google-scholar-id
```

没有注册或不希望公开的字段直接删除或留空。获得学校邮箱后，还需要同步修改 `_data/cv.yml` 中的 `email`。

### 5.5 添加项目

在 `_projects/` 下新建一个英文小写、使用连字符的文件，例如：

```text
_projects/new-research-project.md
```

模板：

```markdown
---
layout: page
title: 项目名称
description: 一句话项目简介
importance: 5
category: 研究与工程
---

## 项目概述

说明问题背景、项目目标和你的角色。

## 主要工作

- 负责的具体工作。
- 使用的方法、模型或系统。
- 与其他成员合作时明确自己的贡献。

## 结果

- 可验证的指标、演示、报告或实际应用。

[代码仓库](https://github.com/用户名/仓库名)

**技术栈：** Python, PyTorch, ...
```

- `importance` 越小，项目显示越靠前。
- `category` 必须保持为 `研究与工程`，否则当前项目页不会显示该项目。
- 没有公开代码时可以不放链接，但不要使用无效占位链接。
- 内部指标应标注测试集性质，不能公开的数据不要上传。
- 项目图片可放在 `assets/img/`，并在 Front Matter 中增加 `img: 文件名`。

### 5.6 删除或暂时隐藏项目

彻底删除：删除 `_projects/` 中对应的 Markdown 文件。

暂时隐藏：在该项目 Front Matter 中增加：

```yaml
published: false
```

### 5.7 添加首页动态

在 `_news/` 下新建文件，文件名建议使用 `YYYY-MM-DD-short-title.md`：

```markdown
---
layout: post
date: 2026-09-01 00:00:00+0800
inline: true
related_posts: false
---

开始联合培养博士阶段学习。
```

动态正文保持一两句话即可，适合记录入学、奖项、论文、报告、开源项目和重要活动。

### 5.8 修改 GitHub 仓库展示列表

文件：`_data/repositories.yml`

```yaml
github_repos:
  - ZhewenZhang2333/deep-learning-model
  - ZhewenZhang2333/another-public-repository
```

只添加公开仓库。仓库名必须使用 `用户名/仓库名` 格式。

### 5.9 以后添加论文

当前论文页面仅显示“目前暂无公开论文”。以后有论文时：

1. 将规范 BibTeX 条目添加到 `_bibliography/papers.bib`。
2. 准备 DOI、arXiv、PDF、代码、项目页和预览图等可公开链接。
3. 在 `_pages/publications.md` 中启用 BibTeX 论文列表。
4. 如需首页精选论文，将 `_pages/about.md` 的 `selected_papers` 改为 `true`，并在 BibTeX 条目中标记 `selected={true}`。
5. 同步更新英文页面和 CV。

第一次启用论文页面涉及页面结构，建议先在独立分支中完成并确认预览，不要直接在 `master` 上试改。

## 6. YAML 和 Markdown 常见错误

- Front Matter 必须以 `---` 开始并以 `---` 结束。
- YAML 冒号后必须有空格，例如 `title: 首页`。
- 不要使用 Tab 缩进。
- 列表项以 `- ` 开头，并与同级条目对齐。
- 文件名尽量只使用英文小写字母、数字和连字符。
- Markdown 链接格式为 `[显示文字](https://example.com)`。
- 修改中文时注意不要把文件保存为 ANSI、GBK 或出现乱码。
- 不要删除 Liquid 代码中的双花括号，例如 `{{ '/projects/' | relative_url }}`。

如果 Actions 构建失败，先检查最近修改的 YAML 缩进、Front Matter 和链接格式。

## 7. 发布与回退

正常发布流程：

```text
修改 master 源文件 → Deploy site 构建 → 自动更新 gh-pages → GitHub Pages 发布
```

如果线上内容有误：

1. 在 GitHub 中找到导致问题的提交。
2. 使用 **Revert** 创建回退 Pull Request，或在本地恢复相应文件。
3. 不要删除 `gh-pages` 分支，也不要手动覆盖该分支。
4. 回退合并后等待 `Deploy site` 再次成功。

## 8. 每次更新后的检查清单

- [ ] 中文和英文身份信息是否一致。
- [ ] 时间、学校名称和职位是否准确。
- [ ] 邮箱、GitHub 和项目链接是否可以打开。
- [ ] 是否删除了不应公开的隐私或内部信息。
- [ ] 项目指标是否注明来源，是否能够合理解释。
- [ ] `npm run lint:prettier` 是否通过。
- [ ] `npm run lint:style-contract` 是否通过。
- [ ] GitHub Actions 的 `Deploy site` 是否成功。
- [ ] 手机和电脑上是否都能正常阅读。
