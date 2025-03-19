---
layout: default
title: Publications
permalink: /publications/
---
<h1>Publications</h1>
<div id="publications">Loading...</div>

<script>
  fetch("{{ site.baseurl }}/data.json")
    .then(response => response.json())
    .then(json => {
      let container = document.getElementById("publications");
      container.innerHTML = "";

      json.paper.forEach(yearGroup => {
        let h3 = document.createElement("h3");
        h3.textContent = yearGroup.year;
        container.appendChild(h3);

        let section = document.createElement("section");
        yearGroup.content.forEach(paper => {
          let article = document.createElement("article");
          article.innerHTML = `
            <a href="${paper.url}"><h4>${paper.title}</h4></a>
            <h5>${paper.author}</h5>
            <p>${paper.cite}</p>
          `;
          section.appendChild(article);
        });

        container.appendChild(section);
      });
    });
</script>