---
layout: page
title: 项目
permalink: /projects/
description: 代表性的人工智能研究、工程实践与课程项目。
nav: true
nav_order: 2
display_categories: [研究与工程]
horizontal: false
---

<div class="projects">
{% assign categorized_projects = site.projects | where: "category", "研究与工程" %}
{% assign sorted_projects = categorized_projects | sort: "importance" %}
<div class="row row-cols-1 row-cols-md-2">
{% for project in sorted_projects %}
  {% include projects.liquid %}
{% endfor %}
</div>
</div>

> 页面中的实验指标来自个人简历记录。项目代码、报告及可公开材料将在确认链接后补充。
