---
permalink: /about/collaborators.html
layout: people
title: TAC-HEP Collaborators
---


{% assign members = site.collaborators | where_exp:"item", "item.active and item.hidden != true"
                                     | last_name_sort: "name" %}
{% assign former_members = site.collaborators | where_exp: "item", "item.active == nil or item.active == false and item.hidden != true"
                                  | last_name_sort: "name" %}

<h1>TAC-HEP Collaborators</h1><br>

<div class="container-fluid">
<div class="row">
{% for person in members %}
  {% include standard_person_card.md person=person %}
{% endfor %}
</div>
</div>



<h1>Old</h1><br>

{% comment %}
{% assign members = site.collaborators | where_exp:"item", "item.active and item.hidden != true"
                                     | last_name_sort: "name" %}
{% assign former_members = site.collaborators | where_exp: "item", "item.active == nil or item.active == false and item.hidden != true"
                                  | last_name_sort: "name" %}

<h1>TAC-HEP Collaborators</h1><br>

<div class="container-fluid">
<div class="row">
{% for person in members %}
    {% include standard_person_card.md person=person %}
{% endfor %}
</div>
</div>
{% endcomment %}



