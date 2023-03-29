---
permalink: /about/collaborators.html
layout: people
title: TAC-HEP Collaborators
---

{% assign univs = site.institutes %}

{% assign univpeople = '' %}
{% assign labpeople = '' %}

<h1>TAC-HEP University Collaborators</h1><br>

{% for univ in univs %}
  {% for person in univ.personnel %}
    {% if univ.category == 'university' %}
      {% assign univpeople = univpeople | append: "," | append: person %}
    {% elsif univ.category == 'lab' %}
      {% assign labpeople = labpeople | append: "," | append: person %}
    {% endif %}
  {% endfor %}
{% endfor %}

{% assign univarray = univpeople | split: ',' %}
{% assign labarray = labpeople | split: ',' %}
{% assign univarray = univarray | compact %}
{% assign labarray = labarray | compact %}

<h2>university people - {{ univarray.size }} </h2>
<h2>lab people - {{ labarray.size }} </h2>

<h1>TAC-HEP University Collaborators</h1><br>

<div class="container-fluid">
  <div class="row">
    {% for person in univarray %}
       <h2>{{ person }} - university</h2>
    {% endfor %}
  </div>
</div>

<h1>TAC-HEP DOE Laboratory Collaborators</h1><br>

<div class="container-fluid">
  <div class="row">
    {% for person in labarray %}
       <h2>{{ person }} - lab</h2>
    {% endfor %}
  </div>
</div>

<h1>Old</h1><br>

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



