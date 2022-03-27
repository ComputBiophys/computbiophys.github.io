---
layout: page
title: people
permalink: /people/
description: group members
nav: true
display_categories: [PI, Secretary, Postdocs, Graduate Students]
horizontal: false
---

<div class="row">
    <div class="col-sm-12 mt-3 mt-md-0">
        {% include figure.html path="assets/img/group_photo.jpg" title="The Group" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

<!-- pages/people.md -->
<div class="projects">
  <!-- Display categorized people -->
  {%- for category in page.display_categories %}
  <h2 class="category">{{ category }}</h2>
  {%- assign categorized_people = site.people | where: "category", category -%}
  {%- assign sorted_people = categorized_people | sort: "importance" %}
  <!-- Generate cards for each people -->
  {% if page.horizontal -%}
  <div class="container">
    <div class="row row-cols-2">
    {%- for project in sorted_people -%}
      {% include people_horizontal.html %}
    {%- endfor %}
    </div>
  </div>
  {%- else -%}
  <div class="grid">
    {%- for project in sorted_people -%}
      {% include people.html %}
    {%- endfor %}
  </div>
  {%- endif -%}
  {% endfor %}

