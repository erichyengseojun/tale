---
layout: default
title: Publications
permalink: /publications/
---

{% for year_group in site.data.data.paper %}
  <h3>{{ year_group.year }}</h3>
  <section style="margin-bottom: 30px;">
    {% for paper in year_group.content %}
      <article style="margin-bottom: 20px;">
        {% if paper.url %}
        <a href="{{ paper.url }}" target="_blank"><h4>{{ paper.title }}</h4></a>
        {% else %}
        <h4>{{ paper.title }}</h4>
        {% endif %}
        <p><strong>{{ paper.author }}</strong></p>
        <p><em>{{ paper.cite }}</em></p>
      </article>
    {% endfor %}
  </section>
{% endfor %}