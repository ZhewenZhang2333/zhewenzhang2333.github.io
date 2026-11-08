---
layout: page
title: 项目
permalink: /projects/
description: 当前的宏观事件预测研究，以及此前在语言、视觉与自动规划方面的项目。
nav: true
nav_order: 4
display_categories: [当前研究, 研究与工程]
horizontal: false
---

## 当前研究

### [宏观事件与跨市场预测]({{ '/projects/macro-event-market-research/' | relative_url }})

当几种经济机制都能解释同一个事件，预测时已经公开的资料能否帮我们区分它们？这个项目关注事件前的概率判断和事件后的跨市场反应，记录每项判断所依据的证据与可检验的结果。[公开仓库](https://github.com/ZhewenZhang2333/macro-event-market-research)

## 研究与工程项目

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

既有项目的实验指标按个人简历中记录的评价口径列出。
