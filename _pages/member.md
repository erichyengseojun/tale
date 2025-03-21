---
layout: default
title: Members
permalink: /members/
---

<style>
  section {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 30px;
  }

  @media (max-width: 1000px) {
    section { grid-template-columns: repeat(2, 1fr); }
  }

  img {
    width: 170px;
    max-height: 230px;
  }
</style>

{% for degree in site.data.data.member %}
  <h2>{{ degree[0] }}</h2>
  <section>
    {% for person in degree[1] %}
      <article>
        <a href="{{ person.url }}">
          <img src="{{ '/resource/img/person/' | append: person.name | append: '.jpg' | relative_url }}" alt="{{ person.name }}">
          <h3>{{ person.name }}</h3>
          <p>{{ person.period }}</p>
          <h5>{{ person.email }}</h5>
          <p>{{ person.description }}</p>
        </a>
      </article>
    {% endfor %}
  </section>
{% endfor %}