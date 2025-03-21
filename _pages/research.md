---
layout: default
title: Research Projects
permalink: /research/
---

{% for project in site.data.data.project %}
<article style="margin-bottom: 40px;">
  <h3>{{ project.title }}</h3>
  <h5>{{ project.organization }}</h5>
  <p><strong>{{ project.period }}</strong></p>
  <p>{{ project.description }}</p>
</article>
{% endfor %}