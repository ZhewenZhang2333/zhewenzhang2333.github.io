# Zhewen Zhang — Personal Homepage

这是张哲闻（Zhewen Zhang）的中英双语个人学术主页，基于 [al-folio](https://github.com/alshedivat/al-folio) 构建。

- 中文主页：<https://zhewenzhang2333.github.io/>
- English page：<https://zhewenzhang2333.github.io/en/>
- GitHub：<https://github.com/ZhewenZhang2333>

## 内容

- 联合培养博士生个人介绍
- 教育与工作经历
- 人工智能研究与工程项目
- 中文在线简历
- 中英文双语入口

论文栏目目前隐藏，后续有公开成果时可通过 `_bibliography/papers.bib` 恢复。

## 本地检查

```bash
npm ci
npm run lint:prettier
npm run lint:style-contract
bundle exec jekyll build
```

完整 Jekyll 构建需要 Ruby 3.3 和 Bundler。推送到 `master` 后，GitHub Actions 会自动构建并部署 GitHub Pages。

## 主要内容文件

- `_pages/about.md`：中文主页
- `_pages/about-en.md`：英文主页
- `_pages/cv.md`：在线简历入口
- `_data/cv.yml`：结构化履历
- `_projects/`：项目详情
- `_data/socials.yml`：公开联系方式
