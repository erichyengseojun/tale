---
layout: default
title: Lab Members
permalink: /member/
---

<style>
  @import url('https://fonts.googleapis.com/css2?family=Noto+Sans+KR:wght@300&display=swap');

  body {
    font-family: 'Noto Sans KR', sans-serif;
  }

  section {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 30px;
    margin-bottom: 40px;
  }

  @media (max-width: 1000px) {
    section {
      grid-template-columns: repeat(2, 1fr);
    }
  }

  article {
    text-align: left;
  }

  article img {
    width: 170px;
    max-height: 230px;
    display: block;
    margin: 0 auto 10px;
  }
</style>

{% for category in site.data.data.member %}
  <h2>{{ category[0] }}</h2>
  <section>
    {% for person in category[1] %}
      <article>
        {% if person.url %}
        <a href="{{ person.url }}" target="_blank">
        {% endif %}
          <img src="{{ '/resource/img/person/' | append: person.name | append: '.jpg' | relative_url }}" alt="{{ person.name }}">
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