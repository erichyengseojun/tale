---
layout: default
title: Research Projects
permalink: /research/
---
<h1>Research Projects</h1>
<div id="research">Loading...</div>

<script>
  fetch("{{ site.baseurl }}/data.json")
    .then(response => response.json())
    .then(json => {
      let container = document.getElementById("research");
      container.innerHTML = "";

      json.project.forEach(project => {
        let article = document.createElement("article");
        article.innerHTML = `
          <h4>${project.title}</h4>
          <h5>${project.organization}</h5>
          <p>${project.period}</p>
          <h5>${project.description}</h5>
        `;
        container.appendChild(article);
      });
    });
</script>