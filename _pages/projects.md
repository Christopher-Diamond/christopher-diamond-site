---
layout: page
title: projects
permalink: /projects/
description: Research, digital and collaborative projects.
nav: true
nav_order: 3
horizontal: false
---

<!-- pages/projects.md -->
<div class="projects">
{% if site.enable_project_categories and page.display_categories %}
  <!-- Display categorized projects -->
  {% for category in page.display_categories %}
  <a id="{{ category }}" href=".#{{ category }}">
    <h2 class="category">{{ category }}</h2>
  </a>
  {% assign categorized_projects = site.projects | where: "category", category %}
  {% assign sorted_projects = categorized_projects | sort: "importance" %}
  <!-- Generate cards for each project -->
  {% if page.horizontal %}
  <div class="container">
    <div class="row row-cols-1 row-cols-md-2">
    {% for project in sorted_projects %}
      {% include projects_horizontal.liquid %}
    {% endfor %}
    </div>
  </div>
  {% else %}
  <div class="row row-cols-1 row-cols-md-3">
    {% for project in sorted_projects %}
      {% include projects.liquid %}
    {% endfor %}
  </div>
  {% endif %}
  {% endfor %}

{% else %}

<!-- Display projects without categories -->

{% assign sorted_projects = site.projects | sort: "importance" %}

  <!-- Generate cards for each project -->

{% if page.horizontal %}

  <div class="container">
    <div class="row row-cols-1 row-cols-md-2">
    {% for project in sorted_projects %}
      {% include projects_horizontal.liquid %}
    {% endfor %}
    </div>
  </div>
  {% else %}
  <div class="row row-cols-1 row-cols-md-3">
    {% for project in sorted_projects %}
      {% include projects.liquid %}
    {% endfor %}
  </div>
  {% endif %}
{% endif %}
</div>

<p class="text-muted small mt-5">
Card images:
Translating Vidyāpati: <a href="https://commons.wikimedia.org/wiki/File:Manuscript_of_songs_of_Vidyapati,_Maithili_language,_Newar_script.jpg">manuscript of Vidyāpati’s songs</a>, Maithili in Newar script, Asa Safu Kuthi, Kathmandu (public domain).
Singing the Manuscript: <a href="https://commons.wikimedia.org/wiki/File:Chaitanya_sankirtan.jpg">Chaitanya’s nagar kīrtan in Nabadwip</a>, lithograph, Calcutta Art Studio, 19th century, British Library (public domain).
ANUBhasha and Mithila Studies Network: logos of each organisation.
</p>
