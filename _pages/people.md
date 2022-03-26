---
layout: page
title: people
permalink: /people/
description: group members
nav: true
display_categories: [PI, Assistant, Postdocs, Students]
horizontal: false
---

<!-- pages/people.md -->
<div class="projects">
  <!-- Display categorized people -->
  {%- for category in page.display_categories %}
  <h2 class="category">{{ category }}</h2>
  {%- assign categorized_project = site.people | where: "category", category -%}
  {%- assign sorted_project = categorized_project | sort: "importance" %}
  <!-- Generate cards for each people -->
  {% if page.horizontal -%}
  <div class="container">
    <div class="row row-cols-2">
    {%- for project in sorted_project -%}
      {% include projects_horizontal.html %}
    {%- endfor %}
    </div>
  </div>
  {%- else -%}
  <div class="grid">
    {%- for project in sorted_project -%}
      {% include projects.html %}
    {%- endfor %}
  </div>
  {%- endif -%}
  {% endfor %}
