---
layout: default
title: Lab Members
permalink: /members/
---

{% for category in site.data.data.member %}
  <h2>{{ category[0] }}</h2>
  <section style="display: flex; flex-wrap: wrap; gap: 30px; margin-bottom: 40px;">
    {% for person in category[1] %}
      <article style="width: 300px;">
        {% if person.url %}
        <a href="{{ person.url }}" target="_blank">
        {% endif %}
          <h3>{{ person.name }}</h3>
          <p><strong>{{ person.period }}</strong></p>
          <p>{{ person.description }}</p>
          <p><em>{{ person.email }}</em></p>
        {% if person.url %}
        </a>
        {% endif %}
      </article>
    {% endfor %}
  </section>
{% endfor %}