# Zhewen Zhang · 张哲闻

张哲闻的个人学术主页，基于 [al-folio](https://github.com/alshedivat/al-folio) 构建。

[English homepage](https://zhewenzhang2333.github.io/) · [中文主页](https://zhewenzhang2333.github.io/zh/) · [研究项目](https://zhewenzhang2333.github.io/projects/) · [教学经历](https://zhewenzhang2333.github.io/teaching/)

## 内容维护

- `_pages/about-en.md` 和 `_pages/about.md` 分别维护英文和中文首页。
- `_projects/` 保存项目详情，`_pages/projects.md` 维护项目索引。
- `_news/` 保存动态，`assets/pdf/Zhewen_Zhang_CV.pdf` 是首页提供下载的简历。
- `master` 保存站点源码。GitHub Actions 构建 Jekyll 并发布到 `gh-pages`。

## 本地检查

```bash
npm ci
npm run lint:prettier
npm run lint:style-contract
bundle exec jekyll build
```
