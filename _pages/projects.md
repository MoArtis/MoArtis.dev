---
layout: page
title: Projects
noheader: true
use-site-title: true
permalink: /projects/
# bigimg: /img/IMG_20190820_091812.jpg
---

<div class="project-section">
    <h2 class="project-section-title">Commercial games</h2>
    <h3 class="project-section-subtitle">A selection of the commercial games I worked on.</h3>
    <hr>
</div>
{% include projectList.html projects=site.data.Projects.proGames %}

<div class="project-section">
    <h2 class="project-section-title">Game mods</h2>
    <h3 class="project-section-subtitle">A good way to learn about gamedev: modify other's games.</h3>
    <hr>
</div>
{% include projectList.html projects=site.data.Projects.mods %}

<div class="project-section">
    <h2 class="project-section-title">Prototypes</h2>
    <h3 class="project-section-subtitle">Some interesting prototypes from gamejams or cancelled projects.</h3>
    <hr>
</div>
{% include projectList.html projects=site.data.Projects.prototypes %}
