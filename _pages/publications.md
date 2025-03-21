---
layout: default
title: Publications
permalink: /publications/
---

<style>
  h3.year-heading {
    font-size: 1.8em;
    margin-top: 60px;
    margin-bottom: 20px;
    border-bottom: 2px solid #ccc;
    padding-bottom: 5px;
    color: #222;
  }

  section.publication-year {
    padding: 20px 0;
    border-bottom: 1px solid #ddd;
    margin-bottom: 40px;
  }

  article.publication {
    margin-bottom: 20px;
    padding-left: 10px;
  }

  article.publication h4 {
    margin: 5px 0;
  }

  article.publication p {
    margin: 3px 0;
    color: #333;
  }

  a {
    color: black;
    text-decoration: none;
    transition: color 0.2s ease;
  }

  a:hover {
    color: orange;
  }
</style>

{% for year_group in site.data.data.paper %}
  <h3 class="year-heading">{{ year_group.year }}</h3>
  <section class="publication-year">
    {% for paper in year_group.content %}
      <article class="publication">
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