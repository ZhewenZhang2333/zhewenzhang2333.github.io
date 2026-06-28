---
layout: page
title: 项目
permalink: /projects/
description: 研究、工程实践与课程项目。
nav: true
nav_order: 4
display_categories: [研究与工程]
horizontal: false
---

以下项目来自过往研究实习、课程与工程实践。博士阶段项目将在研究方向确定后补充。

<div class="projects-list">
{% assign categorized_projects = site.projects | where: "category", "研究与工程" %}
{% assign sorted_projects = categorized_projects | sort: "importance" %}
{% for project in sorted_projects %}
  <section>
    <h3><a href="{{ project.url | relative_url }}">{{ project.title }}</a></h3>
    <p>
      {% if project.role %}<strong>角色：</strong>{{ project.role }}{% endif %}
      {% if project.role and project.period %} · {% endif %}
      {% if project.period %}<strong>时间：</strong>{{ project.period }}{% endif %}
    </p>
    <p>{{ project.description }}</p>
    {% if project.highlights %}
      <ul>
        {% for highlight in project.highlights %}
          <li>{{ highlight }}</li>
        {% endfor %}
      </ul>
    {% endif %}
  </section>
  {% unless forloop.last %}<hr>{% endunless %}
{% endfor %}
</div>

> 页面中的实验指标来自个人简历记录。项目代码、报告及可公开材料将在确认链接后补充。
