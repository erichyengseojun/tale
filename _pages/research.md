---
layout: default
title: Research Projects
permalink: /research/
---

<style>
  article.project {
    margin-bottom: 50px;
    padding-bottom: 20px;
    border-bottom: 1px solid #ccc;
  }

  article.project h3 {
    font-size: 1.5em;
    margin-bottom: 5px;
    color: #111;
  }

  article.project h5 {
    font-size: 1.1em;
    font-weight: 500;
    margin: 5px 0;
    color: #555;
  }

  article.project p {
    margin: 5px 0;
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

{% for project in site.data.data.project %}
<article class="project">
  <h3>{{ project.title }}</h3>
  <h5>{{ project.organization }}</h5>
  <p><strong>{{ project.period }}</strong></p>
  <p>{{ project.description }}</p>
</article>
{% endfor %}