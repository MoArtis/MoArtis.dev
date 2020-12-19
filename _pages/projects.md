---
layout: page
title: Projects
noheader: true
use-site-title: true
meta-description: A selection of games, tools and mods I worked on.
permalink: /projects/
---

<div class="project-section">
    <h2 class="project-section-title">Commercial games</h2>
    <h3 class="project-section-subtitle">A selection of the commercial games I worked on.</h3>
    <hr>
</div>
{% include projectList.html projects=site.data.Projects.proGames %}

<div class="project-section">
    <h2 class="project-section-title">Game mods</h2>
    <h3 class="project-section-subtitle">A great way to learn about game development: Modifying existing games.</h3>
    <hr>
</div>
{% include projectList.html projects=site.data.Projects.mods %}

<div class="project-section">
    <h2 class="project-section-title">Prototypes</h2>
    <h3 class="project-section-subtitle">Some interesting prototypes from game jams or cancelled projects.</h3>
    <hr>
</div>
{% include projectList.html projects=site.data.Projects.prototypes %}
