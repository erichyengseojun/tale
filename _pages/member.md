---
layout: default
title: Members
permalink: /members/
---
<h1>Our Members</h1>
<div id="members">Loading...</div>

<script>
  fetch("{{ site.baseurl }}/data.json")
    .then(response => response.json())
    .then(json => {
      let container = document.getElementById("members");
      container.innerHTML = "";

      Object.keys(json.member).forEach(category => {
        if (json.member[category].length === 0) return;

        let section = document.createElement("section");
        let h2 = document.createElement("h2");
        h2.textContent = category;
        section.appendChild(h2);

        json.member[category].forEach(person => {
          let article = document.createElement("article");
          article.innerHTML = `
            <a href="${person.url}">
                <img src="{{ site.baseurl }}/resource/img/person/${person.name}.jpg" alt="${person.name}" />
                <h3>${person.name}</h3>
                <p>${person.period}</p>
                <h5>${person.email}</h5>
                <p>${person.description}</p>
            </a>
          `;
          section.appendChild(article);
        });

        container.appendChild(section);
      });
    });
</script>