---
permalink: /about/collaborators.html
layout: people
title: TAC-HEP Collaborators
---

{% assign univs = site.institutes %}

<h1>TAC-HEP University Collaborators</h1><br>

<div class="container-fluid">
  <div class="row">
    {% for univ in univs %}
      {% for person in univ.personnel %}
        {% assign collaborator = site.collaborators | where_exp:"collaborator", "collaborator.shortname == person"
    | first %}
        {% if collaborator.active and collaborator.hidden != true %}
          {% if univ.category == 'university' %}
            {% include standard_person_card.md person=collaborator %}
          {% endif %}
        {% endif %}
      {% endfor %}
    {% endfor %}
  </div>
</div>

<h1>TAC-HEP Laboratory Collaborators</h1><br>

<h1>Old</h1><br>

{% assign members = site.collaborators | where_exp:"item", "item.active and item.hidden != true"
                                     | last_name_sort: "name" %}
{% assign former_members = site.collaborators | where_exp: "item", "item.active == nil or item.active == false and item.hidden != true"
                                  | last_name_sort: "name" %}


<h1>TAC-HEP University Collaborators</h1><br>

<div class="container-fluid">
<div class="row">
{% for person in members %}
    {% include standard_person_card.md person=person %}
{% endfor %}
</div>
</div>

<h1>TAC-HEP DOE Lab Collaborators</h1><br>

<div class="container-fluid">
<div class="row">
{% for person in members %}
    {% include standard_person_card.md person=person %}
{% endfor %}
</div>
</div>

{%- comment -%}
<h1>Former Collaborators</h1><br>

<div class="container-fluid">
<div class="row">
{% for person in former_members %}
    {% include standard_person_card.md person=person %}
{% endfor %}
</div>
</div>
{%- endcomment -%}

